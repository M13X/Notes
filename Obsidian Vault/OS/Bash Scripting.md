# Bash Scripting

## Variables

| Command               | Description                                           |
| --------------------- | ----------------------------------------------------- |
| `name=value`          | Assign variable `name` a `value`                      |
| `${name}`             | Access the value of variable `name`                   |
| `unset <variable>`    | Removes the value of variable                         |
| `${#variable}`        | Number of characters inside variable                  |
| `${var:number}`       | Get substring starting from position `number`         |
| `${var:begin:length}` | Substring starting from `begin` + `length`            |
| `${var: -number}`     | Get the last `number` characters of string            |
| `${var: -num:length}` | Get substring from last `num` characters for `lenght` |
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