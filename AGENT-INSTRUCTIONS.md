# AGENT-INSTRUCTIONS.md
## Self-Deploying AI Agent System with Task Prioritization

---

# 🚀 PART 1: DEPLOYMENT INSTRUCTIONS

> **AI AGENT**: Execute these steps to deploy the agent instruction system.

## Step 1: Create AGENTS.md
Copy the complete template from Part 2 below into a new file called `AGENTS.md` in the project root.

## Step 2: Analyze Current Project State
Before deployment, review:
- **INDEX.md** - Check all in-progress items (🚧 status)
- **DEVELOPMENT_LOG.md** - Review recent entries and pending TODOs
- **Test results** - Verify nothing is currently broken
- **Git status** - Check for uncommitted changes

## Step 3: Initialize Task Registry
In the new AGENTS.md, populate the "Active Task Registry" section with:
- All 🚧 (in-progress) items from INDEX.md
- All ⏳ (pending) items marked as high priority
- Any TODO items from recent DEVELOPMENT_LOG.md entries

## Step 4: Configure Agent Personality
Based on the project type, adjust the "Agent Configuration" section in AGENTS.md:
- Set appropriate caution levels (startup = high, mature = moderate)
- Define code review strictness
- Set testing requirements

## Step 5: Move Original to DOCS
```bash
# Create DOCS folder if needed
mkdir -p DOCS

# Move this instruction file
mv AGENT-INSTRUCTIONS.md DOCS/

# Update any references in INDEX.md
```

## Step 6: Create Kiro Steering Doc
**IMPORTANT - User Action Required:**
1. Copy the entire contents of the newly created AGENTS.md
2. In Kiro, click the **+** button next to "Steering Docs"
3. Enter **"AGENTS"** as the name
4. Paste the copied AGENTS.md contents into the new steering doc
5. Save the steering doc

This ensures all agents have access to the same instructions regardless of the interface used.

## Step 7: Update INDEX.md
Add this to the Documentation section of INDEX.md:
```markdown
| AGENTS.md | AI Agent Instructions | ✅ Complete | AI Agents | [Today's Date] |
| /DOCS/AGENT-INSTRUCTIONS.md | Original Template | ✅ Archived | Reference | [Today's Date] |
```

## Step 8: Verification Checklist
- [ ] AGENTS.md exists in project root
- [ ] Active Task Registry is populated
- [ ] Agent Configuration matches project needs
- [ ] Original AGENT-INSTRUCTIONS.md moved to DOCS/
- [ ] INDEX.md updated with new documentation entries
- [ ] Kiro Steering Doc "AGENTS" created (user confirms)
- [ ] All in-progress work is documented

---

# 📋 PART 2: AGENTS.md TEMPLATE

> **Copy everything below this line into AGENTS.md**

---

# AGENTS.md
## AI Agent Universal Instructions & Task Management System

> **🤖 AGENT**: This is your primary instruction set. Read this BEFORE starting any work.

---

## 🎯 Prime Directives

1. **Check Before Starting** - Always verify task priority and dependencies
2. **Complete Before Moving** - Finish current tasks before starting new ones
3. **Test Everything** - No code is complete without tests
4. **Document Always** - Update INDEX.md and DEVELOPMENT_LOG.md continuously
5. **Communicate Concerns** - If something seems wrong, say so

---

## 📋 Active Task Registry

> **CRITICAL**: Check this BEFORE accepting new work

### 🚧 Currently In Progress
| Task | Status | Blocking | Started | Developer | Next Step |
|------|--------|----------|---------|-----------|-----------|
| [PLACEHOLDER] | 50% | None | [Date] | [Agent] | [Specific action] |

### ⏳ Pending High Priority
| Task | Depends On | Estimated Effort | Deadline | Assigned |
|------|------------|------------------|----------|----------|
| [PLACEHOLDER] | [Task ID] | [Hours] | [Date] | [Agent] |

### 📝 Backlog (Lower Priority)
| Task | Reason Delayed | Can Start When | Impact if Delayed |
|------|----------------|----------------|-------------------|
| [PLACEHOLDER] | [Reason] | [Condition] | [Impact] |

---

## 🔄 Task Management Protocol

### When Receiving a New Task Request

#### Step 1: Check Task Registry
```yaml
IF task exists in DEVELOPMENT_LOG.md:
  → Continue with existing task
ELSE:
  → Proceed to Step 2
```

#### Step 2: Analyze Impact
Review and communicate:
1. **Check in-progress tasks** (🚧 status in INDEX.md)
2. **Identify dependencies** that might break
3. **Assess completion order** for optimal flow

#### Step 3: Present Options to User
```markdown
🤖 **Task Analysis Complete**

**New Task**: [User's request]

**Currently In Progress**:
- Task A: 70% complete, 2 hours to finish
- Task B: 30% complete, may conflict with new request

**Recommendation**: Complete Task A first because:
- [Reason 1: Prevents dependency issues]
- [Reason 2: More efficient build order]

**Options**:
1. ✅ **Recommended**: Finish Task A first, then start new task
2. ⏳ **Queue**: Add new task to backlog, continue current work
3. 🔄 **Switch**: Pause current work, start new task (not recommended)

Please confirm your preference.
```

#### Step 4: Handle User Response

**If User Agrees to Wait**:
1. Add task to DEVELOPMENT_LOG.md with:
   ```markdown
   ### [LINE#] | [DATE] [TIME] | CODES: PEND
   **Summary**: [Task description] - QUEUED
   **Status**: ⏳ Waiting
   **Reason**: Waiting for [current task] completion
   **Estimated Start**: [Date/Time]
   **Details**: [Everything needed to resume]
   ```
2. Add to Active Task Registry in "Pending" section
3. Continue with current task

**If User Insists on Immediate Start**:
1. Document current task state for resumption
2. Update status of paused task to ⏳
3. Begin new task with note about potential impacts
4. Add warning to DEVELOPMENT_LOG.md

---

## 🏗️ Development Patterns

### File Creation Protocol
```typescript
/**
 * @filename /src/[module]/[feature].ts
 * @module [ModuleName]
 * @description [Complete description]
 * @author AI Agent - [Model/Platform]
 * @date [Current Date]
 * @status [Draft|Review|Complete]
 * @tests /tests/[module]/[feature].test.ts
 * @dependencies [List all imports]
 * @exports [List all exports]
 * @todos [Any incomplete items]
 */

// Implementation following patterns below...
```

### Standard Implementation Patterns

#### API Endpoint Pattern
```typescript
// /src/api/routes/[resource].routes.ts
import { Router } from 'express';
import { authenticate } from '../../auth/middleware';
import { validate } from '../middleware/validation';
import { [Schema] } from '../schemas/[resource].schema';
import { [Service] } from '../../services/[resource].service';
import { Logger } from '../../utils/logger';
import { asyncHandler } from '../../utils/asyncHandler';

const router = Router();
const logger = new Logger('[Resource]Routes');
const service = new [Service]();

/**
 * GET /api/[resources]
 * @description List all [resources]
 * @access Private
 */
router.get('/', 
  authenticate,
  asyncHandler(async (req, res) => {
    logger.info('Listing [resources]', { userId: req.user.id });
    const result = await service.list(req.query);
    res.json({ success: true, data: result });
  })
);

/**
 * POST /api/[resources]
 * @description Create new [resource]
 * @access Private
 */
router.post('/',
  authenticate,
  validate([Schema]),
  asyncHandler(async (req, res) => {
    logger.info('Creating [resource]', { userId: req.user.id });
    const result = await service.create({
      ...req.body,
      userId: req.user.id
    });
    res.status(201).json({ success: true, data: result });
  })
);

export default router;
```

#### Service Layer Pattern
```typescript
// /src/services/[service].service.ts
import { [Repository] } from '../repositories/[model].repository';
import { CacheService } from './cache.service';
import { Logger } from '../utils/logger';
import type { [Model], Create[Model]Dto } from '../types';

export class [Service]Service {
  private repository: [Repository];
  private cache: CacheService;
  private logger: Logger;
  
  constructor() {
    this.repository = new [Repository]();
    this.cache = new CacheService('[Service]');
    this.logger = new Logger('[Service]Service');
  }
  
  async create(dto: Create[Model]Dto): Promise<[Model]> {
    this.logger.info('Creating [model]', dto);
    
    // Validate business rules
    await this.validateBusinessRules(dto);
    
    // Transform data
    const entity = await this.transformDtoToEntity(dto);
    
    // Persist
    const result = await this.repository.create(entity);
    
    // Clear relevant caches
    await this.cache.invalidate('[Model]List');
    
    // Trigger side effects
    await this.triggerPostCreateActions(result);
    
    this.logger.info('[Model] created', { id: result.id });
    return result;
  }
  
  private async validateBusinessRules(dto: any): Promise<void> {
    // Business validation logic
  }
  
  private async transformDtoToEntity(dto: any): Promise<any> {
    return {
      ...dto,
      createdAt: new Date(),
      updatedAt: new Date()
    };
  }
  
  private async triggerPostCreateActions(entity: any): Promise<void> {
    // Side effects like notifications, analytics, etc.
  }
}
```

#### Repository Pattern
```typescript
// /src/repositories/[model].repository.ts
import { BaseRepository } from './base.repository';
import { db } from '../database/connection';
import { Logger } from '../utils/logger';
import type { [Model], Create[Model]Dto, Update[Model]Dto } from '../types';

export class [Model]Repository extends BaseRepository<[Model]> {
  private logger: Logger;
  
  constructor() {
    super('[models]'); // table/collection name
    this.logger = new Logger('[Model]Repository');
  }
  
  async create(data: Create[Model]Dto): Promise<[Model]> {
    try {
      const result = await db('[models]').insert(data).returning('*');
      return result[0];
    } catch (error) {
      this.logger.error('Create failed', error);
      throw this.handleDatabaseError(error);
    }
  }
  
  async findById(id: string): Promise<[Model] | null> {
    try {
      const result = await db('[models]').where({ id }).first();
      return result || null;
    } catch (error) {
      this.logger.error('Find failed', error);
      throw this.handleDatabaseError(error);
    }
  }
  
  async update(id: string, data: Update[Model]Dto): Promise<[Model]> {
    try {
      const result = await db('[models]')
        .where({ id })
        .update({ ...data, updatedAt: new Date() })
        .returning('*');
      return result[0];
    } catch (error) {
      this.logger.error('Update failed', error);
      throw this.handleDatabaseError(error);
    }
  }
  
  private handleDatabaseError(error: any): Error {
    // Convert DB errors to app errors
    if (error.code === '23505') {
      return new Error('Duplicate entry');
    }
    return error;
  }
}
```

### Testing Requirements

#### Unit Test Pattern
```typescript
// /tests/unit/[module]/[feature].test.ts
import { describe, it, expect, beforeEach, jest } from '@jest/globals';
import { [Class] } from '../../../src/[module]/[feature]';

describe('[Class]', () => {
  let instance: [Class];
  let mockDependency: jest.Mocked<[Dependency]>;
  
  beforeEach(() => {
    mockDependency = {
      method: jest.fn()
    };
    instance = new [Class](mockDependency);
  });
  
  describe('[method]', () => {
    it('should [expected behavior]', async () => {
      // Arrange
      const input = { /* test data */ };
      const expected = { /* expected result */ };
      mockDependency.method.mockResolvedValue(expected);
      
      // Act
      const result = await instance.[method](input);
      
      // Assert
      expect(result).toEqual(expected);
      expect(mockDependency.method).toHaveBeenCalledWith(input);
    });
    
    it('should handle errors gracefully', async () => {
      // Arrange
      const error = new Error('Test error');
      mockDependency.method.mockRejectedValue(error);
      
      // Act & Assert
      await expect(instance.[method]({}))
        .rejects.toThrow('Test error');
    });
  });
});
```

#### Integration Test Pattern
```typescript
// /tests/integration/[feature].test.ts
import request from 'supertest';
import { app } from '../../src/app';
import { db } from '../../src/database/connection';

describe('[Feature] Integration', () => {
  beforeEach(async () => {
    await db.migrate.latest();
    await db.seed.run();
  });
  
  afterEach(async () => {
    await db.migrate.rollback();
  });
  
  describe('POST /api/[resource]', () => {
    it('should create [resource] successfully', async () => {
      const payload = { /* valid data */ };
      
      const response = await request(app)
        .post('/api/[resource]')
        .set('Authorization', 'Bearer [token]')
        .send(payload)
        .expect(201);
      
      expect(response.body.success).toBe(true);
      expect(response.body.data).toMatchObject(payload);
      
      // Verify in database
      const dbRecord = await db('[table]')
        .where({ id: response.body.data.id })
        .first();
      expect(dbRecord).toBeDefined();
    });
  });
});
```

---

## 🚨 Error Handling Standards

### Application Error Class
```typescript
export class AppError extends Error {
  constructor(
    public message: string,
    public statusCode: number = 500,
    public code?: string,
    public details?: any
  ) {
    super(message);
    this.name = 'AppError';
    Error.captureStackTrace(this, this.constructor);
  }
  
  toJSON() {
    return {
      name: this.name,
      message: this.message,
      code: this.code,
      statusCode: this.statusCode,
      ...(process.env.NODE_ENV === 'development' && { 
        details: this.details,
        stack: this.stack 
      })
    };
  }
}
```

### Global Error Handler
```typescript
export const errorHandler = (err: Error, req: Request, res: Response, next: NextFunction) => {
  const logger = new Logger('ErrorHandler');
  
  // Log error
  logger.error('Request failed', {
    error: err,
    request: {
      method: req.method,
      url: req.url,
      body: req.body,
      user: req.user?.id
    }
  });
  
  // Handle known errors
  if (err instanceof AppError) {
    return res.status(err.statusCode).json(err.toJSON());
  }
  
  // Handle validation errors
  if (err.name === 'ValidationError') {
    return res.status(400).json({
      name: 'ValidationError',
      message: 'Validation failed',
      details: err.details
    });
  }
  
  // Default error
  res.status(500).json({
    name: 'InternalServerError',
    message: 'An unexpected error occurred',
    ...(process.env.NODE_ENV === 'development' && { 
      originalError: err.message 
    })
  });
};
```

---

## 🔒 Security Checklist

### For Every Feature
- [ ] **Input Validation** - Validate all inputs at the edge
- [ ] **Authentication** - Verify user identity
- [ ] **Authorization** - Check user permissions
- [ ] **Rate Limiting** - Prevent abuse
- [ ] **Data Sanitization** - Clean all user inputs
- [ ] **SQL Injection Prevention** - Use parameterized queries
- [ ] **XSS Protection** - Escape output
- [ ] **CSRF Protection** - Use tokens for state changes
- [ ] **Sensitive Data** - Never log passwords/tokens
- [ ] **Error Messages** - Don't expose internal details

### Security Code Patterns
```typescript
// Input validation
import { z } from 'zod';

const UserSchema = z.object({
  email: z.string().email(),
  password: z.string().min(8).max(100),
  name: z.string().min(1).max(100).regex(/^[a-zA-Z\s]+$/)
});

// SQL injection prevention
// ❌ BAD
const query = `SELECT * FROM users WHERE id = ${userId}`;

// ✅ GOOD
const query = db('users').where({ id: userId });

// XSS prevention
// ❌ BAD
res.send(`<h1>${userInput}</h1>`);

// ✅ GOOD
import { escape } from 'html-escaper';
res.send(`<h1>${escape(userInput)}</h1>`);
```

---

## 📊 Code Quality Standards

### Metrics to Maintain
| Metric | Target | Critical | Action if Below |
|--------|--------|----------|-----------------|
| Test Coverage | >80% | <60% | Stop and add tests |
| Cyclomatic Complexity | <10 | >15 | Refactor immediately |
| Duplicate Code | <3% | >5% | Extract common functions |
| Documentation | 100% | <80% | Document before proceeding |

### Code Review Checklist
- [ ] Follows project patterns
- [ ] Has appropriate tests
- [ ] Includes error handling
- [ ] Contains logging
- [ ] Updates documentation
- [ ] No sensitive data exposed
- [ ] Performance considered
- [ ] Accessibility maintained

---

## 🔄 Git Workflow

### Branch Naming
```
feature/[task-code]-[brief-description]
bugfix/[issue-number]-[brief-description]
hotfix/[critical-issue]
refactor/[module]-[what]
```

### Commit Message Format
```
[type]([scope]): [subject]

[body - what and why]

[footer - breaking changes, issues closed]
```

Types: feat, fix, docs, style, refactor, test, chore

### Pre-Commit Checklist
- [ ] All tests pass
- [ ] Linting passes
- [ ] Build succeeds
- [ ] Documentation updated
- [ ] INDEX.md current
- [ ] DEVELOPMENT_LOG.md entry added

---

## 🎭 Agent Configuration

### Personality Settings
```yaml
Project Phase: [Startup|Growth|Mature|Maintenance]
Caution Level: [High|Medium|Low]
Verbosity: [Detailed|Balanced|Concise]
Initiative: [Proactive|Balanced|Reactive]
```

### Communication Style
- **Always confirm** understanding of requirements
- **Explain concerns** with evidence
- **Suggest alternatives** when appropriate
- **Admit uncertainty** rather than guess
- **Ask for clarification** when ambiguous

### Decision Making
1. **Gather Context** - Read all relevant docs
2. **Analyze Options** - Consider multiple approaches
3. **Evaluate Trade-offs** - Performance vs maintainability
4. **Communicate Reasoning** - Explain the why
5. **Document Decision** - Update Decision Log in INDEX.md

---

## 📝 Session Management

### Starting a Session
1. Review AGENTS.md (this file)
2. Check INDEX.md Current Status
3. Read recent DEVELOPMENT_LOG.md entries
4. Verify environment is working
5. Check for uncommitted changes
6. Identify session goals

### During the Session
- Update file statuses in real-time
- Commit frequently (every 30-60 min)
- Run tests after each change
- Document decisions as made
- Note any blockers immediately

### Ending a Session
1. Complete DEVELOPMENT_LOG.md entry
2. Update INDEX.md Current Status
3. Commit all changes
4. Run full test suite
5. Document next steps clearly
6. Update Active Task Registry

---

## 🚀 Quick Commands

### Development
```bash
# Start development
npm run dev

# Run tests
npm test
npm run test:watch
npm run test:coverage

# Code quality
npm run lint
npm run lint:fix
npm run format

# Build
npm run build
npm run build:prod
```

### Utility Scripts
```bash
# Check for issues
npm run check:all

# Update dependencies
npm run deps:check
npm run deps:update

# Database
npm run db:migrate
npm run db:seed
npm run db:reset
```

### Debugging
```bash
# Debug mode
NODE_ENV=development DEBUG=* npm run dev

# Inspect mode
node --inspect-brk ./src/index.js

# Memory profiling
node --max-old-space-size=4096 ./src/index.js
```

---

## 🆘 Common Issues & Solutions

### Issue: Circular Dependencies
**Symptom**: Module not found or undefined imports
**Solution**: Use dependency injection or interfaces
```typescript
// ❌ BAD: Direct circular import
import { ServiceB } from './serviceB';
export class ServiceA {
  constructor() {
    this.serviceB = new ServiceB();
  }
}

// ✅ GOOD: Dependency injection
export class ServiceA {
  constructor(private serviceB: IServiceB) {}
}
```

### Issue: Memory Leaks
**Symptom**: Increasing memory usage over time
**Solution**: Clean up resources
```typescript
class Service {
  private intervals: NodeJS.Timeout[] = [];
  
  start() {
    this.intervals.push(setInterval(() => {}, 1000));
  }
  
  stop() {
    this.intervals.forEach(clearInterval);
    this.intervals = [];
  }
}
```

### Issue: Slow Tests
**Symptom**: Test suite takes >5 minutes
**Solution**: Use test doubles and parallel execution
```typescript
// Mock external services
jest.mock('../services/email.service');

// Run tests in parallel
jest --maxWorkers=4
```

---

## 💡 Best Practices

### Code Organization
1. **Single Responsibility** - One class, one purpose
2. **Dependency Injection** - Pass dependencies, don't create
3. **Interface Segregation** - Small, focused interfaces
4. **Composition over Inheritance** - Prefer composition
5. **Early Returns** - Reduce nesting

### Performance
1. **Lazy Loading** - Load only when needed
2. **Caching** - Cache expensive operations
3. **Pagination** - Never return unlimited results
4. **Indexing** - Add database indexes
5. **Connection Pooling** - Reuse connections

### Maintainability
1. **Clear Naming** - Be descriptive
2. **Small Functions** - <50 lines
3. **Comment Why** - Not what
4. **Consistent Style** - Follow conventions
5. **Refactor Regularly** - Keep it clean

---

## 🤝 Working with Humans

### When Humans Join the Session
1. **Provide Context** - Summarize current state
2. **Explain Challenges** - Share any blockers
3. **Suggest Next Steps** - Offer recommendations
4. **Ask Questions** - Clarify ambiguities
5. **Document Handoff** - Update logs thoroughly

### Communication Templates

**Status Update**:
```markdown
📊 Current Status:
- Working on: [Task]
- Progress: [X%]
- Blockers: [None|Describe]
- Next step: [Action]
- ETA: [Time estimate]
```

**Problem Report**:
```markdown
⚠️ Issue Detected:
- What: [Problem description]
- Where: [File/Function]
- Impact: [Who/What affected]
- Proposed solution: [Recommendation]
- Alternative: [Other option]
```

**Decision Request**:
```markdown
🤔 Decision Needed:
- Context: [Background]
- Options:
  1. [Option A] - Pros/Cons
  2. [Option B] - Pros/Cons
- Recommendation: [Your suggestion]
- Deadline: [When needed by]
```

---

## 📚 Learning Resources

### Documentation Priority
1. **Project README** - Overall context
2. **INDEX.md** - Current state
3. **DEVELOPMENT_LOG.md** - Historical context
4. **API Docs** - Interface contracts
5. **Test Files** - Expected behavior

### External Resources
- [Language Documentation]
- [Framework Guides]
- [Best Practices]
- [Security Guidelines]
- [Performance Tips]

---

## 🎯 Success Metrics

### You're Doing Well When:
- ✅ Tests pass on first run
- ✅ No regression bugs
- ✅ Documentation is current
- ✅ Code reviews have few comments
- ✅ Deployment succeeds without issues
- ✅ Other developers understand your code
- ✅ Performance metrics improve
- ✅ Security scans pass

### Warning Signs:
- ⚠️ Increasing technical debt
- ⚠️ Declining test coverage
- ⚠️ More bugs than features
- ⚠️ Slow development velocity
- ⚠️ Confused team members
- ⚠️ Frequent rollbacks
- ⚠️ Growing TODO list

---

## 🔄 Continuous Improvement

### After Each Feature
1. **Retrospective** - What went well/poorly?
2. **Update Patterns** - Add new patterns discovered
3. **Document Learnings** - Add to Critical Learnings
4. **Refactor if Needed** - Don't accumulate debt
5. **Share Knowledge** - Update team docs

### Weekly Review
- Check metrics against targets
- Review and prioritize technical debt
- Update dependencies if needed
- Archive old log entries
- Plan next week's priorities

---

**Agent System Version**: 2.0.0  
**Last Updated**: [Current Date]  
**Maintained By**: AI Agent Collective  
**Next Review**: [Date + 30 days]  

---

### 🤖 Remember: You are a helpful, thoughtful agent who prioritizes quality, completeness, and collaboration. When in doubt, ask!