# DEPENDENCY_UPDATES_HELPER.md
## Self-Deploying Package Update & Cataloguing System

---

# 🚀 PART 1: DEPLOYMENT INSTRUCTIONS

> **AI AGENT**: Execute these steps to deploy the dependency management system.

## Step 1: Initial Analysis
Before starting updates, gather baseline information:

```bash
# For Node.js projects
npm outdated --json > npm-outdated-initial.json
npm ls --depth=0 --json > npm-list-initial.json
npm audit --json > npm-audit-initial.json

# For Python projects
pip list --outdated --format=json > pip-outdated-initial.json
pip freeze > requirements-initial.txt

# For Ruby projects
bundle outdated --parseable > bundle-outdated-initial.txt

# Save initial state for rollback if needed
cp package.json package.json.backup
cp package-lock.json package-lock.json.backup
```

## Step 2: Create DEPENDENCY_CATALOGUE.md
Copy the template from Part 2 below into a new file called `DEPENDENCY_CATALOGUE.md` in the project root.

## Step 3: Systematic Package Updates

### Update Process for Each Package:
1. **Check current version** vs latest stable
2. **Read changelog** for breaking changes
3. **Update individually** to isolate issues
4. **Run tests** after each update
5. **Document results** in the catalogue

### Node.js Update Sequence:
```bash
# For each package from npm outdated
npm install [package]@latest --save-exact

# Test after each update
npm test

# If tests fail, check for specific version
npm view [package] versions --json
npm install [package]@[last-stable-version]

# Document in DEPENDENCY_CATALOGUE.md
```

## Step 4: Document Everything

For each package update, record:
- Previous version → New version
- Update status (✅ Success | ⚠️ Warning | ❌ Failed)
- Breaking changes noted
- New features available
- Deprecated features
- Test results
- Rollback instructions if needed

## Step 5: Update Other Documentation

### Add to INDEX.md:
```markdown
| DEPENDENCY_CATALOGUE.md | Package Version Tracking | ✅ Complete | All Agents | [Today's Date] |
```

### Add to DEVELOPMENT_LOG.md:
```markdown
### [LINE#] | [DATE] [TIME] | CODES: DEPS, MAINT
**Summary**: Monthly dependency update and catalogue creation
**Duration**: [Time taken]
**Impact**: Files: package.json, package-lock.json | Packages Updated: X/Y

#### Changes
- Updated X packages to latest stable versions
- Identified Y packages with breaking changes
- Documented Z deprecation warnings

#### Issues Resolved
- [Security vulnerability] in [package] → Updated to [version]

#### Discovered
- [Package] has breaking changes in v[X], staying on v[Y]
- [Package] deprecates [function] in favor of [new function]

#### TODO Generated
- [ ] Refactor code using deprecated [function] from [package]
- [ ] Plan migration to [package] v[X] (breaking changes)
```

## Step 6: Update Agent Instructions

### Modify AGENTS.md
Add this section after "Active Task Registry":

```markdown
## 📦 Package Management

**IMPORTANT**: Before troubleshooting package-related errors, consult DEPENDENCY_CATALOGUE.md for:
- Current package versions and capabilities
- Known conflicts and workarounds
- Deprecated functions to avoid
- Update history and rollback procedures

When encountering package errors:
1. Check DEPENDENCY_CATALOGUE.md first
2. Verify package version matches catalogue
3. Review documented warnings/issues
4. Consider if error relates to recent updates
```

### Modify INDEX.md
Add to the "Known Issues & Technical Debt" section:

```markdown
### Package Version Constraints
See DEPENDENCY_CATALOGUE.md for:
- Packages held at specific versions
- Reasons for version locks
- Planned upgrade paths
- Monthly update schedule (Next: [Date])
```

## Step 7: Move Helper to DOCS
```bash
# Create DOCS folder if needed
mkdir -p DOCS

# Move this helper file
mv DEPENDENCY_UPDATES_HELPER.md DOCS/

# Update INDEX.md reference
```

## Step 8: Set Up Monthly Schedule
Add to DEPENDENCY_CATALOGUE.md header:
```markdown
⏰ **Update Schedule**: Monthly (Day [X] of each month)
📅 **Last Update**: [Today's Date]
📅 **Next Update Due**: [Date + 30 days]
```

## Step 9: Verification Checklist
- [ ] All packages analyzed and documented
- [ ] DEPENDENCY_CATALOGUE.md created with complete data
- [ ] Tests pass after updates
- [ ] Breaking changes documented
- [ ] AGENTS.md updated with package reference
- [ ] INDEX.md updated with catalogue entry
- [ ] DEVELOPMENT_LOG.md entry created
- [ ] Helper file moved to DOCS/
- [ ] Backup files created for rollback

---

# 📋 PART 2: DEPENDENCY_CATALOGUE.md TEMPLATE

> **Copy everything below this line into DEPENDENCY_CATALOGUE.md**

---

# DEPENDENCY_CATALOGUE.md
## Package Version Management & Update History

> **🔍 Quick Reference**: Check here FIRST when encountering package-related errors or warnings.

---

## 📅 Maintenance Schedule

```yaml
Update Frequency: Monthly
Last Update: [DATE]
Next Update Due: [DATE + 30 days]
Last Updated By: [Agent/Developer Name]
Total Packages: [COUNT]
Up-to-date: [COUNT]
Outdated: [COUNT]
Locked Versions: [COUNT]
```

---

## 🚨 Critical Information

### ⚠️ Packages with Version Locks
These packages MUST NOT be updated without careful testing:

| Package | Locked Version | Latest Version | Reason for Lock | Unlock Plan |
|---------|---------------|----------------|-----------------|-------------|
| [PLACEHOLDER] | [X.Y.Z] | [A.B.C] | Breaking changes in [feature] | Refactor [module] first |

### 🔴 Known Conflicts
Packages that conflict when updated together:

| Package A | Version | Package B | Version | Conflict Description | Resolution |
|-----------|---------|-----------|---------|---------------------|------------|
| [PLACEHOLDER] | [version] | [PLACEHOLDER] | [version] | [Description] | [How to resolve] |

---

## 📦 Complete Package Registry

### Production Dependencies

| Package | Current | Latest Stable | Status | Last Updated | Notes |
|---------|---------|---------------|--------|--------------|-------|
| [PLACEHOLDER] | [X.Y.Z] | [X.Y.Z] | ✅ Current | [DATE] | [Notes] |
| [PLACEHOLDER] | [X.Y.Z] | [A.B.C] | ⚠️ Behind | [DATE] | Breaking changes in v[A] |
| [PLACEHOLDER] | [X.Y.Z] | [X.Y.Z] | 🔒 Locked | [DATE] | See version locks above |

### Development Dependencies

| Package | Current | Latest Stable | Status | Last Updated | Notes |
|---------|---------|---------------|--------|--------------|-------|
| [PLACEHOLDER] | [X.Y.Z] | [X.Y.Z] | ✅ Current | [DATE] | [Notes] |

### Optional Dependencies

| Package | Current | Latest Stable | Status | Purpose | Can Remove? |
|---------|---------|---------------|--------|---------|-------------|
| [PLACEHOLDER] | [X.Y.Z] | [X.Y.Z] | [Status] | [Why needed] | Yes/No |

---

## 📊 Update History

### [DATE] Update Session

#### Successfully Updated
| Package | From Version | To Version | Test Result | Performance Impact |
|---------|--------------|------------|-------------|-------------------|
| [PLACEHOLDER] | [X.Y.Z] | [A.B.C] | ✅ Pass | None observed |

#### Failed Updates (Rolled Back)
| Package | Attempted Version | Error | Rollback Version | Fix Required |
|---------|------------------|-------|------------------|--------------|
| [PLACEHOLDER] | [X.Y.Z] | [Error description] | [X.Y.Z] | [What needs fixing] |

#### Skipped Updates
| Package | Current | Available | Reason for Skipping | Revisit Date |
|---------|---------|-----------|---------------------|--------------|
| [PLACEHOLDER] | [X.Y.Z] | [A.B.C] | [Reason] | [DATE] |

---

## 🔄 Breaking Changes Tracker

### Recent Breaking Changes (Last 90 Days)

| Package | Version | Breaking Change | Migration Guide | Impact on Our Code |
|---------|---------|----------------|-----------------|-------------------|
| [PLACEHOLDER] | [X.0.0] | [Description] | [Link or steps] | [Files affected] |

### Upcoming Breaking Changes (Next 90 Days)

| Package | Target Version | Deprecation Warning | Required Action | Deadline |
|---------|---------------|--------------------|--------------------|----------|
| [PLACEHOLDER] | [X.0.0] | [Warning text] | [What to do] | [DATE] |

---

## 🆕 New Features Available

### Features in Updated Packages

| Package | Version | New Feature | Benefit | Implementation Priority |
|---------|---------|-------------|---------|------------------------|
| [PLACEHOLDER] | [X.Y.Z] | [Feature] | [Why useful] | High/Medium/Low |

### Features Requiring Updates

| Package | Required Version | Feature | Current Blocker | Unblock Plan |
|---------|-----------------|---------|-----------------|--------------|
| [PLACEHOLDER] | [X.Y.Z] | [Feature] | [What blocks update] | [How to unblock] |

---

## ⚰️ Deprecated Functions & Features

### Currently Using Deprecated Features

| Package | Deprecated Item | Used In Files | Replacement | Migration Deadline |
|---------|----------------|---------------|-------------|-------------------|
| [PLACEHOLDER] | [Function/Feature] | [File list] | [New approach] | [DATE or version] |

### Successfully Migrated (Last 30 Days)

| Package | Old Feature | New Feature | Migration Date | Files Changed |
|---------|-------------|-------------|----------------|---------------|
| [PLACEHOLDER] | [Old] | [New] | [DATE] | [Count] files |

---

## 🔒 Security Audit Results

### Current Vulnerabilities

| Severity | Package | Version | Vulnerability | Fix Available | Action Required |
|----------|---------|---------|---------------|---------------|-----------------|
| 🔴 Critical | [PLACEHOLDER] | [X.Y.Z] | [CVE-ID] | Yes - [version] | Update immediately |
| 🟡 Moderate | [PLACEHOLDER] | [X.Y.Z] | [CVE-ID] | No | Monitor for fix |
| 🟢 Low | [PLACEHOLDER] | [X.Y.Z] | [CVE-ID] | Yes - [version] | Schedule update |

### Security Updates Applied

| Package | Vulnerability | Fixed Version | Update Date | Verified |
|---------|--------------|---------------|-------------|----------|
| [PLACEHOLDER] | [CVE-ID] | [X.Y.Z] | [DATE] | ✅ |

---

## ⚠️ Warnings & Notices

### Peer Dependency Warnings

| Package | Warning | Current State | Resolution | Priority |
|---------|---------|---------------|------------|----------|
| [PLACEHOLDER] | [Warning text] | [State] | [How to fix] | [High/Med/Low] |

### Deprecation Warnings

| Source | Warning Message | First Seen | Action Required | Deadline |
|--------|----------------|------------|-----------------|----------|
| [PLACEHOLDER] | [Message] | [DATE] | [Action] | [DATE] |

### Build Warnings

| Package | Warning | Impact | Fix Available | Notes |
|---------|---------|--------|---------------|-------|
| [PLACEHOLDER] | [Warning] | [Impact] | Yes/No | [Notes] |

---

## 📈 Performance Metrics

### Bundle Size Impact

| Package | Version | Size | Change from Previous | Alternatives |
|---------|---------|------|---------------------|--------------|
| [PLACEHOLDER] | [X.Y.Z] | [XX KB] | +[X] KB | [Alternative package] |

### Build Time Impact

| Metric | Before Updates | After Updates | Change | Acceptable? |
|--------|---------------|---------------|--------|-------------|
| Dev Build | [X]s | [Y]s | +[Z]s | Yes/No |
| Prod Build | [X]s | [Y]s | +[Z]s | Yes/No |
| Test Suite | [X]s | [Y]s | +[Z]s | Yes/No |

---

## 🔧 Rollback Procedures

### Quick Rollback Commands

```bash
# Full rollback to pre-update state
cp package.json.backup package.json
cp package-lock.json.backup package-lock.json
npm ci

# Selective rollback of specific package
npm install [package]@[previous-version] --save-exact

# Verify rollback
npm test
npm run build
```

### Rollback History

| Date | Reason | Packages Rolled Back | From Version | To Version |
|------|--------|---------------------|--------------|------------|
| [PLACEHOLDER] | [Reason] | [Package list] | [Versions] | [Versions] |

---

## 📝 Update Procedures

### Monthly Update Checklist

> **For agents performing monthly updates:**

1. **Pre-Update**
   - [ ] Create backups of package files
   - [ ] Run full test suite - document baseline
   - [ ] Check CI/CD status - all green
   - [ ] Review last month's issues

2. **Update Process**
   - [ ] Run `npm outdated` and document
   - [ ] Check each package's changelog
   - [ ] Update dev dependencies first
   - [ ] Update prod dependencies one by one
   - [ ] Test after each update
   - [ ] Document all changes

3. **Post-Update**
   - [ ] Run security audit
   - [ ] Check bundle size changes
   - [ ] Verify build times acceptable
   - [ ] Update this catalogue
   - [ ] Update DEVELOPMENT_LOG.md
   - [ ] Commit with detailed message

4. **Communication**
   - [ ] Note breaking changes in team channel
   - [ ] Update INDEX.md if needed
   - [ ] Flag any required refactoring

### Update Commands Reference

```bash
# Node.js / npm
npm outdated                      # List outdated packages
npm update                        # Update to latest minor/patch
npm install [pkg]@latest         # Update specific package
npm audit                        # Security audit
npm audit fix                    # Auto-fix vulnerabilities

# Python / pip
pip list --outdated              # List outdated packages
pip install --upgrade [pkg]      # Update specific package
pip-review --auto                # Update all packages

# Ruby / Bundler
bundle outdated                  # List outdated gems
bundle update [gem]              # Update specific gem
bundle update                    # Update all gems

# Check for breaking changes
npm view [package] versions      # List all versions
npm view [package] changelog     # View changelog (if available)
```

---

## 🎯 Package-Specific Notes

### [Package Name: PLACEHOLDER]
```yaml
Current Version: [X.Y.Z]
Update Strategy: [Conservative/Aggressive]
Test Coverage: [Areas to test when updating]
Known Issues: [List any known problems]
Documentation: [Link to docs]
Our Usage: [How we use this package]
Dependencies: [Other packages that depend on this]
```

[Repeat for each critical package]

---

## 🔄 Integration with CI/CD

### Automated Checks

| Check | Tool | Configuration | Last Run | Status |
|-------|------|---------------|----------|--------|
| Dependency Audit | npm audit | .github/workflows/audit.yml | [DATE] | ✅ |
| License Check | license-checker | package.json script | [DATE] | ✅ |
| Bundle Size | size-limit | .size-limit.json | [DATE] | ⚠️ |

### Update Notifications

- **Dependabot**: Configured for [security/all] updates
- **Renovate**: [Enabled/Disabled] - Config at renovate.json
- **Manual Review**: Required for major version updates

---

## 📊 Statistics

### Package Health Metrics

| Metric | Value | Target | Status |
|--------|-------|--------|--------|
| Total Dependencies | [X] | <[Y] | ✅/⚠️/❌ |
| Outdated Packages | [X] | <[Y] | ✅/⚠️/❌ |
| Security Vulnerabilities | [X] | 0 | ✅/⚠️/❌ |
| Deprecated Packages | [X] | 0 | ✅/⚠️/❌ |
| Average Age (days) | [X] | <[Y] | ✅/⚠️/❌ |

### Update Velocity

| Period | Updates Applied | Rolled Back | Success Rate |
|--------|----------------|-------------|--------------|
| This Month | [X] | [Y] | [Z]% |
| Last Month | [X] | [Y] | [Z]% |
| Quarter | [X] | [Y] | [Z]% |

---

## 🚨 Emergency Procedures

### If Build Breaks After Update

1. **Immediate Actions**
   ```bash
   # Rollback to backups
   cp package.json.backup package.json
   cp package-lock.json.backup package-lock.json
   npm ci
   ```

2. **Investigation**
   - Check error messages
   - Review package changelog
   - Search for known issues
   - Check GitHub issues

3. **Resolution**
   - Try intermediate versions
   - Apply patches if available
   - Document in this catalogue
   - Update version lock if needed

### Common Issues & Solutions

| Issue | Symptoms | Likely Cause | Solution |
|-------|----------|--------------|----------|
| Build fails | Error during build | Breaking change | Check changelog, adjust code |
| Tests fail | Test suite errors | API changes | Update test expectations |
| Runtime error | App crashes | Missing dependency | Check peer dependencies |
| Type errors | TypeScript complaints | Type definition changes | Update type imports |

---

## 📚 Resources

### Package Documentation
- [NPM Registry](https://www.npmjs.com/)
- [Package Changelog Finder](https://github.com/[package]/releases)
- [Security Advisories](https://github.com/advisories)
- [Bundle Phobia](https://bundlephobia.com/) - Check package sizes

### Best Practices
- [Semantic Versioning](https://semver.org/)
- [NPM Security Best Practices](https://docs.npmjs.com/security)
- [Dependency Management Guide](https://docs.npmjs.com/cli/v8/using-npm/dependency-management)

---

## 🤖 Agent Instructions

### When Referencing This Catalogue

1. **For Package Errors**: Check current version and known issues first
2. **For Updates**: Review breaking changes and migration guides
3. **For Planning**: Consider upcoming deprecations and required actions
4. **For Debugging**: Check if issue relates to recent updates
5. **For Security**: Prioritize critical vulnerability fixes

### Maintenance Responsibilities

**Monthly Tasks**:
- Update all packages following the checklist
- Document all changes thoroughly
- Run security audits
- Update performance metrics
- Archive old update history (>6 months)

**Weekly Tasks**:
- Check for critical security updates
- Monitor deprecation warnings
- Review automated PR from bots

**Daily Awareness**:
- Note any package-related errors
- Track performance changes
- Document unusual behavior

---

**Catalogue Version**: 1.0.0  
**Schema Version**: 2024.12  
**Last Structure Update**: [DATE]  
**Next Review**: [DATE + 30 days]  

---

### 📝 Remember: This catalogue is the source of truth for all package versions. Always consult before troubleshooting package issues!