# Scenario B: Mid-Project Takeover

## Condition
- Project already exists
- Not yet deployed to production
- Unfamiliar with the codebase

## Workflow Phases

### Phase 1: Exploration (Critical)
1. Do NOT start coding immediately
2. Agent reads and analyzes the codebase
3. Generate architecture documentation
4. Identify key patterns and conventions
5. Map dependencies between modules

### Phase 2: Orientation
1. Create PLAN.md with understanding of current state
2. Identify technical debt and issues
3. Prioritize what needs attention
4. Plan incremental improvements

### Phase 3: Development
1. Follow existing code patterns
2. Small, focused changes
3. Extensive testing
4. Document decisions

## Exploration Prompt
```
Read the entire project at [PROJECT_PATH].
1. Identify the tech stack and frameworks
2. Map the directory structure
3. Identify entry points
4. Find configuration files
5. Trace key user flows
6. Identify patterns and conventions used
7. Note any code smells or issues
8. Generate a project summary document
```

## Key Patterns
- Understand before modifying
- Follow existing conventions
- Make small, incremental changes
- Test everything
- Document your understanding
