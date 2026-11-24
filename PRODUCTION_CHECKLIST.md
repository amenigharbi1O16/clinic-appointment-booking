# Production Checklist

Project: Clinic Appointment Booking
Server: [WildFly version]  |  Database: PostgreSQL [version]  |  Date checked: [date]

| Done | Item | Proof / how I checked it |
|---|---|---|
| [ ] | Credentials are read from the environment or the server, not from source | [Where the datasource password is defined, and the command that shows no password in the repository] |
| [ ] | The production persistence unit uses PostgreSQL, not H2 | [Name of the persistence unit / Maven profile, and the log line showing PostgreSQL] |
| [ ] | `hbm2ddl.auto` is `validate`, or the schema is managed by migrations | [The line in the production persistence configuration] |
| [ ] | The WAR was deployed to a clean server and the main flow was exercised | [Server version, deployment command, and the flow I tested: book, cancel, doctor login, schedule] |
| [ ] | Session cookies are HttpOnly; Secure is set when served over HTTPS | [The setting in `web.xml` and how I checked it in the browser] |
| [ ] | Logout invalidates the session on the server | [The code line and how I tested it] |
| [ ] | BCrypt cost is at least 10 | [The cost value in the code] |
| [ ] | Error pages do not expose stack traces | [How I triggered an error and what the user sees] |
| [ ] | Default test accounts are documented and disabled or changed for production | [How they are disabled in the production profile] |
| [ ] | The database backup and restore steps are written down | [The backup and restore commands, written below] |

## Backup and restore

Backup: [your command]
Restore: [your command]

## Deployment notes

[Order of the steps I followed, and any problem I met]