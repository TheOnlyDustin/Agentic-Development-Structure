# AI Agent Development Instructions
## Universal Coding Guidelines for AI-Assisted Development

## 🎯 Golden Rules

1. **One File, One Complete Feature** - Never leave a file partially implemented
2. **Test As You Build** - Write test immediately after implementation
3. **Update Indexes Always** - Every new file must be registered
4. **Log Everything** - Update DEVELOPMENT_LOG.md after each session
5. **No Broken Builds** - Code must run after every commit

## 📁 Before Starting Any Task

### Pre-Flight Checklist
```bash
# 1. Read current status
cat PROJECT_INDEX.md | grep "Current Status"

# 2. Check last development session
tail -50 DEVELOPMENT_LOG.md

# 3. Verify your module exists
ls -la src/[your-module]/

# 4. Update PROJECT_INDEX.md to claim task
# Mark yourself as Active Agent
```

## 🏗️ File Creation Pattern

### Step 1: Create File with Full Documentation
```typescript
/**
 * @filename /src/[module]/[feature].ts
 * @module ModuleName
 * @description Complete description of what this file does
 * @author AI Agent - [Claude/Cursor/Gemini/Other]
 * @date [Current Date]
 * @dependencies List all imports needed
 * @exports List all exported functions/types
 */

// Import block - group by type
// External dependencies
import [package] from '[package-name]';

// Internal dependencies  
import { [item] } from '../[module]';

// Types
import type { [TypeName] } from '../types';

// Initialize module
const MODULE_NAME = '[ModuleName]';
const logger = new Logger(MODULE_NAME);

// Main implementation
[Complete implementation - no TODOs]

// Export everything
export { functionName, ClassName };
export type { InterfaceName };
```

### Step 2: Register in Module Index
```typescript
// /src/[module]/index.ts
export * from './[feature]';
```

### Step 3: Update Master Registry
```typescript
// /src/modules.index.ts (if exists)
export * as moduleName from './[module-name]';
```

### Step 4: Update PROJECT_INDEX.md
- Mark file as ✅ Created
- Update dependencies
- Note any important decisions

### Step 5: Create Test File
```typescript
// /tests/[module]/[feature].test.ts
```

## 🔧 Common Implementation Patterns

### API Endpoint Pattern
```typescript
// /src/api/routes/[resource].routes.ts

import { Router } from 'express';
import { authenticate } from '../../auth/middleware';
import { validate } from '../middleware/validation';
import { [schema] } from '../schemas/[resource].schema';
import { [Service] } from '../../services/[resource].service';
import { Logger } from '../../utils/logger';

const router = Router();
const logger = new Logger('[Resource]Routes');
const service = new [Service]();

/**
 * @api {get} /api/[resources] List [Resources]
 * @apiName List[Resources]
 * @apiGroup [Resources]
 * @apiDescription Get all [resources]
 */
router.get('/', authenticate, async (req, res, next) => {
  try {
    logger.info('Listing [resources]', { 
      userId: req.user.id 
    });
    
    const result = await service.list(req.query);
    
    res.json({ 
      success: true, 
      data: result 
    });
  } catch (error) {
    logger.error('Failed to list [resources]', error);
    next(error);
  }
});

/**
 * @api {post} /api/[resources] Create [Resource]
 * @apiName Create[Resource]  
 * @apiGroup [Resources]
 */
router.post('/', 
  authenticate, 
  validate([schema]), 
  async (req, res, next) => {
    try {
      logger.info('Creating [resource]', req.body);
      
      const result = await service.create({
        ...req.body,
        userId: req.user.id
      });
      
      res.status(201).json({ 
        success: true, 
        data: result 
      });
    } catch (error) {
      logger.error('Failed to create [resource]', error);
      next(error);
    }
});

export default router;
```

### Service Pattern
```typescript
// /src/services/[service-name].service.ts

import { [Repository] } from '../database/repositories/[model].repository';
import { Logger } from '../utils/logger';
import type { [Model], Create[Model]Dto } from '../types';

export class [Service]Service {
  private repository: [Repository];
  private logger: Logger;
  
  constructor() {
    this.repository = new [Repository]();
    this.logger = new Logger('[Service]Service');
  }
  
  async create(dto: Create[Model]Dto): Promise<[Model]> {
    this.logger.info('Creating [model]', dto);
    
    try {
      // Step 1: Validate/Process
      const processed = await this.process(dto);
      
      // Step 2: Business logic
      const enhanced = await this.enhance(processed);
      
      // Step 3: Save
      const result = await this.repository.create(enhanced);
      
      // Step 4: Post-processing
      await this.postProcess(result);
      
      this.logger.info('[Model] created successfully', { 
        id: result.id 
      });
      return result;
      
    } catch (error) {
      this.logger.error('Failed to create [model]', error);
      throw new Error(`[Model] creation failed: ${error.message}`);
    }
  }
  
  private async process(data: any): Promise<any> {
    // Implementation
    return data;
  }
  
  private async enhance(data: any): Promise<any> {
    // Implementation  
    return data;
  }
  
  private async postProcess(result: any): Promise<void> {
    // Implementation
  }
}
```

### Repository Pattern
```typescript
// /src/database/repositories/[model].repository.ts

import { db } from '../connection';
import { Logger } from '../../utils/logger';
import type { [Model], Create[Model]Dto } from '../../types';

export class [Model]Repository {
  private collection: any; // Your DB collection/table reference
  private logger: Logger;
  
  constructor() {
    this.collection = db.collection('[models]'); // Adjust for your DB
    this.logger = new Logger('[Model]Repository');
  }
  
  async create(data: Create[Model]Dto): Promise<[Model]> {
    try {
      const result = await this.collection.insert({
        ...data,
        createdAt: new Date(),
        updatedAt: new Date()
      });
      
      return result;
      
    } catch (error) {
      this.logger.error('Failed to create [model]', error);
      throw error;
    }
  }
  
  async findById(id: string): Promise<[Model] | null> {
    try {
      const result = await this.collection.findOne({ id });
      return result || null;
      
    } catch (error) {
      this.logger.error('Failed to find [model]', error);
      throw error;
    }
  }
  
  async update(id: string, data: Partial<[Model]>): Promise<[Model]> {
    try {
      const result = await this.collection.update(
        { id },
        { ...data, updatedAt: new Date() }
      );
      
      return result;
      
    } catch (error) {
      this.logger.error('Failed to update [model]', error);
      throw error;
    }
  }
}
```

### Error Handling Pattern
```typescript
// Consistent error handling across all modules

class AppError extends Error {
  constructor(
    public message: string,
    public statusCode: number = 500,
    public details?: any
  ) {
    super(message);
    this.name = 'AppError';
  }
}

// Usage in routes/services
try {
  const result = await operation();
  return result;
} catch (error) {
  if (error instanceof AppError) {
    throw error;
  }
  throw new AppError(
    'Operation failed',
    500,
    { originalError: error.message }
  );
}
```

## 🧪 Testing Patterns

### Unit Test Template
```typescript
// /tests/unit/[module]/[feature].test.ts

import { describe, it, expect, beforeEach, jest } from '@jest/globals';
import { [Class/Function] } from '../../../src/[path]';

describe('[Class/Function]', () => {
  let instance: [Class];
  
  beforeEach(() => {
    instance = new [Class]();
    // Mock dependencies
  });
  
  describe('[methodName]', () => {
    it('should [expected behavior]', async () => {
      // Arrange
      const input = { /* test data */ };
      const expected = { /* expected result */ };
      
      // Act
      const result = await instance.[method](input);
      
      // Assert
      expect(result).toEqual(expected);
    });
    
    it('should handle errors gracefully', async () => {
      // Arrange
      const badInput = { /* invalid data */ };
      
      // Act & Assert
      await expect(instance.[method](badInput))
        .rejects.toThrow('[Expected error]');
    });
  });
});
```

## 📝 Development Log Format

### After Each Session, Update DEVELOPMENT_LOG.md:
```markdown
## [Date] [Time] - [Agent Name]

### Session Goal
[What you aimed to accomplish]

### Completed Tasks
- ✅ [Task 1]
- ✅ [Task 2]  
- ❌ [Incomplete task - why]

### Files Modified
- `/path/to/file` - [What changed]

### Key Decisions
- [Decision]: [Reasoning]

### Test Results
```
[Test output]
```

### Known Issues
- [ ] [Issue to address]

### Next Agent Should
1. [Priority task]
2. [Secondary task]

### Notes
[Any additional context]
```

## 🚨 Common Pitfalls & Solutions

### Pitfall 1: Circular Dependencies
```typescript
// ❌ BAD - Circular dependency
// File A imports B, B imports A

// ✅ GOOD - Use dependency injection or interfaces
class ServiceA {
  constructor(private serviceB: IServiceB) {}
}
```

### Pitfall 2: Missing Error Handling
```typescript
// ❌ BAD
const data = await fetchData();
return data;

// ✅ GOOD  
try {
  const data = await fetchData();
  if (!data) throw new Error('No data found');
  return data;
} catch (error) {
  logger.error('Failed to fetch data', error);
  throw new AppError('Data fetch failed', 500);
}
```

### Pitfall 3: Incomplete Type Definitions
```typescript
// ❌ BAD
function process(data: any) { }

// ✅ GOOD
import type { DataType } from '../types';
function process(data: DataType): ProcessedType { }
```

### Pitfall 4: No Logging
```typescript
// ❌ BAD
async function deleteItem(id) {
  await repository.delete(id);
}

// ✅ GOOD
async function deleteItem(id: string) {
  logger.info('Deleting item', { id });
  try {
    await repository.delete(id);
    logger.info('Item deleted successfully', { id });
  } catch (error) {
    logger.error('Failed to delete item', { id, error });
    throw error;
  }
}
```

## 🔄 Module Development Order

### Correct Build Sequence
1. **Config & Types** → No dependencies
2. **Database/Connection** → Depends on config
3. **Models/Schemas** → Depends on types
4. **Repositories/DAL** → Depends on models, database
5. **Core Logic** → Depends on types
6. **Services** → Depends on repositories, core
7. **API/Controllers** → Depends on services
8. **UI/Frontend** → Depends on API

### For Each Module
1. Create all type definitions first
2. Implement core functionality
3. Add error handling
4. Write tests
5. Update documentation
6. Register in indexes

## 📊 Progress Tracking

### How to Update Progress
1. Open PROJECT_INDEX.md
2. Find your module in the table
3. Change ⏳ to 🚧 when starting
4. Change 🚧 to ✅ when complete
5. Update "Current Status" section
6. Commit with descriptive message

### Commit Message Format
```bash
feat([module]): [what was added]
fix([module]): [what was fixed]
test([module]): [tests added]
docs: [documentation updated]
refactor([module]): [what was refactored]
chore: [maintenance task]
```

## 🔒 Security Checklist

For every module:
- [ ] Validate all inputs
- [ ] Sanitize user content
- [ ] Use parameterized queries
- [ ] Implement rate limiting
- [ ] Add authentication checks
- [ ] Log security events
- [ ] Handle errors without exposing internals
- [ ] Encrypt sensitive data

## 💡 Quick Tips

1. **Use TypeScript Strictly**: No `any` types unless absolutely necessary
2. **Prefer Async/Await**: Over callbacks/promises
3. **Small Functions**: Max 50 lines per function
4. **Clear Names**: Be descriptive, not clever
5. **Early Returns**: Reduce nesting
6. **Const By Default**: Use `let` only when reassignment needed
7. **No Magic Numbers**: Use named constants
8. **Document WHY**: Not just what

## 🚀 Ready to Start?

1. Read PROJECT_INDEX.md for current state
2. Check DEVELOPMENT_LOG.md for context
3. Choose your task
4. Follow this guide step by step
5. Test as you build
6. Update logs and indexes
7. Commit completed work

Remember: **Complete one thing fully before moving to the next!**

---
*This document is the universal source of truth for AI agent development patterns*
*Version: 1.0.0 - Universal Template*