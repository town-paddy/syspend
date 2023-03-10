# syspend
This module recursively searches the parent directory from current directory, and calls sys.path.append(directory: SYSPEND_ROOT file exists)

# Usage
In the case, there is a following project.

- project
    - mypackage.py
    - samples
        - sample.py
    - SYSPEND_ROOT  <------- make this file by your self. empty file is ok.

sample.py can import mypackage using syspend.
```python sample1.py
import syspend
import mypackage

if __name__ == '__main__':
    mypackage.hello()
```

## get_path()
get_path() returns the directory where SYSPEND_ROOT exists. 

```python
import syspend

if __name__ == '__main__':
    syspend.get_path()   # output ex: D:\project\samples
    syspend.get_path('ALT_ROOT')   # returns directory where ALT_ROOT file exists.
    syspend.get_path('SYSPEND_ROOT', '../tools')   # output ex: D:\project\tools
```

## syspend()
syspend() calls sys.path.append(directory: SYSPEND_ROOT file exists). 
when calling import syspend, syspend() is automatically called.

```python
import syspend

if __name__ == '__main__':
    syspend.syspend('ALT_ROOT')   # sys.path.append('directory: ALT_ROOT file exists')
    syspend.syspend('SYSPEND_ROOT', '../tools')   # sys.path.append('D:\project\tools')
```

# Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Please make sure to update tests as appropriate.

# License
[MIT](https://choosealicense.com/licenses/mit/)