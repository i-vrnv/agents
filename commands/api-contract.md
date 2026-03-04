---
description: Validate API contract changes for breaking changes and compatibility
argument-hint: [endpoint-name]
allowed-tools: Bash(git diff:*), Grep, Read, Glob
---

# API Contract Validation for: $1

Validate the API contract changes and ensure backward compatibility.

## Analysis Steps

### 1. Schema Changes Detection
- Check OpenAPI/Swagger specification changes
- Review protocol buffer (proto) definitions
- Identify JSON schema modifications
- Review GraphQL schema changes

### 2. Breaking Changes Analysis
Identify potential breaking changes:
- Removed or renamed fields
- Changed field types
- Modified required/optional field status
- Removed endpoints
- Changed HTTP methods
- Modified authentication requirements
- Changed error response formats

### 3. Request/Response Validation
- Request payload structure changes
- Response payload structure changes
- New required parameters
- Modified validation rules
- Changed default values

### 4. Versioning Assessment
- Is API versioning needed?
- Version header or path-based versioning?
- Deprecation notices required?
- Sunset timeline for old versions

### 5. Backward Compatibility Check
- Will existing clients break?
- Can old clients use new API?
- Graceful degradation strategy
- Migration path for clients

### 6. Documentation Review
- API documentation updated?
- Request/response examples accurate?
- Error codes documented?
- Rate limits documented?
- Authentication flow documented?

### 7. Contract Testing Requirements
- Consumer-driven contract tests needed?
- Integration test coverage
- API mock servers updated?

## Output Format

Provide:
1. **Summary**: Brief overview of changes
2. **Breaking Changes**: List with severity (CRITICAL/HIGH/MEDIUM/LOW)
3. **Migration Guide**: Steps for API consumers to update
4. **Recommendations**: Versioning strategy and rollout plan
5. **Action Items**: Required tasks before deployment
