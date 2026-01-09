# Findings & Decisions

## Requirements
- Users must log in with email + password
- Sessions expire after 24 hours of inactivity
- Passwords must be hashed (never stored plain)
- Support "remember me" option (extends to 30 days)

## Research Findings
- Existing codebase uses Express.js with no auth
- Database is PostgreSQL with Prisma ORM
- Frontend is React with fetch for API calls
- No existing User table - need to create

## Technical Decisions
| Decision | Rationale |
|----------|-----------|
| bcryptjs over bcrypt | Pure JS, no native dependencies, works on all platforms |
| Redis for sessions | Already used for caching, familiar to team |
| HTTP-only cookies | Prevents XSS attacks on session token |
| CSRF tokens | Required for state-changing requests |

## Issues Encountered
| Issue | Resolution |
|-------|------------|
| Prisma migration failed | Had to reset dev database, re-run migrations |
| CORS blocking login | Added credentials: 'include' to fetch calls |

## Resources
- OWASP Auth Cheatsheet: https://cheatsheetseries.owasp.org/
- Express session docs: https://www.npmjs.com/package/express-session
- Prisma User model example: internal wiki /docs/prisma
