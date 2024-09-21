There are multiple ways to setup a Python virtual environment.

### Virtualenv
#### Installation
```
pip install virtualenv
```

```
python3 -m venv <virtual-environment-name>
```

```
source <virtual-environment-name>/bin/activate
```

### Pyenv-virtualenv
#### Installation
```
pyenv virtualenv <python-version> <environment-name>
```

```
pyenv activate <environment-name>
```

### Note
If using an IDE like VSCode, make sure to change the interpreter by using `Cmd + Shift + P`

### Reference
- [Virtualenv](https://www.freecodecamp.org/news/how-to-setup-virtual-environments-in-python/)
- [Pyenv-virtualenv](https://medium.com/@adocquin/mastering-python-virtual-environments-with-pyenv-and-pyenv-virtualenv-c4e017c0b173)