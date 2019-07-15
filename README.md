# Files and Folders

### PS Version
```
$PSVersionTable
```
### Create Folder
```
New-Item -Path 'C:\ps\New Folder' -ItemType Directory
```
### Create File
```
New-Item -Path 'C:\ps\New File.txt' -ItemType File
Set-Content -Path 'C:\ps\New File.txt' 'Content of this file'
```
### Copy Folder (specified)
```
Copy-Item 'C:\ps\Test Folder' 'C:\ps\Test Folder2'
```
### Copy Folder (inside choosen folder/recursively)
```
Copy-Item 'C:\ps\Test Folder' -Destination 'C:\ps\Test Folder2'
```
### Copy File (specified)
```
Copy-Item 'C:\ps\text.txt' 'C:\ps\newTextFile.txt'
```
### Copy File (recursively, filtered to .txt files)
```
Copy-Item -Filter *.txt -Path 'C:\ps\newFolder' -Recurse -Destination 'C:\ps\newFolder2'
```
### Delete Folder
```
Remove-Item 'C:\ps\newFolder`
```
### Delete Folder (silent)
```
Remove-Item 'C:\ps\newFolder` -Recurse
```
### Delete File
```
Remove-Item 'C:\ps\text.txt`
```
### Delete File (silent)
```
Remove-Item 'C:\ps\text.txt`
```
### Append Text Data
```
Set-Content C:\ps\text.txt 'Hello'      //set new content, removes old one
Add-Content C:\ps\text.txt 'World!'     //add content in new line
```
### Erase Content
```
Clear-Content C:\ps\text.txt
```
### Move Folder (with content)
```
Move-Item C:\ps\newFolder C:\ps\newFolder2
```
### Move File
```
Move-Item C:\ps\text.txt
```
### Rename Folder
```
Rename-Item C:\ps\newFolder C:\ps\newNamedFolder
Rename-Item C:\ps\newFolder newNamedFolder
```
### Rename Item
```
Rename-Item C:\ps\text.txt C:\ps\text2.txt
Rename-Item C:\ps\text.txt text2.txt
```
### Read file/get length of it.
```
Get-Content C:\ps\text.txt
(Get-Content C:\ps\text.txt).length
```
### Test Existence (true/false)
```
Test-Path c:\ps\notExisted
Test-Path c:\ps\notExisted.txt
```


# Date and Time

### Get/Set Date
```
Get-Date
Get-Date -DisplayHint Date
Get-Date -DisplayHint Time
Set-Date -Date (Get-Date).AddDays(1)

$timeToAdd = New-TimeSpan -Minutes 60
Set-Date -Adjust $timeToAdd
```




































