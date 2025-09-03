# DEPENDENCY_PRE-SETUP.md
## One-Time Setup for Dependency Management System

> **🤖 AI AGENT**: This is a ONE-TIME setup file. Execute these modifications, then delete this file.

---

## 🎯 Purpose

This file prepares your existing documentation for the dependency management system by adding the necessary sections to AGENTS.md, INDEX.md, and DEVELOPMENT_LOG.md. Once complete, this file should be deleted (not archived) and the main DEPENDENCY_UPDATES_HELPER.md should be run.

---

## ✅ Pre-Setup Checklist

Before starting, verify these files exist:
- [ ] AGENTS.md (in project root)
- [ ] INDEX.md (in project root)
- [ ] DEVELOPMENT_LOG.md (in project root)
- [ ] DEPENDENCY_UPDATES_HELPER.md (ready to run after this setup)

---

## 📝 STEP 1: Modify AGENTS.md

### Location: After the "Active Task Registry" section
### Action: ADD the following section

```markdown
## 📦 Package Management Protocol

**CRITICAL**: Before troubleshooting any package-related errors, warnings, or incorrect tool usage:

1. **FIRST** - Check DEPENDENCY_CATALOGUE.md for:
   - Current installed version vs latest available
   - Known conflicts with other packages  
   - Deprecated functions or methods
   - Version-specific capabilities and limitations
   - Recent update history that might explain new behavior

2. **When encountering package errors**:
   - Verify error against documented warnings in catalogue
   - Check if package is locked at specific version (and why)
   - Review breaking changes if recently updated
   - Consider rollback procedures if critical

3. **Before suggesting package updates**:
   - Consult the version lock list
   - Review documented conflicts
   - Check the last update date (monthly cycle)
   - Verify no breaking changes affect current code

**Monthly Maintenance**: Check if today is within 5 days of the monthly update date. If yes, remind user that package updates are due.
```

### Verification
- [ ] Section added after "Active Task Registry"
- [ ] No duplicate sections created
- [ ] Formatting preserved

---

## 📝 STEP 2: Modify INDEX.md

### Part A - Documentation Section
### Location: In the "Documentation" table (usually in lower half of file)
### Action: ADD this row to the table

```markdown
| DEPENDENCY_CATALOGUE.md | Package Version Tracking | ⏳ Pending | All Agents | [Today's Date] |
```

**Note**: Status is "⏳ Pending" because the catalogue doesn't exist yet. It will be created by DEPENDENCY_UPDATES_HELPER.md.

### Part B - Known Issues Section  
### Location: In "Known Issues & Technical Debt" section
### Action: ADD this subsection

```markdown
### Package Version Management
**Reference**: DEPENDENCY_CATALOGUE.md for complete package information

**Version Locks** (Packages held at specific versions):
- See catalogue for full list and reasons
- Next monthly update: [Pending - will be set on first run]

**Known Package Issues**:
- Check catalogue before troubleshooting
- Document new issues in catalogue
- Update after each monthly maintenance
```

### Verification
- [ ] Documentation table row added
- [ ] Known Issues subsection added
- [ ] No formatting broken

---

## 📝 STEP 3: Modify DEVELOPMENT_LOG.md

### Part A - Work Area Code Matrix
### Location: In the "Work Area Code Matrix" table (near top of file)
### Action: ADD these rows to the existing table

```markdown
| DEPS | Dependencies | Package updates, version management | [Today's Date] | [Today's Date] | 0 |
| MAINT | Maintenance | Monthly updates, security patches | [Today's Date] | [Today's Date] | 0 |
```

**Note**: Entry count starts at 0 since no entries exist yet.

### Part B - Quick Reference Index
### Location: In the "Quick Reference Index" section
### Action: ADD these lines alphabetically

```markdown
DEPS:  [Will be populated after first use]
MAINT: [Will be populated after first use]
```

### Part C - Recurring Tasks Registry
### Location: In "Recurring Tasks Registry" section (create if doesn't exist)
### Action: ADD this task template

```markdown
### DEPS - Monthly Package Updates
**Schedule**: Day [TBD] of each month (will be set on first run)
**Reference**: DEPENDENCY_CATALOGUE.md for procedures
1. Check DEPENDENCY_CATALOGUE.md for next update date
2. Follow "Monthly Update Checklist" in catalogue
3. Run: `npm outdated` → update systematically
4. Test after each update
5. Document all changes in catalogue
6. Update INDEX.md and create log entry
**Time Required**: 2-4 hours typically
**Last Completed**: [Pending]
**Next Due**: [To be determined on first run]
```

### Verification
- [ ] Code matrix rows added
- [ ] Quick Reference Index updated
- [ ] Recurring task added
- [ ] No duplicate entries

---

## 🔄 STEP 4: Create Pre-Setup Log Entry

### Location: Add new entry at the top of DEVELOPMENT_LOG.md entries
### Action: CREATE this entry

```markdown
---
### [LINE#] | [Current Date/Time] | CODES: SETUP, DEPS
**Summary**: Prepared documentation for dependency management system
**Duration**: 15 minutes
**Impact**: Files: 3 modified | Tests: N/A | Coverage: N/A

#### Changes
- Modified AGENTS.md to include Package Management Protocol
- Updated INDEX.md with dependency catalogue references
- Enhanced DEVELOPMENT_LOG.md with DEPS and MAINT codes
- Added recurring task for monthly package updates

#### Issues Resolved
- Documentation now ready for dependency management system

#### Discovered
- Project ready for DEPENDENCY_UPDATES_HELPER.md execution

#### TODO Generated
- [ ] Run DEPENDENCY_UPDATES_HELPER.md to create catalogue
- [ ] Perform initial package audit and updates
- [ ] Set monthly update schedule date

#### Commit Refs
`[commit hash if applicable]` Prepared docs for dependency management

---
```

### Update Line Index
Add the line number of this new entry to the SETUP and DEPS codes in the Quick Reference Index.

---

## 🗑️ STEP 5: Delete This File

### Action: DELETE DEPENDENCY_PRE-SETUP.md
```bash
# After all modifications are complete and verified
rm DEPENDENCY_PRE-SETUP.md
```

**IMPORTANT**: Do NOT move to DOCS. This is a one-time setup file that should be completely removed.

---

## ✅ Final Verification Checklist

Before deleting this file, confirm:

### AGENTS.md Modifications
- [ ] Package Management Protocol section added
- [ ] Section properly formatted
- [ ] No content accidentally deleted

### INDEX.md Modifications  
- [ ] DEPENDENCY_CATALOGUE.md row added to documentation table
- [ ] Package Version Management subsection added
- [ ] All placeholders updated with actual dates

### DEVELOPMENT_LOG.md Modifications
- [ ] DEPS and MAINT codes added to matrix
- [ ] Quick Reference Index includes new codes
- [ ] Recurring task for monthly updates added
- [ ] Pre-setup log entry created
- [ ] Line numbers updated in index

### General
- [ ] All files saved
- [ ] No formatting errors introduced
- [ ] Backup created (if desired)
- [ ] Ready to run DEPENDENCY_UPDATES_HELPER.md

---

## 🚀 Next Steps

After completing all modifications and deleting this file:

### Instruct the user:
```markdown
✅ **Pre-Setup Complete!**

All existing documentation has been updated to support the dependency management system.

**Next Action Required**: 
Please run the following command to start the main dependency cataloguing process:

"Please execute DEPENDENCY_UPDATES_HELPER.md to create the dependency catalogue and perform the initial package audit."

This will:
1. Create DEPENDENCY_CATALOGUE.md
2. Analyze all current packages
3. Perform initial updates
4. Document the complete package landscape
5. Set up the monthly update schedule

Estimated time: 1-2 hours for initial setup
```

---

## ⚠️ Troubleshooting

### If a file doesn't exist:
- Create it from its template first
- Then apply these modifications

### If sections already exist:
- Don't duplicate - merge the content
- Keep the most comprehensive version

### If unsure about placement:
- Look for similar sections
- Maintain alphabetical or logical ordering
- Preserve existing formatting style

---

## 🎯 Success Criteria

You've succeeded when:
1. ✅ All three files modified correctly
2. ✅ No duplicate sections created
3. ✅ All placeholders filled with actual data
4. ✅ This file deleted (not archived)
5. ✅ User instructed to run main helper

---

**File Version**: 1.0.0  
**Purpose**: One-time setup only  
**Created**: [Current Date]  
**Delete After**: Successful completion  

---

### 🤖 Remember: This is a ONE-TIME setup. Delete this file after use!