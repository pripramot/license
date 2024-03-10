---
title: "Using Virtual Environments with pip on Windows 10 and VS Code(English)"
seoTitle: "Python & VS Code Virtual Environments Windows 10"
seoDescription: "Python & VS Code Virtual Environments Windows 10"
datePublished: Sun Mar 10 2024 19:47:04 GMT+0000 (Coordinated Universal Time)
cuid: cltlxefjw000t09jy4ygd9jwb
slug: using-virtual-environments-with-pip-on-windows-10-and-vs-codeenglish
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1710101201378/a8560080-6777-4674-be93-c2bd8b2a9684.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1710101643148/9cc36e61-5728-4556-a8da-8852d6f8726a.png
tags: python, developer

---

### **1\. Main topic**

* **What are Virtual Environments?**
    
* **Create a Virtual Environment**
    
* **Activate the Virtual Environment**
    
* **Install package with pip**
    
* **Check the installation**
    
* **Disable the Virtual Environment**
    
* **Using Virtual Environment in VS Code**
    
* **Additional tips**
    

### **2\. Secondary topic**

* **Purpose of Virtual Environments**
    
* **Benefits of Virtual Environments**
    
* **Steps to create a Virtual Environment**
    
* **Results of creating a Virtual Environment**
    
* **Steps to enable Virtual Environment on Command Prompt**
    
* **Steps to enable Virtual Environment on PowerShell**
    
* **Result of activating the Virtual Environment**
    
* **Steps to install packages with pip**
    
* **Result of installing the package**
    
* **Installation inspection steps**
    
* **Results of the installation inspection**
    
* **Steps to disable the Virtual Environment**
    
* **Result of disabling the Virtual Environment**
    
* **Setting up the Python interpreter in VS Code**
    
* **Result of Python interpreter settings**
    
* **Virtual environment managers**
    
* **Package updates**
    
* **Using requirements.txt**
    

### **3\. Content**

**1\. What are Virtual Environments?**

Virtual Environments allow Python projects to isolate their dependencies. This means that each project can have its own set of specific versions of libraries, without having to worry about conflicts with dependencies of other projects. This increases the stability and reproducibility of projects.

**2\. Create a Virtual Environment**

**2.1 Step**

1. **Open Command Prompt** on Windows 10
    
2. **Go to the directory of the project** for which you want to create a Virtual Environment.
    
3. Run the following command:
    

```plaintext
python -m venv <ชื่อ virtual environment>
```

**example:**

```plaintext
python -m venv myprojectenv
```

**2.2 Results**

The above command will create a new directory named `<ชื่อ virtual environment>`within the project directory. This directory will contain the specific version of the Python interpreter and the libraries required for the Virtual Environment.

**3\. Activate the Virtual Environment.**

**3.1 on Command Prompt**

1. Go to the directory of the Virtual Environment.
    
2. Run the following command:
    

```plaintext
<ชื่อ virtual environment>\Scripts\activate
```

**example:**

```plaintext
myprojectenv\Scripts\activate
```

**3.2 on PowerShell**

1. Go to the directory of the Virtual Environment.
    
2. Run the following command:
    

```plaintext
.\<ชื่อ virtual environment>\Scripts\Activate.ps1
```

**example:**

```plaintext
.\myprojectenv\Scripts\Activate.ps1
```

**3.3 Results**

The above command will launch the Virtual Environment. The Command Prompt prompt will display the name of the Virtual Environment in square brackets, indicating that the Virtual Environment is currently in use.

**4\. Install the package with pip**

**4.1 Step**

1. Make sure the Virtual Environment is enabled.
    
2. Run the following command to install the package:
    

```plaintext
pip install <ชื่อแพ็กเกจ>
```

**example:**

```plaintext
pip install pandas
```

**4.2 Results**

The above command will install the specified package into the Virtual Environment.

**5\. Check the installation**

**5.1 Step**

1. Make sure the Virtual Environment is enabled.
    
2. Run the following command to see a list of installed packages:
    

```plaintext
pip freeze
```

**5.2 Results**

The above command will list all packages installed in the Virtual Environment.

**6\. Disable the Virtual Environment.**

**6.1 Step**

1. Run the following command:
    

```plaintext
deactivate
```

**6.2 Results**

The above command will disable the Virtual Environment prompt. The Command Prompt will return to its normal state.

---

**7\. Using Virtual Environment in VS Code**

**7.1 Set up the Python interpreter**

1. Open VS Code
    
2. Open the desired project
    
3. Go to **File &gt; Preferences &gt; Settings.**
    
4. Search for "Python: Default Interpreter"
    
5. Select the Python interpreter of the Virtual Environment.
    

**7.2 Results**

VS Code uses the Virtual Environment's Python interpreter.

**8\. Additional tips**

**8.1 Virtual environment managers**

* Virtual environment managers make it easier to manage Virtual Environments.
    
* Example Virtual environment managers:
    
    * `virtualenv`
        
    * `conda`
        

**8.2 Updating packages**

* Run the following command to update the package:
    

```plaintext
pip install --upgrade <ชื่อแพ็กเกจ>
```

**8.3 Using requirements.txt**

* `requirements.txt`This is a text file that lists the packages that the project needs.
    

**Additional content**

* Links to additional resources about Virtual Environments, pip, Windows 10, and VS Code.
    
* Examples of using Virtual Environments in various situations
    
* Tips for troubleshooting common errors related to Virtual Environments