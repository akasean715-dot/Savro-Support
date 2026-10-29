# Savro Support starter
Separate customer Help Center, searchable FAQ, ticket creation, private admin inbox, ticket replies and status management.

## Local setup (Windows / VS Code)
1. Install Node.js 20+.
2. Copy `.env.example` to `.env`.
3. Fill in MySQL credentials for a **separate support database/schema** (for example `savro_support`). Never point this at the existing Savro app database. Use `DB_SSL=true` for TLS.
4. Set a unique admin email/password (12+ characters) and a random `JWT_SECRET` of at least 32 characters.
5. In terminal run `npm install` then `npm start`.
6. Open `http://localhost:3010` and select Admin sign in.

The database/schema must exist and its user needs permission to create tables. First startup creates support tables, FAQ articles, and the initial admin. It will not reset an existing admin password from environment variables.

## Important MVP limitations
- Ticket submission, secure ticket-access token, customer replies, admin login, ticket inbox, status and priority updates are implemented.
- Email sending is **not configured** yet; replies are visible in the ticket portal but no email notifications are sent.
- Conversation updates are refresh-based, not true WebSocket live chat yet.
- Before public launch, add and test email notifications, CAPTCHA/bot protection, backups, privacy/retention policy, and abuse prevention.
- Keep `.env` private; never commit it or paste credentials into chat.
- Deploy this as a new GitHub repository and separate Render service. Keep Savro's current repo/service/database tables untouched.
