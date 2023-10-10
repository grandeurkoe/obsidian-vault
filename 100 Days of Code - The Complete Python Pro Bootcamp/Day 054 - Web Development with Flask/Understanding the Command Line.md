# Understanding the Command Line

The kernel interacts directly with the computer hardware.

The shell or command line is the interface that allows us to interact with the kernel.

Type `cd` in command prompt to get the current directory. In PowerShell, the command is `pwd`.

Type `dir` to get a list of all files in the current directory. In PowerShell, the command is `ls`.

To change directory type `cd <name-of-directory>`. Press TAB to narrow down the possible files that are accessible from current directory.
```cmd
cd .\Desktop\
```

Type `cd ~` to go back to the root directory.

To create a new directory type `mkdir <name-of-directory>`.
```cmd
mkdir Test
```

To create a file type `New-Item -Path "location-of-file\new-file.extension`
```cmd
New-Item -Path "main.py"
```

To remove a file type `rm <name-of-file>`
```cmd
rm main.py
```

To go back to the previous directory type `cd ..`.

To remove a directory type `Remove-Item "location-of-file\new-file.extension"`.

To remove directories recursively i.e. delete every file in the directory type  `Remove-Item "location-of-file\new-file.extension -Recurse"`.