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


# CMDlets

### Create unique CMDlets
```
$list = "one","two","two","three","four","five"    //create variable list and assign values
$list | sort | get-unique                          //get the list, sort it and get unique values
```
### Measure-object
```
Get-Content text.txt | Measure-Object -Character -Line -Word
```
### Get no. of childs
```
Get-ChildItem | Measure-Object
```
### Compare
```
Compare-Object -ReferenceObject $(Get-Content test.txt) -DifferenceObject $(Get-Content test1.txt)                 //shows different content
Compare-Object -ReferenceObject $(Get-Content test.txt) -DifferenceObject $(Get-Content test1.txt) -IncludeEqual   //shows different and equal content
```
### Format List
```
$A = Get-ChildItem .\*.txt    //Create variable contains all .txt files     
Format-List -InputObject $A   //List properties of all files of variable

Get-Service | Format-List
```
### Format Wide
```
$A = Get-ChildItem .\*test*                   //Create variable contain all files named *test*
Format-Wide -InputObject $A                   //List all the files of variable
Format-Wide -InputObject $A -Property Length  //Shows the content length of these files
```
### Where-Object
```
Get-Service | Where-Object {$_.Status -eq "Stopped"}          //Show the list of services "Stopped"
Get-Process | Where-Object {$_.ProcessName -Match "^p.*"}     //Get the list of process matching regex
```
### Get-ChildItem
```
Get-ChildItem -Name
ls -Name
```
### For-Each
```
123,456,789 | ForEach-Object -Process {$_/50}                           //divide numbers by 50 and print it
"one,two,three,four","five,six,seven" | ForEach-Object {$_.Split(",")}  //takes two objects, splits by regex and print it
```
### Start-Sleep
```
Start-Sleep -Seconds 15       //suspend console fot 15seconds
```
### Read-Host
```
$var = Read-Host "Type a variable"  //ask for a variable and assign it to variable $var
$var                                //print variable $var
```
### Select-Object
```
Get-Process | Select-Process -Property ProcessName, Id, WS -Last 5  //get processes, select properties, print last 5
"a","b","c","a","a","a" | Select-Object -Unique                     //get unique values of arr
```
### Sort-Object
```
Get-Process | Sort-Object -Property WS | Select-Object -Last 5  //gets process, sort it by property WS and select last 5
"h","s","a","o","z","y" | Sort-Object                           //sort array
```
### Write-Warning
```
Write-Warning "CPU's are reaching maximum usage!"
```
### Write-Host
```
Write-Host (1,2,3,4,5,6,7) -Separator " -> " -ForegroundColor Red -BackgroundColor White
```
### Invoke-Item
```
Invoke-Item text.txt    //open file with default editor
```
### Invoke-Expression
```
$var = 'Get-Process'     //create variable
Invoke-Expression $var   //use variable data as command
```
### Measure-Command
```
Measure-Command {Get-EventLog "Windows PowerShell"}  //measure time of executing command
```
### Invoke-History
```
Invoke-History  //run last command again
```
### Add-History/Get-History/Get-Culture
```
Get-History -Count 5 | Add-History       //select last 5 commands and add them to history
Get-History
Get-Culture                              //gets current culture set in windows
```























