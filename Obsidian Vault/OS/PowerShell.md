
### cmdlet

A _cmdlet_ (pronounced "command-let") is a compiled command. These are are named according to a **verb**-**noun** naming standard. You can see the list of approved verbs by using the `Get-Verb` cmdlet.

```powershell
Get-Command -Verb Get -Noun alias*
```

```powershell
Get-Help Get-Help
```

To know more about what's being returned and how you can modify what is returned, you can use the command `Get-Member`. The `Get-Member` cmdlet is meant to be _piped_ on top of the command you run so that you can filter the output. A typical command-line invocation of `Get-Member` might look like the following example:

```powershell
Get-Process -Name 'firefox' | Get-Member
```

### Scripting

Overview:
* Variables
* Functions
* Flow control
* Loops
* Error Handling
* Expressions
* .NET integration

#### Variables

```powershell
# PI.ps1
$PI = 3.14
Write-Host "The value of `$PI is $PI" # Prints Here is $PI and its value is 3.14
Write-Host "An expression $($PI + 1)" # Prints An expression 4.14
```

Arrays
```powershell
$array = @("Text", 49, 3.14)
$array.GetType() # System.Array
$array.Count # 3
$array # Returns the whole array
$array.IsFixedSize # True
$array.Add("Test") # Error "Collection was of a fixed size"
$array += "Test"
$array[3] # Returns "Test"
$array = $array -ne 49
$array # Returns everything beside 49

  

#$list = [System.Collections.ArrayList]@() # Unefficient, does one more step to cast the Array to ArrayList
$list = New-Object -TypeName System.Collections.ArrayList
$list.GetType() # ArrayList
$list.IsFixedSize # false
$list.Add("Text1") # Adds "Text1" to list and return position 0
[void]$list.Add("Text2") # Adds "Text2" to list and does not return position 1
$list.AddRange(@(10, 1.1902, "Text3", "Text1"))
$list[3] # Return 1.1902
$list.Remove("Text1") # Removes first instance of "Text1"
```
Array efficiency
```powershell
# Values differ between CPUs
$arraySpeed = @()
Measure-Command -Expression {@(0..50000).ForEach({$arraySpeed += $_})} # ~3.7 seconds

$listSpeed = New-Object -TypeName System.Collections.ArrayList
Measure-Command -Expression {@(0..50000).ForEach({$listSpeed.Add($_)})} # ~0.16 seconds
Measure-Command -Expression {$listSpeed.AddRange(@(0..50000))} # ~0.016 seconds
```

Hash Table
```powershell
# Keys are unique, values are not
$hashTable = @(
   name='Danny'
   key1=10
   pi=3.14
   key2=$true
)
$hashTable.GetType() # Hashtable
$hashTable.Keys # name, key1, pi, key2
$hashTable.Values # Danny, 10, 3.14, true
$hashTable.pi # 3.14
$hashTable['pi'] # 3.14
$hashTable.ContainsKey('key4') # false
$hashTable.ContainsKey('key2') # true
$hashTable.ContainsValue(3) # false
$hashTable.ContainsValue(3.14) # true

$hashTable.Add('key3', 'test new value') # key3 is added with specified value
$hashTable['key4']="added with square bracket"
$hashTable.key5="added with dot notation"
$hashTable.Remove('pi')
```

Custom  Object
```powershell
$employee = New-Object -Type PSCustomObject
Add-Member -InputObject $employee -MemberType NoteProperty -Name 'EmployeeID' -Value '14578'
Add-Member -InputObject $employee -MemberType NoteProperty -Name 'FirstName' -Value 'Danny'

$employee # Returns a table with 'Name' as header and 'Value' as it's members
$employee.FirstName # Danny

Get-Member -InputObject $employee # Returns all members of 'employee': methods (ex: GetType), properties

$employee2=[PSCustomObject]@{ # Creates hashtable and converts into object
   EmployeeID='14051'
   FirstName='John'
}
```

Scope:
* Global
* Script
* Local

Parameter

```powershell
# CreateFile.ps1

Param(
   [Parameter(Mandatory, HelpMessage = "Please provide a valid path")]
   [string]$Path
)
# [Parameter(Mandatory)] optional decorator to make the selected paramater mandatory.
# [string] optional to set a type for parameter.
New-Item $Path
Write-Host "File created at path $Path"
```
```powershell
# Usage
./CreateFile.ps1 -Path './newfile.txt' # File ./newfile.txt was created.
./CreateFile.ps1 -Path './anotherfile.txt' # File ./anotherfile.txt was created.
```

### Flow control

```powershell
Param(
   [Int]$Value
)
If ($Value -lt 0) 
{
  Write-Host "Is negative"
} ElseIf ($Value -eq 3)
{
  Write-Host "Value is 3"
} Else {
  Write-Host "Is Positive"
}
```

### Error handling

```powershell
Try {
     # Do something with a file.
   } Catch [System.IO.IOException] {
     Write-Host "Something IO went wrong: $($_.exception.message)"
   }  Catch {
     Write-Host "Something else went wrong: $($_.exception.message)"
   }
```