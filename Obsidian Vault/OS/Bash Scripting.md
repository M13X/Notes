
# Bash Scripting
## Variables

| Command               | Description                                                                                   |
| --------------------- | --------------------------------------------------------------------------------------------- |
| `name=value`          | Assign variable `name` a `value`                                                              |
| `${name}`             | Access the value of variable `name`                                                           |
| `unset <variable>`    | Removes the value of variable                                                                 |
| `${#variable}`        | Number of characters inside variable                                                          |
| `${var:number}`       | Get substring starting from position `number`                                                 |
| `${var:begin:length}` | Substring starting from `begin` + `length`                                                    |
| `${var: -number}`     | Get the last `number` characters of string                                                    |
| `${var: -num:length}` | Get substring from last `num` characters for `lenght`                                         |
| `$(command)`          | Command expansion. Can be used inside another command<br>or to store its result in a variable |
### Variable manipulation

Can use Wildcards for `substring` to enhance functionality

| Command            | Description                                  |
| ------------------ | -------------------------------------------- |
| `${var#substring}` | Removes `substring` from beginning for `var` |
| `${var%substring}` | Removes `substring`from the end for `var`    |

## Read

| Command                     | Description                                                    |
| --------------------------- | -------------------------------------------------------------- |
| `read <variable>`           | Terminal waits for input and assigns it to `variable`          |
| `read -p <text> <variable>` | Prints `text` and then waits for input to assign to `variable` |
| `read`                      | Value can be found inside `$REPLY`                             |

# Script

> [!WARNING]
> Beware of spaces for each command.
## If-conditions

General

| Symbol        | Description |
| ------------- | ----------- |
| `! <command>` | Negate      |

### String

| Symbol | Description         |
| ------ | ------------------- |
| `==`   | Equals              |
| `!=`   | Does not equal      |
| `-z`   | String is empty     |
| `-n`   | String is not empty |

```bash
# Tells the system that this is a bash script
#! /bin/bash

# Define variables
my_str="Hello"

# Check if string is Hello
if [ "$my_str" == "Hello"]; then
	echo "True"
# Check if string is empty
elif [ -z "$my_str" ]; then
	echo "String empty"
# Check if string is not empty
elif [ -n "$my_str" ]; then
	echo "String NOT empty"
else
	echo "No statement is true"
fi
```

### Numbers

| Symbol | Description      |
| ------ | ---------------- |
| `-eq`  | Equal            |
| `-ne`  | Not equal        |
| `-lt`  | Lower than       |
| `-le`  | Lower or equal   |
| `-gt`  | Greater than     |
| `-ge`  | Greater or equal |

```bash
#! /bin/bash

read -p "Input a number" num

if [ $num -eq 18 ]; then
	echo "$num=18"
elif [ $num -ge 25]; then
	echo "$num is greater or equal than 25"	
fi
```

### Files

| Symbol | Description                                                             |
| ------ | ----------------------------------------------------------------------- |
| `-e`   | Exists. <br>All following commands will check if file exists by default |
| `-d`   | Is directory                                                            |
| `-f`   | Is regular file                                                         |
| `-s`   | Is not empty                                                            |
| `-r`   | Is readable                                                             |
| `-w`   | Is writable                                                             |
| `-x`   | Is executable                                                           |

```bash
#! /bin/bash
read -p "Input name of file: " file

if [ -e "$file" ]; then
	echo "File exists"
elif [ ! -s "file" ]; then
	echo "File exists and is empty"
fi
```

### Logic Conditions


| Symbol | Description |
| ------ | ----------- |
| `-a`   | AND         |
| `-o`   | OR          |
For modern way the statement will be surrounded by `[[ ]]`. Spacing ruling is the same
+ `&&` : AND
+ `||`: OR


```bash
#! /bin/bash

num=8

if [ $num -gt 3 -a $num -lt 10 ]; then
	echo "3 < $num < 10"
fi

if [ $num -gt 3 -o $num -lt 10 ]; then
	echo "3 < $num OR  $num < 10"
fi

file="file.sh"

# Check if file is not empty and executable
if [ -s "$file" -a -x "$file" ]; then
	echo "$file is not empty and is executable"
fi
```

## For loop

```bash
#! /bin/bash

for i in {1,2,3,4}; do
	echo "$i"
done

for i in {c..g}{1..3}; do
	echo "$i"
done

for i in {1,"hello",3,"BAD","there"}; do
	echo "$i"
	if [ "$i" == "BAD" ]; then
		echo "Breaking out of the loop"
		break
	fi
done

# Naviage through each txt file in same directory
for my_file in ./*.txt; do
	echo "$my_file"
done
```

Modern way

```bash
#! /bin/bash

for (( i = 0; i < 25; i=i+1 )); do
	echo "$i"
done
```

## Parameters

```bash
#! /bash/bin

# Script will accept parameters starting from 1 to n
echo "Parameter 1: $1\nParameter 2: $2\n...Parameter 50: ${50}"
echo "Number of parameters: $#"
# All parameters as a list
echo "All parameters: $@"
# All parameters concatenated
echo "All parameters: $*"
for i in $@; do
	# Print each parameter
	echo "$i"
done

# Parameters will be shifted by [number] of positions
# Here $1 takes the place of $3; $2 of $4.... ${50} of ${52}
shift 2
```

## Function

```bash
#! /bin/bash

my_function(){
	echo "Function was called"
	local var1="var1"
	var2="var2"
}

echo "Script started"
# Function was called
my_function

# Var1 will print nothing because is out of scope but var2 will print its value
echo "$var1, $var2"

hello_func(){
	echo "Hello $1"
	echo " also hello to $2"
	return 10
}

# Result will be "Hello Danny also hello John"
hello_func "Danny" "John"
echo "Return value is $?"
```

## Array

```bash
#! /bin/bash

my_array=(1 2 3 4 5)
my_array[3]="hello"

# Append to array
my_array+=(6 7 "new text")

# All elements of array
echo "${my_array[@]}"

# Number of elements in array
echo "${#my_array[@]}"

# All indexes that are filled
echo "${!my_array[@]}"
```