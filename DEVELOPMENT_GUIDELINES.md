# Development Guidelines

## Code Structure
This project follows a modular architecture. Each module should be self-contained with its own routes, components, and business logic.

### Directory Structure
```
project-root/
├── server/
│   ├── src/
│   │   ├── modules/
│   │   │   ├── core/
│   │   │   ├── user-management/
│   │   │   ├── authentication/
│   │   │   └── ...
│   │   └── module-loader.js
├── client/
│   ├── src/
│   │   ├── modules/
│   │   │   ├── core/
│   │   │   ├── user-management/
│   │   │   ├── authentication/
│   │   │   └── ...
│   │   └── module-loader.js
└── module-config.json
```

## Module Development
1. Create a new directory for your module under `server/src/modules/` and/or `client/src/modules/`.
2. Implement the module's functionality.
3. Update `module-config.json` to include your new module.

## Critical Development Guidelines

### 1. File Structure and Naming
- Always provide relative paths with file names commented at the top of each generated file.
- Use kebab-case for file names (e.g., `my-component.js`).
- Use PascalCase for component names (e.g., `MyComponent`).

### 2. Code Completeness
- Generate complete, production-ready files. Avoid placeholders or incomplete examples.
- Include meaningful implementations and comprehensive tests for each module.
- Only use placeholders when absolutely necessary, clearly marking them for later completion.

### 3. Documentation
- Include clear, concise comments in all code.
- Keep documentation up-to-date with each change or new feature.

### 4. Testing
- Write thorough, meaningful tests for each module.
- Avoid generic or example tests that don't fully assess functionality.

### 5. Error Handling and Logging
- Implement proper error handling in all code.
- Use the project's logging system consistently.

### 6. Security
- Always consider security implications in code generation.
- Never include sensitive information (API keys, passwords) in generated code.

### 7. Performance
- Consider performance implications, especially for database operations and API calls.

### 8. Accessibility
- Ensure all UI components follow WCAG guidelines.

### 9. Code Generation and Adaptation
- When adapting code from other projects, ensure compatibility with the Node project structure.
- Adjust imports, file paths, and dependencies to fit the project structure.

### 10. Version Control
- Provide meaningful commit messages that clearly describe changes.

### 11. Environment Specifics
- Development is done on a Windows 10 machine using Git Bash for command line operations.

## Thread Handoff Process
To maintain continuity across development sessions and conversation threads, we use a standardized handoff process:

1. At the end of each significant development session or conversation thread, update the PROJECT_STATUS.md file with the latest handoff summary.
2. The handoff summary should include:
   - Project Status Summary
   - Current Focus
   - Recent Changes
   - Next Steps
   - Open Questions or Challenges
3. At the beginning of each new development session or conversation thread, refer to the PROJECT_STATUS.md file to quickly get up to speed.
4. Continuously update README.md, DEVELOPMENT_GUIDELINES.md, and ROADMAP.md to reflect the current project status and plans.

This process ensures that anyone can quickly understand the current state of the project and continue work efficiently.

## Communication and Collaboration
- Primary communication: Direct conversation with AI, referencing these guidelines.
- Consistently refer to `DEVELOPMENT_GUIDELINES.md`, `README.md`, and `Roadmap.md` for project direction and standards.
- Emphasize the need for complete, production-ready code in all interactions.

## Deployment
(Include guidelines for deploying the application, if applicable.)

## Continuous Integration/Continuous Deployment (CI/CD)
(Include information about the CI/CD pipeline, if applicable.)



These updated guidelines provide a comprehensive framework for our development process. They address crucial aspects such as code completeness, security, performance, and accessibility, which are essential for creating a robust and maintainable application.

Now that we have these guidelines in place, we can proceed with implementing the core module. Before we start, let's update our PROJECT_STATUS.md to reflect our current status and next steps:


# Project Status

## Project Status Summary
The project is in its initial setup phase. We have established the basic project structure, including the modular architecture for both server and client sides. We have also updated our development guidelines to ensure high-quality, consistent code throughout the project.

## Current Focus
- Implementing the core module with basic functionality
- Setting up the database and ORM
- Creating the basic CRUD operations for the plant management system

## Recent Changes
- Updated DEVELOPMENT_GUIDELINES.md with comprehensive guidelines for AI-assisted development
- Refined project structure and documentation

## Next Steps
1. Set up the database and choose an ORM
2. Implement the core module with basic plant management functionality
3. Create comprehensive tests for the core module
4. Set up error handling and logging for the core module
5. Begin work on the user management module

## Open Questions or Challenges
- Decide on the specific ORM to use for database interactions
- Determine the best approach for handling real-time updates (e.g., WebSockets, Server-Sent Events)
- Explore options for integrating with weather APIs