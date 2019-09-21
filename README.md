# Bash vs PowerShell
Cheatsheet with syntax comparison between Bash and Powershell


## Conditions

### Bash

```bash
if condition ; then
    # Do something
elif other_condition ; then
    # Do something
else
    # Do something
fi
```

### PowerShell

```powershell
if(condition)
{
    # Do something
}
elseif(other_condition)
{
    # Do something
}
else
{
    # Do something
}
```

## Checking if string is empty

### Bash

```bash
[[ -z "$str" ]]  #True if length of string is zero
[[ -n "$str" ]]  #True if length of string is non-zero
```

### PowerShell
```powershell
[string]::IsNullOrEmpty($stringVariable)  #True if string is null or empty
-not [string]::IsNullOrEmpty($stringVariable) #True if string is not null and not empty
```

## Checking if path exists

### Bash

```bash
[[ -e "$path" ]]  #Returns true if the path exists.
[[ -f "$path" ]]  #Returns true if the path exists and is a regular file
[[ -d "$path" ]]  #Returns true if the path exists and is a directory
```

### PowerShell
```powershell
Test-Path $path                     #Returns true if the path exists.           
Test-Path $path -PathType Leaf      #Returns true if the path exists and is a regular file
Test-Path $path -PathType Container #Returns true if the path exists and is a directory
```


## Get the length of the variable

### Bash

```bash
${#string_variable}   # Length of the string variable
${#array_variable[@]} # Length of the array
```

### PowerShell
```powershell
$string_variable.length  # Length of the string variable
$array_variable.length   # Length of the array
```

## Replace a part of the string

### Bash

```bash
"${string_variable/what_replace/replace_with}"
```

### PowerShell
```powershell
$string_variable -replace "what_replace","replace_with"
```

## For loop

### Bash

```bash
for (( i=1; i<=10; i++ )); do 
    # do something
done
```

### PowerShell
```powershell
for($i=0; $i -lt 10; $i++)
{
    # do something
}
```

## Foreach loop

### Bash

```bash
for element in "${array[@]}"; do
     # do something
done
```

### PowerShell
```powershell
foreach($element in $array)
{
    # do something
}
```

## Case statement

### Bash

```bash

case $var in
1)
    # do something
;;
2)
    # do something
;;
3)
    # do something
;;
esac
```

### PowerShell
```powershell
switch ($var) {
    1  {
       # do something
       break
    }
    2  {
       # do something
       break
    }  
    default {
       # do something
       break
    }
}
```
