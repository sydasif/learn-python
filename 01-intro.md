# Introduction to Python

Computer programming, or coding, involves instructing a computer to perform tasks using a language it understands. Since computers cannot think independently, they require detailed instructions for tasks, decision-making, data handling, and error management. Coding can be simple to learn, akin to writing, but excelling in it, like poetry, requires additional skills and effort.

Programming mirrors real-life processes by breaking down actions into logical steps a computer can follow. For example, making instant coffee involves gathering resources, verifying conditions, performing tasks in sequence, and completing a procedure—similar to how programming structures tasks and decisions.

Good code is efficient, readable, simple, scalable, and easy to modify and test. Developing such skills takes time, but anyone can learn programming by taking the first steps. Everyday activities often resemble programming, even if we aren't aware of it.

## A brief introduction to programming

Programming involves instructing a computer to perform tasks by managing objects, which represent real-world entities like people, cars, or items. Objects in Python have properties (characteristics) and methods (actions). For example, a person object might have properties like name or age and methods like speak or walk. Python objects have a unique ID, a type defining their operations, and a value, which may be mutable or immutable. By naming objects (variables), we can manipulate data, evaluate conditions, and perform actions. Python, as a language, helps us create, use, and manage these objects to build software representing real-world systems.

### Setting up the environment

On our machines, the latest Python version is as shown below:

```shell
<> $ python
Python 3.13.1 (main, Dec  9 2024, 00:00:00) [GCC 14.2.1 20240912 (Red Hat 14.2.1-3)] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> import sys
>>> print(sys.version)
3.13.1 (main, Dec  9 2024, 00:00:00) [GCC 14.2.1 20240912 (Red Hat 14.2.1-3)]
```

The examples in this book use Python 3.13, released on December 2, 2024. Ensure you use this version to follow along and run the source code provided.

### Python virtual environments

Virtual environments in Python allow you to create isolated environments for projects, preventing dependency conflicts. For example, if Project X uses Django 4.2 and Project Y requires Django 5.0, virtual environments let you work on both without issues. Each environment contains the necessary executables and libraries for a specific project. Starting with Python 3.5, the recommended method to create virtual environments is the `venv` module, as described in the [official documentation](https://docs.python.org/3/library/venv.html). Alternatively, you can use the third-party package [virtualenv](https://virtualenv.pypa.io).

#### First virtual environment

Creating and using a virtual environment is straightforward. Follow these steps:

- Open a terminal and navigate to your project root folder. Create a project folder (e.g., `my-project`) and switch to it:

```shell
<> $ mkdir my-project
<> $ cd my-project/
```

- Create a virtual environment (e.g., `.venv`) using the `venv` module:

```shell
<> my-project$ python -m venv .venv
```

- Activate the virtual environment (commands differ by OS):

```shell
<> my-project$ source .venv/bin/activate  # Linux/macOS
```

- Verify the Python version used in the virtual environment:

```shell
(.venv) <> my-project$ python
Python 3.13.1 (main, Dec  9 2024, 00:00:00) [GCC 14.2.1 20240912 (Red Hat 14.2.1-3)] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> exit()
```

- Deactivate the virtual environment when done:

```shell
(.venv) <> my-project$ deactivate
<> my-project$
```

This ensures you work with isolated environments for different projects without version conflicts. Also notice how the prompt changes after we activate the
virtual environment, showing its name on the left (and how it disappears when we deactivate it).

#### Installing third-party libraries

To install third-party libraries using a `requirements.txt` file, follow these steps:

- Activate the virtual environment:

```shell
<> my-project$ source test/bin/activate
```

- Review the `requirements.txt` file contents:

```shell
(.venv) <> my-project$ cat requirements.txt
django==5.0.3
requests==2.31.0
```

- Install the libraries listed in the file:

```shell
(.venv) <> my-project$ pip install -r requirements.txt
Collecting django==5.0.3 (from -r requirements.txt (line 1))
    Downloading Django-5.0.3-py3-none-any.whl.metadata (4.2 kB)
Collecting requests==2.31.0 (from -r requirements.txt (line 2))
    Downloading requests-2.31.0-py3-none-any.whl.metadata (4.6 kB)

... more collecting omitted ...

Installing collected packages: urllib3, sqlparse, idna, charset-normalizer, certifi, asgiref, requests, django
Successfully installed asgiref-3.8.1 certifi-2024.12.14 charset-normalizer-3.4.1 django-5.0.3 idna-3.10 requests-2.31.0 sqlparse-0.5.3 urllib3-2.3.0

[notice] A new release of pip is available: 24.2 -> 24.3.1
[notice] To update, run: pip install --upgrade pip
(.venv) <> my-project$
```

This process installs the listed libraries along with their dependencies. For more information, check the [pip user guide](https://pip.pypa.io/en/stable/user_guide/). You can also directly install packages with commands like `pip install django`.

## How to run a Python program

There are a few different ways in which you can run a Python program.

### Running Python scripts

Python excels as a scripting language, making it ideal for automating tasks such as data parsing, file management, and configuration updates. Developers often create scripts for routine tasks like cleaning expired database sessions, which can be automated using tools like Cron to run scripts at scheduled times. Python scripts save time by handling repetitive tasks efficiently and promoting automation.

### Running the Python interactive shell

Running Python in the interactive shell is a straightforward way to test code and debug quickly. To access it, activate your virtual environment and type `python` in the console. You'll see a prompt like this:

```shell
(.venv) <> my-project$ python
Python 3.13.1 (main, Dec  9 2024, 00:00:00) [GCC 14.2.1 20240912 (Red Hat 14.2.1-3)] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>>
```

You can perform calculations or write code interactively:

```python
>>> 3 + 7
10
>>> 10 / 4
2.5
```

The shell handles large computations easily, which may require special libraries in other languages like Java or C++. For beginners, Python’s IDLE offers a graphical alternative with additional features and is available with Python installers.

Python can be run as a service, allowing it to function as a script or application. It also supports creating **Graphical User Interfaces (GUIs)** using various frameworks.

### GUI Development in Python

One popular library is **Tkinter**, which comes bundled with Python. Tkinter is an object-oriented interface for Tk, enabling the creation of rich, native applications for Windows, Linux, macOS, and more. Here's an example of frameworks for GUI development:

1. **Tkinter**: Pre-installed with Python.
2. **PyQT/PySide**: Powerful frameworks for cross-platform GUIs.
3. **wxPython**: Another cross-platform library.
4. **Kivy**: Focused on multi-touch applications.

For more information, check Python's GUI FAQ:- [What GUI toolkits exist for Python?](https://docs.python.org/3/faq/gui.html)

When choosing a GUI framework, ensure it:

- Offers required features for your project.
- Supports all necessary platforms.
- Has a strong, active community.
- Wraps easily accessible graphic drivers or tools.

### How is Python code organized?

Python code is organized into files, and when a file has the `.py` extension, it's considered a **Python module**. For larger applications, it's impractical to have all the code in a single file, so Python allows you to organize code into **packages**, which are essentially directories containing multiple modules.

### Example Structure

```bash
example
├── core.py
├── run.py
└── util
    ├── __init__.py
    ├── db.py
    ├── maths.py
    └── network.py
```

- **core.py** and **run.py** are modules.
- **util** is a package containing modules for database tools (`db.py`), math functions (`maths.py`), and network operations (`network.py`).
- The **`__init__.py`** file tells Python that `util` is a package, although it's not mandatory anymore, it's recommended to include it.

Without organizing code into modules and packages, it becomes more difficult to understand and maintain large applications. An unorganized example might look like this:

```bash
files_only
├── core.py
├── db.py
├── maths.py
├── network.py
└── run.py
```

This structure is harder to interpret, especially in large-scale applications.
