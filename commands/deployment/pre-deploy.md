---
description: Run comprehensive pre-deployment validation checks
allowed-tools: Bash(git status:*), Bash(git log:*), Bash(git diff:*), Bash(mvn:*), Bash(go:*), Bash(python:*), Bash(pytest:*), Read, Grep, Glob
---

# Pre-Deployment Validation Checklist

Run comprehensive checks before deployment to production.

## 1. Build Validation
- [ ] Code compiles successfully
- [ ] No build warnings or errors
- [ ] Dependencies are up to date and compatible
- [ ] Build artifacts generated correctly

**Commands to run:**
- Java: `mvn clean package` or `./gradlew build`
- Go: `go build ./...` and `go vet ./...`
- Python: `python -m py_compile` or build check

## 2. Test Execution
- [ ] All unit tests passing
- [ ] All integration tests passing
- [ ] End-to-end tests passing
- [ ] No flaky tests
- [ ] Test coverage meets threshold

**Commands to run:**
- Java: `mvn test` and `mvn verify`
- Go: `go test ./... -v -race`
- Python: `pytest` with coverage

## 3. Code Quality
- [ ] No uncommitted changes
- [ ] Code follows style guidelines
- [ ] Linting passes
- [ ] Static analysis clean
- [ ] No security vulnerabilities detected

**Commands to run:**
- Git: `git status`
- Go: `golangci-lint run`
- Java: `mvn checkstyle:check` or `./gradlew check`
- Python: `pylint` and `mypy`

## 4. Database Migrations
- [ ] Migration scripts validated
- [ ] Rollback scripts tested
- [ ] Migration tested on staging
- [ ] Data integrity verified
- [ ] Performance impact assessed

## 5. Configuration Review
- [ ] Environment variables configured
- [ ] Configuration files updated
- [ ] Secrets properly managed (not in code)
- [ ] Feature flags configured correctly
- [ ] Rate limits and timeouts set appropriately

## 6. API Contract Validation
- [ ] No breaking API changes (or properly versioned)
- [ ] API documentation updated
- [ ] Contract tests passing
- [ ] Backward compatibility verified

## 7. Performance Benchmarks
- [ ] Performance tests run
- [ ] Response times acceptable
- [ ] Resource usage within limits
- [ ] Load test results acceptable
- [ ] No performance regressions

## 8. Security Review
- [ ] Security scan completed
- [ ] No new vulnerabilities introduced
- [ ] Authentication/authorization verified
- [ ] Input validation complete
- [ ] Dependency vulnerabilities checked

## 9. Documentation
- [ ] README updated
- [ ] API documentation current
- [ ] Changelog updated
- [ ] Deployment runbook updated
- [ ] Architecture diagrams current

## 10. Deployment Preparation
- [ ] Deployment plan documented
- [ ] Rollback plan prepared
- [ ] Monitoring alerts configured
- [ ] Team notified of deployment
- [ ] Deployment window scheduled

## 11. Version Management
- [ ] Version number incremented
- [ ] Git tags created
- [ ] Release notes prepared
- [ ] CHANGELOG.md updated

## 12. Monitoring & Observability
- [ ] Logging configured
- [ ] Metrics endpoints working
- [ ] Health check endpoints ready
- [ ] Distributed tracing enabled
- [ ] Alert thresholds configured

---

## Execution Instructions

1. Run build and test commands for your stack
2. Verify git status shows clean working directory
3. Check recent commits: `git log --oneline -10`
4. Review changes since last deploy: `git diff origin/main...HEAD`
5. Verify all checklist items above
6. Report any failures or concerns before proceeding

## Output Format

Provide:
- **Status**: READY / NOT READY / BLOCKED
- **Passed Checks**: List of successful validations
- **Failed Checks**: List of failures with details
- **Warnings**: Non-blocking issues to be aware of
- **Next Steps**: Actions required before deployment
