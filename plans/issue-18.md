### Goal
Set up the core backend service and integrate WhatsApp Cloud API webhooks to receive and verify messages securely.

### Steps
1. Initialize project structure, dependencies, and environment configuration template (`.env.example`).
2. Implement `GET /webhook` verification endpoint handling Meta's `hub.mode`, `hub.verify_token`, and `hub.challenge`.
3. Implement `POST /webhook` endpoint to receive incoming WhatsApp event payloads.
4. Add payload signature verification (`X-Hub-Signature-256`) for request security.
5. Parse incoming message objects (sender phone number, message text, message ID) into structured data.
6. Configure local tunneling documentation (e.g. ngrok/Cloudflare) and test the webhook against the Meta developer portal.

### What could go wrong
- Webhook verification handshake fails if the response returns JSON instead of the raw challenge string.
- Signature verification fails due to body parsers modifying the raw payload buffer before hashing.
- Tunnel disconnection or URL expiration interrupts webhook deliveries during local testing.

### Done when
- [ ] Backend service starts locally and passes all linting and tests.
- [ ] Meta webhook verification handshake succeeds with the GET endpoint.
- [ ] Inbound WhatsApp text messages hit the POST endpoint, pass signature verification, and are parsed and logged.