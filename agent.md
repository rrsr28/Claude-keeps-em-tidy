# Claude PR Review Rules

## Code Review Rules
- Code should be DRY (Don't Repeat Yourself)
- There should be no secrets or credentials in the code
- Extremely complicated code needs comments
- Use descriptive variable and constant names
- API routes must have error handling, and they shouldn't intentionally return a HTTP 500
- API changes should be backwards compatible
- Use retries when calling external API services
- Don't log sensitive data
- Function and method naming should follow consistent patterns
- Ensure proper exception handling and avoid bare `except` clauses
- Use type hints for functions
- Write unit tests for all new functions/methods
- Keep functions short (under 50 lines if possible)
- Use meaningful commit messages (explain the **why**)
- Validate and sanitize all user input
- Use async programming where appropriate
- Follow PEP 8 (Python style)
- Update dependencies regularly and address security vulnerabilities
- Implement auth and authorization correctly
- Handle errors gracefully without exposing sensitive data
- Use secure random number generators for cryptography
- API endpoints should use Pydantic models for input and output

## Summary Risk Classification Guidelines
- Risk classification: Low or High
- Justify classification based on PR contents (e.g., Risk classification: Low. Reason: Only documentation changes.)

### Examples
**Low Risk:**
- Minor UI tweaks
- Documentation updates
- Typo fixes
- Small perf optimizations

**High Risk:**
- DB schema changes
- Auth system modifications
- New API endpoints
- Major refactoring of core logic
