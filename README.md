# Linux-administration-i
# Linux Administration I — User, Group, Permissions & Sudo Configuration

This project demonstrates foundational Linux system administration skills, including user and group management, directory permissions, and restricted sudo access. All tasks were performed on Ubuntu in a controlled lab environment and documented with screenshots.

---

## 📌 Project Objectives
- Create and manage users and groups  
- Configure directory ownership and permissions  
- Implement restricted sudo privileges  
- Validate access controls and permission boundaries  
- Document the entire workflow for portfolio presentation  

---

# 🧩 1. Create a New User

A new user account was created for the project.

### Command:
```bash
sudo adduser student1
```

### Screenshot:
![Create User](screenshots/Screenshot\ \(1\).png)

---

# 🧩 2. Create a New Group

A dedicated group was created for project access control.

### Command:
```bash
sudo groupadd projectgroup
```

### Screenshot:
![Create Group](screenshots/Screenshot\ \(2\).png)

---

# 🧩 3. Add User to the Group

The new user was added to the project group.

### Commands:
```bash
sudo usermod -aG projectgroup student1
groups student1
```

### Screenshot:
![Add User to Group](screenshots/Screenshot\ \(3\).png)

---

# 🧩 4. Create a Shared Project Directory

A shared directory was created for group collaboration.

### Command:
```bash
sudo mkdir /projectfolder
```

### Screenshot:
![Create Directory](screenshots/Screenshot\ \(4\).png)

---

# 🧩 5. Assign Group Ownership

Ownership of the directory was assigned to the project group.

### Command:
```bash
sudo chown :projectgroup /projectfolder
```

### Screenshot:
![Chown Directory](screenshots/Screenshot\ \(5\).png)

---

# 🧩 6. Set Directory Permissions

Permissions were configured to allow full access for the owner and group.

### Commands:
```bash
sudo chmod 770 /projectfolder
ls -ld /projectfolder
```

### Screenshot:
![Set Permissions](screenshots/Screenshot\ \(6\).png)

---

# 🧩 7. Configure Restricted Sudo Access

The user was granted limited sudo privileges for the `apt` command only.

### Command:
```bash
sudo visudo
```

### Sudoers Entry:
```
student1 ALL=(ALL) /usr/bin/apt
```

### Screenshot:
![Sudoers Entry](screenshots/Screenshot\ \(7\).png)

---

# 🧩 8. Test Allowed Sudo Command

The user successfully ran an allowed sudo command.

### Command:
```bash
sudo apt update
```

### Screenshot:
![Allowed Command](screenshots/Screenshot\ \(8\).png)

---

# 🧩 9. Test Denied Sudo Command

A restricted command was correctly denied.

### Command:
```bash
sudo systemctl status ssh
```

### Screenshot:
![Denied Command](screenshots/Screenshot\ \(9\).png)

---

# 🧩 10. Final Verification

Group membership, directory permissions, and sudo restrictions were verified.

### Commands:
```bash
ls -ld /projectfolder
groups student1
sudo grep student1 /etc/sudoers
```

### Screenshot:
![Final Verification](screenshots/Screenshot\ \(10\).png)

---

# 🧠 Skills Demonstrated

| Skill Area | Description |
|-----------|-------------|
| **User Management** | Creating, modifying, and validating user accounts |
| **Group Administration** | Managing group membership and access control |
| **Filesystem Permissions** | Applying Linux permission models (rwx, chmod, chown) |
| **Privilege Management** | Configuring restricted sudo access via sudoers |
| **Security Best Practices** | Enforcing least‑privilege access |
| **Documentation** | Clean, professional workflow documentation |

---

# 📘 What I Learned

- How Linux handles users, groups, and permissions  
- How to apply least‑privilege principles using sudoers  
- How to validate access controls through testing  
- How to document a technical workflow for professional presentation  
- How to structure a Linux admin project for GitHub and portfolio use  

---

# 🏁 Summary

This project demonstrates core Linux administration capabilities required for help desk, IT support, and system administration roles. It shows the ability to configure users, groups, permissions, and restricted sudo access — all essential skills for managing secure Linux environments.

