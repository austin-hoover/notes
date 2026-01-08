# Terminal


## Add prefix to all files in directory.
```
for f in * ; do mv -- "$f" "fig_$f" ; done
```


## Delete all files with extension ".pyc"
```
find . -name "*.pyc" -exec rm -f {} \;
```


## Delete all ".DS_Store" files in directory recursively
```
find . -type f -name "*.DS_Store" -exec rm -rf {} \;
```


## Delete all ".ipynb_checkpoints" folders in directory recursively
```
find . -type d -name "*.ipynb_checkpoints" -exec rm -rf {} \;
```


## Make all file names lowercase.
```
for f in *; do mv "$f" "$f.tmp"; mv "$f.tmp" "`echo $f | tr "[:upper:]" "[:lower:]"`"; done
```


## Open program using Rosetta emulator (https://www.bigbinary.com/books/learn-rubyonrails-book/setting-up-mac).

* Right click on /Applications/Utilities/Terminal.
* Open info and check "open using Rosetta".
* Restart Terminal.
* Type "arch" to verify. If Rosetta is enabled, it will print "i386". Otherwise it will print "arm64".


## Pass the rest of the command line arguments to script in bash.
```
python $1 $2 "${@:3}"
```


## Permanently add to python path
```
export PYTHONPATH="${PYTHONPATH}:/my/other/path"
```


## Remove python version
```
sudo rm -rf /Library/Frameworks/Python.framework/Versions/${python_version_number}/
sudo rm -rf "/Applications/Python ${python_version_number}/"
cd /usr/local/bin && ls -l | grep "/Library/Frameworks/Python.framework/Versions/${python_version_number}" | awk '{print $9}' | sudo xargs rm
```


## Zip files
```
zip -r mydir.zip mydir
```


## Zip files without compression
```
zip -0 -r mydir.zip mydir
```

