---
description: Design a new feature with architecture and implementation plan
argument-hint: [feature-name]
---

Design the following feature: $1

Provide a comprehensive design including:

## 1. Architecture Overview
- High-level component design
- System boundaries and responsibilities
- Data flow diagram

## 2. Component Design
- Core components and their responsibilities
- Component interactions and dependencies
- Interface definitions

## 3. Database Schema Changes
- New tables or collections needed
- Schema modifications to existing tables
- Indexes required for performance
- Migration strategy

## 4. API Endpoints Specification
- Endpoint paths and HTTP methods
- Request/response schemas
- Authentication/authorization requirements
- Rate limiting considerations

## 5. Integration Points
- External services to integrate with
- Internal services/modules affected
- Message queues or event streams
- Third-party APIs

## 6. Error Handling Strategy
- Expected error scenarios
- Error codes and messages
- Retry logic and circuit breakers
- Fallback mechanisms

## 7. Performance Considerations
- Expected load and throughput
- Caching strategy
- Database query optimization
- Async processing needs

## 8. Testing Strategy
- Unit test coverage plan
- Integration test scenarios
- Performance test requirements
- Contract testing needs

## 9. Security Considerations
- Authentication and authorization
- Input validation requirements
- Data encryption needs
- Security vulnerabilities to prevent

## 10. Deployment Plan
- Rollout strategy
- Feature flags needed
- Backward compatibility
- Rollback plan
