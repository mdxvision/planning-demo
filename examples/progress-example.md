# Progress Log

## Session: 2026-01-09

### Current Status
- **Phase:** 4 - Testing & Verification
- **Started:** 2026-01-08

### Actions Taken
- [x] Created User model in Prisma schema
- [x] Ran migration: `npx prisma migrate dev --name add-users`
- [x] Built auth service with login/logout methods
- [x] Created /api/auth/login POST endpoint
- [x] Created /api/auth/logout POST endpoint
- [x] Added session middleware to Express app
- [x] Built LoginForm React component
- [x] Connected form to API with error handling
- [x] Wrote tests for auth endpoints

### Test Results
| Test | Expected | Actual | Status |
|------|----------|--------|--------|
| Valid login | 200 + session cookie | 200 + session cookie | PASS |
| Wrong password | 401 Unauthorized | 401 Unauthorized | PASS |
| Missing email | 400 Bad Request | 400 Bad Request | PASS |
| Logout clears session | No session cookie | No session cookie | PASS |
| Session expiry | 401 after 24h | Not yet tested | PENDING |

### Errors
| Error | Resolution |
|-------|------------|
| "Cannot find module bcrypt" | Switched to bcryptjs |
| Redis ECONNREFUSED | Started Redis with `brew services start redis` |
| Test failing on CI | Added Redis service to GitHub Actions workflow |
