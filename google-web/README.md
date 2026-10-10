# MailStudio Google Web

Free hosting through Google Apps Script. No paid Render resource is used.

Deploy `Code.gs`, `Index.html` and `appsscript.json` in a standalone Apps Script project. Enable Gmail advanced service v1; deploy a web app executing as **User accessing the web app**, access **Anyone with a Google account**. Set the script property `adminEmail` to the workspace owner Gmail address; do not hardcode personal identities in public source.

Each Gmail signs in and authorizes independently. Admin registers an address; the invited user opens the same app, connects their account and shares their newly created business-data spreadsheet with the admin. User sees only their own data; admin can configure each mailbox and see cached records. Each user must install their own time trigger. Admin cannot use their authorization to send from another mailbox. Gmail quota and authorization requirements apply.

New mailbox sending is disabled; new tasks are paused. Independent daily/category caps, fixed/random spacing, timezone, weekdays, start date and optional warmup are configurable. Google triggers may run late. Manual reply retains the original bypass of automatic window/spacing, but counts against caps. Sending journal is persisted before Gmail; unknown outcomes block further sends and never automatically replay. Followups retain original thread headers and frozen template and stop on normal replies. Only sent-folder matches resolve unknown records.

Migrated: mailbox invitation, groups, contact CSV import/dedup, template substitution, task control, configurable schedules, first/followup/manual messages, text conversation cache, drafts, attachments, sent history and JSON backups.

Remaining differences: mailbox credentials use Google consent instead of app passwords; original desktop SQLite migration and original bulk delivery ring tests are not implemented in this version. Existing desktop packages remain available. Attachments are not cached for incoming messages. Gmail and Google authorization policy may limit new external users of an unverified personal app.

Validation: `node tests.cjs` (mocked provider, no live email). Browser code syntax checked. Deployment and hosted authorization still require validation.
