# Linux User Management Lab

## Lab Title
Cybersecurity Associate Assignment 1: Linux User Management & File Permissions

## Objective
To demonstrate proficiency in Linux user and group management, file ownership, and permission settings by creating departmental workspaces for TechCorp Solutions.

## Tools Used
- Kali Linux (Debian-based distribution)
- Terminal/Shell
- useradd, usermod, groupadd, chown, chmod
- getent, id, ls, cat

## Step-by-Step Process

### Part 1: Marketing Department (Private Files)
1. Created `marketing` group using `groupadd`
2. Created 5 users: alice_m, bob_m, carol_m, david_m, emma_m
3. Added users to marketing group with `usermod -a -G`
4. Created individual report files in `/home/shared/marketing/`
5. Set ownership to respective users
6. Applied `chmod 700` for strict private access

### Part 2: IT Department (Shared Collaboration)
1. Created `itdept` group using `groupadd`
2. Created 5 users: frank_it, grace_it, henry_it, iris_it, jack_it
3. Added users to itdept group
4. Created shared `project_specs.txt` in `/home/shared/itdept/`
5. Set group ownership to `itdept`
6. Applied `chmod 770` for collaborative access

## Commands Executed
[Include all commands from the guide above]

## Screenshots of Results
- cat /etc/passwd output
  <img width="470" height="115" alt="verifying all users created" src="https://github.com/user-attachments/assets/80e28a1c-18ee-4cac-9e3c-d428372e085d" />

- getent group outputs <br>
  <img width="272" height="67" alt="verifying groups and members" src="https://github.com/user-attachments/assets/b9ee5ca4-2ec2-4d2d-bd7b-04281707f159" />

- ls -l directory listings <br>
  <img width="338" height="110" alt="verifying files created with permissions" src="https://github.com/user-attachments/assets/0a0d33fa-0499-41af-890a-0a77c5497ba4" />

- id command outputs <br>
  <img width="325" height="67" alt="verifying group user permissions" src="https://github.com/user-attachments/assets/923461b0-980f-4ce8-933d-cde909bbe90b" />


## Key Observations / Lessons Learned
- `chmod 700` (rwx------) ensures only the file owner can access, perfect for private workspaces
- `chmod 770` (rwxrwx---) enables group collaboration while keeping outsiders out
- The `-a` flag in `usermod -a -G` is critical to append groups without removing existing ones
- Proper group ownership (`chown :group`) is essential for shared resource access
- Directory structure planning (`/home/shared/dept/`) improves organizational security

## Author
__Joel Mensah Kordie Ankamah-Boateng__
