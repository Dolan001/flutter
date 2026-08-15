# Flutter WebSocket client

- Validate versioned frames before mapping them into domain events. Keep sockets, retry policy, secure
  ticket acquisition, cursor storage, and connectivity/lifecycle handling outside widgets.
- Use secure cookies where supported or short-lived single-use HTTPS-issued tickets; never persist or
  log reusable URL tokens.
- Reconnect with capped exponential backoff and jitter only when network and app lifecycle allow.
  Resume by cursor, detect sequence gaps, HTTP-resync, deduplicate event IDs, and reconcile command IDs.
- Bound queues and expose connecting/live/degraded/offline/resync states. Persist drafts, not unbounded
  frames; acknowledge sends only after server ack.
- Suspend or deliberately retain connections on background according to product policy. Integrate
  offline push notifications for background delivery instead of assuming a permanent socket.
- Test Android/iOS lifecycle, network changes, auth expiry, reconnect, duplicates/order gaps, resync,
  malformed frames, offline send, accessibility announcements, and app termination/restoration.
