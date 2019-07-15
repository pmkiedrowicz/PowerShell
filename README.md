# PowerShell
### PS Version
```
$PSVersionTable
```
### Create Folder
```
New-Item -Path 'C:\MyScripts\New Folder' -ItemType Directory
```
### Create File
```
New-Item -Path 'C:\MyScripts\New File.txt' -ItemType File
```
### Copy Folder (specified)
```
Copy-Item 'C:\MyScripts\Test Folder' 'C:\MyScripts\Test Folder2'
```
### Copy Folder (inside choosen folder/recursively)
```
Copy-Item 'C:\MyScripts\Test Folder' -Destination 'C:\MyScripts\Test Folder2'
```
### Copy File (specified)
```
Copy-Item 'C:\MyScripts\text.txt' 'C:\MyScripts\newTextFile.txt'
```
### Copy File (recursively, filtered to .txt files)
```
Copy-Item -Filter *.txt -Path 'C:\MyScripts\newFolder' -Recurse -Destination 'C:\MyScripts\newFolder2'
```
### Delete Folder
```
Remove-Item 'C:\MyScripts\newFolder`
```
### Delete Folder (silent)
```
Remove-Item 'C:\MyScripts\newFolder` -Recurse
```
### Delete File
```
Remove-Item 'C:\MyScripts\text.txt`
```
### Delete File (silent)
```
Remove-Item 'C:\MyScripts\text.txt`
```
### Move Folder (with content)
```
Move-Item C:\MyScripts\newFolder C:\MyScripts\newFolder2
```
### Move File
```
Move-Item C:\MyScripts\text.txt
```
### Rename Folder
```
Rename-Item C:\MyScripts\newFolder C:\MyScripts\newNamedFolder
```
### Rename Item
```
Rename-Item C:\MyScripts\text.txt text2.txt
```
### Read file/get length of it.
```
Get-Content C:\MyScripts\text.txt
(Get-Content C:\MyScripts\text.txt).length
```









































