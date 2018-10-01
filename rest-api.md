# REST API specification

- all request / response should be json format.
- token will be sent via `Authorization: Bearer <token>`.

## API

- GET /initialize
  - Initialize entpoint.

- POST /auth/token
- POST /auth/renew
- DELETE /auth/expire
- GET /auth/me

- GET /members?channel_id=
- POST /members

- GET /channels
- POST /channels/:channel_id/join_status
- DELETE /channels/:channel_id/join_status
- POST /channels/:channel_id/messages
- DELETE /channels/:channel_id/messages/:id

- GET /messages?channel_ids=&maximum_id=&limit=

- GET /direct_messages?recipient_id=&after=&limit=
- POST /direct_messages
- DELETE /direct_messages/:id

- GET /admin/members
- PATCH /admin/members/:id/approve

- GET /admin/channels
- POST /admin/channels
- PATCH /admin/channels
  - enable to rename only
- PATCH /admin/channels/:id/archive
