# Backend integration plan

Recommended first implementation:
- Android: Kotlin + Jetpack Compose.
- Backend: Supabase Edge Functions (or another server-side runtime).
- Database: store connected account IDs, encrypted token references, upload jobs and per-platform status.
- Video storage: private object storage with short-lived signed URLs. Meta publishing requires the video to be fetchable by Meta's servers during publishing.
- Secrets: store OAuth client secrets and platform credentials only in server-side secret storage.

## Suggested endpoints
- `POST /oauth/youtube/start`
- `GET /oauth/youtube/callback`
- `POST /oauth/meta/start`
- `GET /oauth/meta/callback`
- `POST /uploads` — create a job and receive a signed upload URL
- `POST /publish` — validate selected destinations and enqueue per-platform jobs
- `GET /jobs/{jobId}` — return per-platform states

## Job model
`id, owner_id, video_object_key, title, caption, selected_platforms, created_at`

Per-platform status:
`queued | uploading | processing | published | failed`

Store provider post/video IDs and safe error summaries. Use idempotency keys to avoid duplicate posts after retries.

## Platform notes
- YouTube Data API `videos.insert` supports video upload and metadata; use OAuth scope `youtube.upload`. Prefer resumable uploads for mobile networks.
- Instagram publishing requires an eligible Instagram Professional account and the relevant Meta permissions. Reels publishing uses a media container, status check, then publish call. The media URL must be accessible to Meta.
- Facebook Reels publishing uses Meta's Reels publishing flow and Page access permissions.

## Security checklist
- Use OAuth authorization-code flow and validate `state`.
- Never ask users to paste passwords.
- Encrypt refresh tokens at rest.
- Keep access tokens off device logs and analytics.
- Add account disconnect and data deletion.
- Publish only after the user explicitly confirms.
