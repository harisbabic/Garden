#### Development Environment Setup

To set up your development environment for the Garden Planner project, follow these steps:

1. **Clone the Repository**:
   ```bash
   git clone [repository-url]
   cd GardenPlanner
   ```

2. **Install Dependencies**:
   - **Backend**:
     ```bash
     cd server
     npm install
     ```
   - **Frontend**:
     ```bash
     cd client
     npm install
     ```

3. **Environment Variables**:
   - Create a `.env` file in the root of the `server` directory based on the `.env.example` template.
   - Ensure all required variables are set, such as `DB_HOST`, `DB_USER`, and `JWT_SECRET`.

4. **Database Setup**:
   - Run the database schema and seed files to set up your development database.

5. **Start the Application**:
   - **Backend**:
     ```bash
     npm run dev
     ```
   - **Frontend**:
     ```bash
     npm start
     ```
