# User Management

## User Account Features

Comprehensive user account management system for PokeTradeVault.

## Registration

### Registration Flow
1. User provides email, username, password
2. System validates input:
   - Email format is valid
   - Username is unique and meets requirements
   - Password meets security requirements
3. System creates account
4. Verification email sent (optional for MVP)

### Username Requirements
- 3-20 characters
- Alphanumeric plus underscore and hyphen
- Must start with letter
- Case-insensitive uniqueness

### Password Requirements
- Minimum 8 characters
- At least one uppercase letter
- At least one lowercase letter
- At least one number
- At least one special character (recommended)

## Authentication

### Login
- Email/username + password authentication
- JWT token issued on successful login
- Token expires after 24 hours
- Refresh token for extended sessions (future)

### Session Management
- Token stored in HTTP-only cookie (web)
- Token stored securely (mobile)
- Automatic logout on token expiration
- Manual logout invalidates token

## User Profile

### Profile Information
- **Public**:
  - Username
  - Reputation score
  - Member since date
  - Trade statistics
- **Private**:
  - Email address
  - Account settings

### Profile Management
- Update username (with cooldown period)
- Change password (requires current password)
- Update email (requires verification)
- Delete account (soft delete with grace period)

## Reputation System

### Reputation Score
- Starts at 0
- Increases with successful trades
- Decreases with cancelled trades or violations
- Displayed on user profile

### Reputation Calculation
- +10 points per completed trade
- -5 points per cancelled trade (after acceptance)
- -50 points per violation
- Bonus points for highly-rated trades (future)

## Account Security

### Security Features
- Password hashing with bcrypt
- Rate limiting on login attempts
- Account lockout after failed attempts
- Password reset via email
- Two-factor authentication (future)

### Privacy Controls
- Control vault visibility (public/private)
- Block users from trading
- Hide online status (future)

## Related Documents

- [[Security]] - Security implementation details
- [[API Design]] - User and auth endpoints
- [[Data Model]] - User entity structure
