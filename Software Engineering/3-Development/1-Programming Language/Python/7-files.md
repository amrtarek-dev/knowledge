To open a file called "update_log.txt" in Python
``` python
with open("update_log.txt", "r") as file:
```

- `with` handles errors and manages external resources when used with other functions.
	- It will then manage the resources by closing the file after exiting the with statement.
- `open()` function opens a file in Python.
- `r` which indicates that you want to read the file
	- `w` if you want to write
	- `a` if you want to append to a file
When you open a file using with open(), you must provide a variable that can store the file while you are within the with statement.
- `as` assigns a variable that references another object.

Then you can read the file
``` python
with open("update_log.txt", "r") as file:
    updates = file.read()
print(updates)
```

If you want to write in file, you need to open it in write mode then write the data
``` python
line = "jrafael,192.168.243.140,4:56:27,True"
with open("access_log.txt", "a") as file:
    file.write(line)
```