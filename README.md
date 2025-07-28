# 🐍 Build an Artifact - (Python)

After writing your Python code, you need to **package** it for easy deployment and distribution. Using **pip** and virtual environments on Ubuntu Linux, you can create a simple Python artifact that outputs "Hello World". This guide shows how to do this and how to open the project in IntelliJ IDEA.

---

## 📆 What is an Artifact?

An **artifact** in Python packaging is a distributable package containing:

- Your source code
- Required dependencies specified in `requirements.txt` or `setup.py`
- Metadata for installation

### ➡️ Why Artifacts Matter:

- Easy installation via `pip`
- Share your package on PyPI or internal repos
- Consistent environment setup across machines

---

## 🧰 Build Tools for Python

Python packaging and artifact creation can be done using:

- `pip` — Python package installer
- `venv` — built-in virtual environment manager
- `setuptools` and `wheel` — for building packages

---

### **Sample Workflow for Hello World Python Package **

![Python](Images/python.gif)

1.  Create and navigate to your project directory

```bash
mkdir hello_world_python
cd hello_world_python
```

2. Set up a virtual environment (recommended)

```bash
python3 -m venv venv
source venv/bin/activate
touch hello.py
touch setup.py
```

3. Create your Python source file

```python
# hello.py
def main():
    print("Hello World")

if __name__ == "__main__":
    main()
```

4. Create setup.py for packaging

```python
# setup.py
from setuptools import setup

setup(
    name="hello_world_python",
    version="0.1",
    py_modules=["hello"],
    entry_points={
        "console_scripts": [
            "hello-world=hello:main",
        ],
    },
)
```

5.  Install build tools inside your virtual environment

```bash
source venv/bin/activate
sudo apt install pip
pip install --upgrade pip setuptools wheel
```

6.  Build the package artifact

```bash
python setup.py sdist bdist_wheel
```

- This creates distribution files inside the dist/ folder (.tar.gz and .whl files).

7. zip build folder

```bash
zip <desired zip file name> build
```

7. Unzip build folder

```bash
unzip <zip file name> build
cd <where you copy or move the file>/build/lib
python3 hello.py
```

- Expected output: Hello World

---

## 🧪 How It Works – Build Process Summary

1. **Install Dependencies** (via `npm install`)
2. **Package Code** into a `.zip` (or other format)
3. **Store Artifact** for deployment or sharing

---

## 📌 Final Thoughts

Understanding **build tools** and **artifact packaging** in Node.js is crucial for DevOps engineers to automate packaging, ensure deployment consistency, and manage dependencies effectively. With the right tools and artifact strategy, you streamline software delivery across any environment.

🧑‍💻 _Created by Rico John Dato-on_
🔗 [LinkedIn](https://www.linkedin.com/in/rico-john-dato-on) • [Portfolio](https://ricodatoon.netlify.app)

```

```
