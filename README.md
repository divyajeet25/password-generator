# Random Password Generator

A simple **Random Password Generator** built using **Python**. This script generates secure passwords with a mix of **lowercase letters, uppercase letters, and numbers**.

## 🖥️ Features

- Generates strong passwords of custom lengths
- Ensures a **minimum length of 8 characters**
- Includes **random uppercase letters and numbers**
- Supports generating **multiple passwords at once**

## 📸 Screenshot



## 🛠️ Installation

1. **Clone this repository:**
   ```sh
   git clone https://github.com/divyajeet25/password-generator.git
   ```
2. **Navigate to the project folder:**
   ```sh
   cd password-generator
   ```
3. **Run the script:**
   ```sh
   python password_generator.py
   ```

## 🚀 Usage

1. Run the script and **enter the number of passwords** you want to generate.
2. Specify the **length** for each password (minimum 8 characters enforced).
3. The program will **generate and display** the passwords.

## 📜 Code Overview

```python
import random

def generatepassword(pwlength):
    alphabet="abcdefghijklmnopqrstuvwxyz"
    passwords=[]

    for i in pwlength:
        password=""
        for j in range(i):
            next_letter_index=random.randrange(len(alphabet))
            password=password+alphabet[next_letter_index]
        password=replaceWithNumber(password)
        password=replaceWithUppercaseLetter(password)    
        passwords.append(password)
    return passwords

def replaceWithNumber(pword):
    for i in range(random.randrange(1,3)):
        replace_index=random.randrange(len(pword)//2)
        pword=pword[0:replace_index]+str(random.randrange(10))+pword[replace_index+1:]
    return pword
    
def replaceWithUppercaseLetter(pword):
    for i in range(random.randrange(1,3)):
        replace_index=random.randrange(len(pword)//2,len(pword))
        pword=pword[0:replace_index]+pword[replace_index].upper()+pword[replace_index+1:]
    return pword

def main():
    numPasswords = int(input("How many passwords do you want to generate?: "))
    print("Generating "+str(numPasswords)+" passwords")
    passwordLengths=[]
    print("Minimum length of password should be 8")
    for i in range(numPasswords):
        length=int(input("Enter the length of password #"+str(i+1)+" "))
        if length<8:
            length=8
        passwordLengths.append(length)
    password=generatepassword(passwordLengths) 
    for i in range(numPasswords):
        print("Password #"+str(i+1)+" = "+password[i])

main()
```

## 🏗️ Technologies Used

- **Python** 🐍
- **random** (Python built-in library for generating random values)

## 🤝 Contributing

Feel free to **fork this repository** and submit pull requests. Suggestions and improvements are always welcome!

## 📜 License

This project is **open-source** and available under the MIT License.

---

Made with ❤️ by [Divyajeet]

