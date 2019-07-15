# PowerShell
PS Version
'''
$PSVersionTable
'''
Create Folder
'''
New-Item -Path 'C:\MyScripts\New Folder' -ItemType Directory
'''
Create File
'''
New-Item -Path 'C:\MyScripts\New File.txt' -ItemType File
'''
Copy Folder (specified)
'''
Copy-Item 'C:\MyScripts\Test Folder' 'C:\MyScripts\Test Folder2'
'''
Copy Folder (inside choosen folder/recursively)
'''
Copy-Item 'C:\MyScripts\Test Folder' -Destination 'C:\MyScripts\Test Folder2'
'''