# Oracle Pluggable Database Assignment II - README

## Student Information
- **Student ID**: 29008
- **First Name**: karenzi jacques
- **Course**: Database Development with PL/SQL (INSY 8311)


---

### Task 1: Create a New Pluggable Database
**Objective**: Create a permanent PDB for future class work

**Naming Convention Used**:
- **PDB Name**: `[FirstTwoLetters]_pdb_[StudentID]`
  - Example: `er_pdb_2024101`
- **Username**: `[FirstName]_plsqlauca_[StudentID]`
  - Example: `eric_plsqlauca_2024101`
- **Password**: [Your chosen password - do not share publicly]

**Steps Performed**:
1. Connected to CDB as SYSDBA
2. Created the PDB using appropriate SQL commands
3. Opened the PDB in READ WRITE mode
4. Created the user account with necessary privileges
5. Verified successful creation and user login

**Evidence**: See `screenshots/task1_pdb_creation.png`

---

### Task 2: Create and Delete a Temporary PDB
**Objective**: Demonstrate PDB lifecycle management

**Naming Convention Used**:
- **Temporary PDB Name**: `[FirstTwoLetters]_to_delete_pdb_[StudentID]`
  - Example: `er_to_delete_pdb_2024101`

**Steps Performed**:
1. Created temporary PDB
2. Verified PDB existence in `v$pdbs` view
3. Closed the PDB
4. Dropped the PDB including datafiles
5. Confirmed successful deletion

**Evidence**: See `screenshots/task2_pdb_deletion.png`

---

### Task 3: Oracle Enterprise Manager (OEM)
**Objective**: Configure and access OEM dashboard

**Steps Performed**:
1. Started OEM service
2. Accessed OEM web interface
3. Logged in with appropriate credentials
4. Verified PDB status in dashboard
5. Captured dashboard view showing completed tasks

**Evidence**: See `screenshots/task3_oem_dashboard.png`

---

## Challenges Encountered and Solutions

### Challenge 1: [If any]
**Issue**: [Description of problem]
**Solution**: [How you resolved it]

### Challenge 2: [If any]
**Issue**: [Description of problem]
**Solution**: [How you resolved it]

*If no challenges were encountered, state: "No significant challenges encountered during this assignment."*

---

## Screenshots Directory Structure
```
screenshots/
├── task1_pdb_creation.png
├── task1_pdb_open.png
├── task1_user_created.png
├── task2_pdb_creation.png
├── task2_pdb_verification.png
├── task2_pdb_deletion.png
├── task2_deletion_confirmed.png
└── task3_oem_dashboard.png
```

---

## Key SQL Commands Used

### PDB Creation
```sql
-- Connect as SYSDBA
CREATE PLUGGABLE DATABASE [pdb_name]
  ADMIN USER [admin_user] IDENTIFIED BY [password]
  FILE_NAME_CONVERT = ('[source_path]', '[target_path]');

-- Open PDB
ALTER PLUGGABLE DATABASE [pdb_name] OPEN;
```

### User Creation
```sql
-- Connect to PDB
ALTER SESSION SET CONTAINER = [pdb_name];

-- Create user
CREATE USER [username] IDENTIFIED BY [password];
GRANT CONNECT, RESOURCE TO [username];
```

### PDB Deletion
```sql
-- Close PDB
ALTER PLUGGABLE DATABASE [pdb_name] CLOSE IMMEDIATE;

-- Drop PDB
DROP PLUGGABLE DATABASE [pdb_name] INCLUDING DATAFILES;
```

---

## Academic Integrity Statement
I, **[Your Full Name]**, hereby declare that:
- All work submitted is my own individual effort
- No commands, screenshots, or documentation were copied from classmates
- No AI tools (ChatGPT or similar) were used to generate solutions
- All screenshots represent my actual execution of tasks
- This repository and all its contents reflect my genuine understanding and work

**Signature**: [Your Name]  
**Date**: [Submission Date]

---

## Submission Information
- **GitHub Repository**: [Your Public Repository URL]
- **Primary PDB Created**: `[Your PDB Name]`
- **Google Form Submitted**: [Yes/Confirmation]
- **Submission Status**: On-time / [Date Submitted]

---

## References
- Oracle Database Documentation: Oracle Multitenant Architecture
- Oracle Enterprise Manager Cloud Control Documentation
- Course Materials: Database Development with PL/SQL (INSY 8311)

---

## Contact
- **Email**: [Your AUCA Email]
- **GitHub**: [Your GitHub Username]

---

*"Excellence is never an accident; it is the result of discipline, commitment, and integrity."*

---

**Repository Status**: ✅ PUBLIC  
**Last Updated**: [Date]
