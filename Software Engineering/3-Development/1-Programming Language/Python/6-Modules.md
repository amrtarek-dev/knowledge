A module is a Python file that contains additional functions, variables, and other kinds of runnable code. A Python library is a collection of modules.

**library** is a collection of modules that provide code users can access in their programs.

## The Python Standard Library
it is an extensive collection of Python code that often comes packaged with Python. It includes a variety of modules, each with pre-built code centered around a particular type of task.

- The `re` module, which provides functions used for searching for patterns in log files
- The `csv` module, which provides functions used when working with .csv files
- The `glob` and `os` modules, which provide functions used when interacting with the command line    
- The `time` and `datetime` modules, which provide functions used when working with timestamps
- `statistics` module which has the `mean()` and `median()` functions

### importing modules

- import an entire module
- import specific function from a module

``` python
import statistics
monthly_failed_attempts = [20, 17, 178, 33, 15, 21, 19, 29, 32, 15, 25, 19]
mean_failed_attempts = statistics.mean(monthly_failed_attempts)
print("mean:", mean_failed_attempts)
# mean: 35.25
median_failed_attempts = statistics.median(monthly_failed_attempts)
print("median:", median_failed_attempts)
# median: 20.5

# Import specific functions
from statistics import mean, median
monthly_failed_attempts = [20, 17, 178, 33, 15, 21, 19, 29, 32, 15, 25, 19]
mean_failed_attempts = mean(monthly_failed_attempts)
print("mean:", mean_failed_attempts)
median_failed_attempts = median(monthly_failed_attempts)
print("median:", median_failed_attempts)
```


## `re`
Regular expression
- `\w` for any alpha-numertic value or you can use `_`
- . matches to all characters, including symbols
- \d matches to all single digits [0-9]
- \s matches to all single spaces 
- \. matches to the period character
- `+` for any repeating (count)
- `{ }` number of repetitions

``` python
import re
email_log = """Email received June 2 form user1@email.com.
			   Email received June 2 from user2@email.com.
			   Email received June 2 from invalid_email@email.com."""
			   
# To get the email in the log
print(re.findall("\w+@\w+\.\w+", email_log))
```

## External libraries
you can also download external libraries and incorporate them into your Python code.
before using them, you need to install them.

``` bash
pip install numpy
```


