Ashish, here is the **updated README** with the sections you requested **removed**. It focuses only on **core Python developer terminal commands**.

````markdown
# Python Developer Terminal Commands Guide

A practical guide to **important terminal commands for Python developers**.  
These commands help with **running Python programs, managing virtual environments, and installing dependencies**.

---

# 1. Checking Python Installation

### Check Python Version

```bash
python --version
```

or

```bash
python3 --version
```

Example Output

```
Python 3.11.5
```

---

### Locate Python Installation

```bash
which python
```

Example Output

```
/usr/bin/python
```

---

# 2. Running Python Programs

### Run a Python Script

```bash
python app.py
```

or

```bash
python3 app.py
```

---

### Run Python Interactive Shell

```bash
python
```

This opens the Python REPL.

Example

```python
print("Hello World")
```

Exit shell

```
exit()
```

---

# 3. Python Virtual Environments

Virtual environments isolate project dependencies.

---

### Create Virtual Environment

```bash
python -m venv venv
```

This creates a folder named **venv**.

---

### Activate Virtual Environment

#### macOS / Linux

```bash
source venv/bin/activate
```

#### Windows

```bash
venv\Scripts\activate
```

Terminal will show:

```
(venv)
```

---

### Deactivate Virtual Environment

```bash
deactivate
```

---

# 4. Python Package Management

Python uses **pip** for installing packages.

---

### Install Package

```bash
pip install package_name
```

Example

```bash
pip install pandas
```

---

### Install Specific Version

```bash
pip install package_name==1.2.0
```

---

### Upgrade Package

```bash
pip install --upgrade package_name
```

---

### Uninstall Package

```bash
pip uninstall package_name
```

---

### List Installed Packages

```bash
pip list
```

---

### Show Package Details

```bash
pip show package_name
```

Example

```bash
pip show pandas
```

---

# 5. Dependency Management

### Freeze Installed Packages

Creates a list of installed dependencies.

```bash
pip freeze
```

---

### Save Dependencies to File

```bash
pip freeze > requirements.txt
```

---

### Install Dependencies from File

```bash
pip install -r requirements.txt
```

---

# 6. Running Python Modules

Instead of running scripts directly, Python modules can be executed.

```bash
python -m module_name
```

Example

```bash
python -m http.server
```

This starts a simple local web server.

---

# Summary

Important Python developer commands:

```
python
python -m venv venv
source venv/bin/activate
pip install
pip list
pip freeze
pip install -r requirements.txt
```

Mastering these commands helps Python developers **manage environments and dependencies efficiently from the terminal**.
````
