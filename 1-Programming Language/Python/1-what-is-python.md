# What is Python?

Python is a high-level interpreted programming language with an object-oriented structure. It offers a vast number of libraries that make complex implementations easy, and good features that makes it the first choice to implement a lot of applications.

## Hello Python
Let's start with a simple "Hello, Python!" example. open your preferred code editor and put the below code in it then save it as file with the name **hello.py**:

```python
print("Hello, world!")
```

## Running Python

Python has two versions: **Python 2** and **Python 3**. In this article, we will focus on **Python 3**.

To install the Python interpreter on a Linux OS, you can use the default system installation or install it for Debian-based Linux using the following command:

```bash
$ sudo apt install python3
```
For security and compatibility reasons, it is recommended to run Python in a **virtual environment**. This allows you to create a temporary environment specific to your project and its required libraries.

### Virtual Environment

To install a virtual environment on Linux, use the following command:

```bash
sudo apt install python3-venv
```
To create a virtual environment named **"myenv"**, use the following command:

```bash
python3 -m venv myenv
```
To activate the virtual environment, use the following command:

```bash
source ./myenv/bin/activate
```
## Writing Python Code

There are two ways to write Python code:

### Interactive Python (REPL)

**REPL** stands for **Read** => **Evaluate** => **Print** => **Loop**. It allows you to run individual Python statements sequentially.
You can enter the REPL mode by running **python3** command in shell
```bash
python3

Python 3.9.6 (default, Feb  3 2024, 15:58:27) 
[Clang 15.0.0 (clang-1500.3.9.4)] on darwin
Type "help", "copyright", "credits" or "license" for more information.
>>>
```
Then you can run any python command and see the output of it immediately

For example:

```python
>>> print("Hello, world!")
```
### Python Scripts

The second way that you can write Python code in script files with the **".py"** extension and run them using the Python interpreter. To run a script named **"example.py"**, use the following command:

```bash
python3 example.py
```

In Python, spacing and **indentation** are crucial because they define the structure of code blocks. The indentation level determines which statements belong to a specific block.

### Python PEPs:

Python follows a style guide and best practices known as **[Python Enhancement Proposals (PEPs)](https://www.python.org/dev/peps)**. For example, PEP8 provides guidelines for code style and indentation.

Now, let's dive into the first lesson.