# Oracle Pluggable Database Assignment II - README

## Student Information
- **Student ID**: 29008
- **First Name**: Jacques
- **Course**: Database Development with PL/SQL (INSY 8311)

---

## Assignment Overview
- Creating and managing Pluggable Databases (PDBs)
- User creation and administration within PDBs
- Oracle Enterprise Manager (OEM) configuration
- Professional technical documentation

---

## Oracle Environment
- **Oracle Version**: [e.g., Oracle 19c/21c]
- **Operating System**: [e.g., Windows 10/Linux Ubuntu 22.04]
- **Container Database (CDB)**: [Your CDB Name]
- **Oracle Enterprise Manager**: [Version]

---

## Tasks Completed

### Task 1: Create a New Pluggable Database

**Naming Convention Used**:
- **PDB Name**: `ja_pdb_29008`
- **Username**: `jacques_plsqlauca_29008`

**Steps Performed**:
1. Connected to CDB as SYSDBA
2. Created the PDB using appropriate SQL commands
3. Opened the PDB in READ WRITE mode
4. Created the user account with necessary privileges
5. Verified successful creation and user login

---

### Task 2: Create and Delete a Temporary PDB

**Naming Convention Used**:
- **Temporary PDB Name**: `ja_to_delete_pdb_29008`

**Steps Performed**:
1. Created temporary PDB
2. Verified PDB existence in `v$pdbs` view
3. Closed the PDB
4. Dropped the PDB including datafiles
5. Confirmed successful deletion
---

### Task 3: Oracle Enterprise Manager (OEM)

**Steps Performed**:
1. Started OEM service
2. Accessed OEM web interface
3. Logged in with appropriate credentials
4. Verified PDB status in dashboard
5. Captured dashboard view showing completed tasks

---

## Key SQL Commands Used

### PDB Creation
```sql
-- Connect as SYSDBA
CREATE PLUGGABLE DATABASE ja_pdb_29008
  ADMIN USER pdb_admin IDENTIFIED BY your_password
  FILE_NAME_CONVERT = ('/pdbseed/', '/ja_pdb_29008/');

-- Open PDB
ALTER PLUGGABLE DATABASE ja_pdb_29008 OPEN;

-- Set PDB to auto-start
ALTER PLUGGABLE DATABASE ja_pdb_29008 SAVE STATE;
```

### User Creation
```sql
-- Connect to PDB
ALTER SESSION SET CONTAINER = ja_pdb_29008;

-- Create user
CREATE USER jacques_plsqlauca_29008 IDENTIFIED BY your_password;
GRANT CONNECT, RESOURCE TO jacques_plsqlauca_29008;
GRANT UNLIMITED TABLESPACE TO jacques_plsqlauca_29008;
```

### PDB Deletion
```sql
-- Close PDB
ALTER PLUGGABLE DATABASE ja_to_delete_pdb_29008 CLOSE IMMEDIATE;

-- Drop PDB
DROP PLUGGABLE DATABASE ja_to_delete_pdb_29008 INCLUDING DATAFILES;
```

### Verification Commands
```sql
-- Check PDBs
SELECT pdb_name, status FROM dba_pdbs;

-- Check container name
SHOW CON_NAME;

-- Verify user creation
SELECT username FROM dba_users WHERE username = 'JACQUES_PLSQLAUCA_29008';
```

---

## Academic Integrity Statement

“All sources were properly cited. Implementations and analysis represent original work. No AI-
generated content was copied without attribution or adaptation.”

---

## Submission Information
- **GitHub Repository**:https://github.com/jacqueskarenzi/oracle_pdb_ass_II_29008_jacques/tree/main
- **Primary PDB Created**: `ja_pdb_29008`
- **Temporary PDB Created & Deleted**: `ja_to_delete_pdb_29008`


---

## References
- Oracle Database Documentation: Oracle Multitenant Architecture
- Oracle Enterprise Manager Cloud Control Documentation
- Course Materials: Database Development with PL/SQL (INSY 8311)
