# Development Guidelines

## Code Structure
[Add code structure information here..]

### 1. **Project Structure**
We'll start by organizing the project into a clear and scalable directory structure within your `~/Node/projects` directory:

```bash
mkdir -p ~/Node/projects/GardenPlanner/{client,server,scripts,config,logs,docs}
```

- **client/**: Front-end application for the garden planning interface.
- **server/**: Back-end API for data management, tracking, and storage.
- **scripts/**: Utility scripts for automation and setup.
- **config/**: Configuration files, including environment variables.
- **logs/**: Log files for debugging and monitoring.
- **docs/**: Documentation and project plans.

### 2. **Initial Setup**
Using our scripts, initialize the project:

```bash
cd ~/Node/projects/GardenPlanner
~/Node/scripts/init-project.sh
```

This will copy the basic project template into the `GardenPlanner` directory and install necessary dependencies.

### 3. **Environment Configuration**
Set up the environment with secure `.env` variables. For this project, you'll likely need variables related to database configuration, API keys for any third-party services (like weather data), and JWT secrets for user authentication.

```bash
~/Node/scripts/setup-env.sh GardenPlanner
```

### 4. **Back-End API (server/)**
The server will handle data collection from forms (planting, monthly tracking, etc.), store it in a database, and provide endpoints for the front-end to fetch and display data.

**Example structure:**
```bash
mkdir -p server/src/{controllers,models,routes}
```

**Server entry point (index.js):**
```javascript
const express = require('express');
const app = express();
const PORT = process.env.PORT || 3000;

app.use(express.json());

app.listen(PORT, () => {
  console.log(`Server is running on port ${PORT}`);
});
```

### 5. **Database Setup**
Given the need for extensive tracking capabilities, you'll want a relational database like PostgreSQL or MySQL. Create schemas for tracking forms, plant tables, and planning data.

**Example schema (garden_schema.sql):**
```sql
CREATE TABLE plants (
    id SERIAL PRIMARY KEY,
    name VARCHAR(100) NOT NULL,
    type VARCHAR(50),
    plant_date DATE,
    ph_level DECIMAL(3,2),
    feeding_schedule TEXT
);

CREATE TABLE monthly_tracking (
    id SERIAL PRIMARY KEY,
    plant_id INT REFERENCES plants(id),
    month VARCHAR(20),
    growth_stage TEXT,
    issues TEXT,
    actions_taken TEXT
);
```

### 6. **Front-End Application (client/)**
The front-end will be responsible for data input (e.g., through forms) and visualization (e.g., planting schedules, monthly tracking).

Consider using a framework like React for building interactive UI components, with form validations and dynamic table renderings.

**Client entry point (index.js):**
```javascript
import React from 'react';
import ReactDOM from 'react-dom';
import App from './App';

ReactDOM.render(<App />, document.getElementById('root'));
```

### 7. **Security Implementation**
Ensure all sensitive data (like API keys) is secured through environment variables. Implement JWT authentication on the server to protect user data.

### 8. **Testing and CI/CD**
Set up testing with Jest for both front-end and back-end. Create a GitHub Actions workflow to run these tests automatically on each push.

**Example GitHub Actions workflow:**
```yaml
name: GardenPlanner CI

on:
  push:
    branches: [ "main" ]

jobs:
  test:
    runs-on: ubuntu-latest

    steps:
    - uses: actions/checkout@v2
    - name: Set up Node.js
      uses: actions/setup-node@v2
      with:
        node-version: '14'
    - run: npm install
    - run: npm test
```

### 9. **Documentation**
Update the `docs/` directory with the `PROJECT_OVERVIEW.md`, tracking forms, tables, and comprehensive garden planning details. This will keep everything well-organized and easy to reference.

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