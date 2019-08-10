# py2so
[English](https://github.com/cckuailong/py2so/blob/master/README.md)
[中文](https://github.com/cckuailong/py2so/blob/master/README_zh.md)

## What is py2so
1. py2so is tool to change the .py to .so, you can use it to hide the source code of py
2. py2so can transfer a single file, more of this, it can certainly transfer the whole project at one time!
3. The .so file generated by the .py file can be called by the main func as "from module import * "
4. py2so can detect the .py file and transfer to .so file, also you can determin which file or directory you don't want to change
5. You can also determin whether keep the source py.
6. Considering the probality of the user's fault to delete the source .py file, py2so provide a copy of the source to avoid it, the name of it tends to be end with "_old"
7. py2so work well with python2 and python3, py2 --> py2so.py    py3 --> py2so_py3.py

## How to config it
```
sudo bash config.sh
```
It will ask some space to install some necessary libraries

## How to use py2so
#### Python2
```
Usage: 
  python py2so.py [options] ...
```

```
Options:
  -v,  --version    Show the version of the py2so
  -h,  --help       Show the help info
  -p,  --py         Python subversion, default value == 7
                    Example: -p 7  (means you use python2.7)
  -d,  --directory  Directory of your project (if use -d, you change the whole directory)
  -f,  --file       File to be transfered (if use -f, you only change one file)
  -c,  --clear      Clear the origin .py
                    (Warning: the option will delete the .py, but don't be so serious, py2so will give the project a copy)
  -m,  --maintain   List the file or the directory you don't want to transfer
                    Note: The directories should be surrounded by '[]', and must be the relative path to -d's value 
                    Example: -m __init__.py,setup.py,[poc,resource,venv,interface]
```

```
Example:
  python py2so.py -f test_file.py
  python py2so.py -d ../test_dir -m __init__.py -c
  python py2so.py -d /home/test/test_dir -m [poc/,resource/,venv/,interface/]
  python py2so.py -d test_dir -m __init__.py,setup.py,[poc/,resource/,venv/,interface/] -c
```
#### Python3
```
Usage: 
  python py2so_py3.py [options] ...
```

```
Options:
  -v,  --version    Show the version of the py2so_py3
  -h,  --help       Show the help info
  -p,  --py         Python subversion, default value == 7
                    Example: -p 7  (means you use python3.7)
  -d,  --directory  Directory of your project (if use -d, you change the whole directory)
  -f,  --file       File to be transfered (if use -f, you only change one file)
  -c,  --clear      Clear the origin .py
                    (Warning: the option will delete the .py, but don't be so serious, py2so_py3 will give the project a copy)
  -m,  --maintain   List the file or the directory you don't want to transfer
                    Note: The directories should be surrounded by '[]', and must be the relative path to -d's value 
                    Example: -m __init__.py,setup.py,[poc,resource,venv,interface]
```

```
Example:
  python py2so_py3.py -f test_file.py
  python py2so_py3.py -d ../test_dir -m __init__.py -c
  python py2so_py3.py -d /home/test/test_dir -m [poc/,resource/,venv/,interface/]
  python py2so_py3.py -d test_dir -m __init__.py,setup.py,[poc/,resource/,venv/,interface/] -c
```



The whole project before:

![demo1](https://github.com/cckuailong/py2so/blob/master/img/1.png)

After py2so:

![demo2](https://github.com/cckuailong/py2so/blob/master/img/2.png)
