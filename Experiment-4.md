# Experiment 4

## Question
Create the /home/consultants directory.
Add write permission to the consultants group. Use the
symbolic method for setting the appropriate permissions.
Forbid others from accessing files in
the /home/consultants directory. Use the octal method for
setting the appropriate permissions.
Change the default umask for the operator1 user. The new
umask prohibits all access for users that are not in their
group. Confirm that the umask is changed

## Approach

1. *Directory Creation*: Use the mkdir command with sudo to create the /home/consultants directory.

2. *Setting Group Permissions*:
   - Use the symbolic method with the chmod command to add write permission for the consultants group.

3. *Restricting Access for Others*:
   - Use the octal method with the chmod command to set permissions that forbid others from accessing the directory, specifically setting it to 770.

4. *Configuring umask for User*:
   - Modify the user's shell configuration file (e.g., .bashrc) to set a new umask value of 007, which restricts access for users not in the group.

5. *Verifying umask Change*:
   - Switch to the operator1 user and use the umask command to confirm that the new umask setting has been applied correctly.

## Code

### 1. Create the directory
```bash
sudo mkdir /home/consultants
```

---

### 2. Add write permission for the consultants group
```bash
sudo groupadd consultants
sudo chown :consultants /home/consultants
sudo chmod g+w /home/consultants
```

---

### 3. Forbid others from accessing the directory
```bash
sudo chmod 770 /home/consultants
```

---

### 4. Change the umask for operator1
```bash
sudo nano /home/operator1/.bashrc
# Add: umask 007
sudo su - operator1
source ~/.bashrc
```

---

### 5. Confirm the umask
```bash
umask
```

---

## Code Snippet

### 1. Change the umask for operator1

![WhatsApp Image 2025-03-22 at 14 36 43_4781ffee](https://github.com/user-attachments/assets/9d4b3207-14e6-4133-81f9-c192969e6abf)

---

### 2. Final Output

![WhatsApp Image 2025-03-22 at 14 33 46_a5463084](https://github.com/user-attachments/assets/5b3e4d51-cb88-457b-99e6-d80a8fdf5263)

