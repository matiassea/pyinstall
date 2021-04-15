# Pyinstall
Pyinstall observacion y comentarios
Instalacion pip install pyinstaller


### Hook de pyintall

Aca esta Hook de Pyinstall para pandas
Estos se encuentran en la carpeta C:\Python37\Lib\site-packages\PyInstaller\hooks
Para mas consulta:
* https://pyinstaller.readthedocs.io/en/stable/hooks.html
* https://pythonhosted.org/PyInstaller/#using-pyinstaller

Listado de hooker:
* http://pydoc.net/PyInstaller/3.3.1/PyInstaller.hooks.hook-_tkinter/
* https://github.com/pyinstaller/pyinstaller
* https://pythonhosted.org/PyInstaller/spec-files.html


A hook file is a Python script, and can use all Python features. 
It can also import helper methods from PyInstaller.utils.hooks and useful 
variables from PyInstaller.compat. These helpers are documented below.

```
from PyInstaller.utils.hooks import collect_submodules

Pandas keeps Python extensions loaded with dynamic imports here.

hiddenimports = collect_submodules('pandas._libs')
```

### Pandas en Pyinstaller

hiddenimports = [
    'pandas._libs.tslibs.timedeltas',
    'pandas._libs.tslibs.nattype',
    'pandas._libs.tslibs.np_datetime',
    'pandas._libs.skiplist',
]

### Ejemplo de links
An example could be pyinstaller.exe --onefile --windowed --icon=app.ico app.py where:
* https://pythonhosted.org/PyInstaller/usage.html


--onefile: Create a one-file bundled executable.
--windowed: Parameter to chooseif you are compiling in Mac OS X or Windows
--icon= : Choose the file to use as icon for file.


### Spec files

* https://pyinstaller.readthedocs.io/en/stable/spec-files.html#using-spec-files

maseva2(def).spec

![spec](https://user-images.githubusercontent.com/17385297/75021839-d7664f00-5473-11ea-974d-50ad9c70c840.png)

#### Codigo en CMD
pyinstaller –onefile XXXX.spec YYY.py => se llama al archivo .spec y al archivo a transformar

#### Ejemplo
* pyinstaller –onefile maseva2(def).spec maseva2.py
* C:\Python37\Scripts> pyinstaller --onefile maseva2(def).spec maseva2.py
* C:\Python37\Scripts> pyinstaller --windowed --onefile maseva2(def).spec maseva2.py
* C:\Python37\Scripts\dist>maseva2.exe
* C:\Python37\Scripts> pyinstaller maseva2(def).spec

# Create only a single file (slower to run, easier to distribute)
pyinstaller hello.py -F

# Specify the icon file to use
pyinstaller hello.py --icon=path/to/icon.ico

* https://www.devdungeon.com/content/pyinstaller-tutorial

