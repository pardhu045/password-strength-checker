# Password Strength Assessment Tool (Python)

## 📌 Objective
This project evaluates the strength of user-provided passwords using commonly accepted security best practices.  
It helps identify weak passwords and reinforces the importance of strong authentication mechanisms in cybersecurity.

---

## 🖥️ Environment Details
- OS: Kali Linux (VMware Workstation)
- Python Version: 3.13.7
- Shell: Bash
- Execution Type: Local lab environment

---

## 🧰 Tools & Technologies
- Programming Language: Python
- Module Used: `re` (Regular Expressions)

---

## 📂 Step-by-Step Execution (Exact Commands Used)

### 1️⃣ Navigate to Projects Directory
```bash
cd ~/cyberprojects
2️⃣ Create Project Directory
bash
Copy code
mkdir password_checker
cd password_checker
3️⃣ Create Python Virtual Environment
bash
Copy code
python -m venv venv
4️⃣ Activate Virtual Environment
bash
Copy code
source venv/bin/activate
After activation, the terminal prompt changes to:

scss
Copy code
(venv)
5️⃣ Create Python Source File
bash
Copy code
touch password_checker.py
nano password_checker.py
🧾 Python Source Code (password_checker.py)
python
Copy code
import re

def check_password_strength(password):
    score = 0

    if len(password) >= 8:
        score += 1
    if re.search(r"[A-Z]", password):
        score += 1
    if re.search(r"[a-z]", password):
        score += 1
    if re.search(r"[0-9]", password):
        score += 1
    if re.search(r"[!@#$%^&*(),.?\":{}|<>]", password):
        score += 1

    return score

password = input("Enter a password to check strength: ")

strength = check_password_strength(password)

print("\nPassword Analysis:")

if strength <= 2:
    print("Strength: WEAK")
elif strength == 3:
    print("Strength: MODERATE")
elif strength == 4:
    print("Strength: STRONG")
else:
    print("Strength: VERY STRONG")
Save and exit the editor:

CTRL + O → Enter

CTRL + X

6️⃣ Run the Program
bash
Copy code
python password_checker.py
▶️ Observed Behavior
Prompts the user to enter a password

Evaluates password complexity

Displays strength classification

No password is stored, logged, or transmitted

🧠 Learning Outcomes
Understanding of password complexity rules

Password policy enforcement concepts

Authentication weaknesses and prevention

Relationship between passwords and account security
