## This Documentation describes how i solved the following problems using bash scripting:
1) Ask the user for their name and age, and output a message with their name and the year they were born.
2) Create a new directory with a name provided by the user, and navigate into it.
3) List all files in the current directory, sorted by file size.
4) Count the number of files in the current directory and output the result.
5) Take a list of numbers as input from the user and output the sum of those numbers.
6) Output a random number between 1 and 100.
7) Create a backup of a specified file by copying it to a backup directory with a timestamp in the filename.
8) Check if a website is online and output a message indicating whether it is up or down.
9) Convert a temperature in Celsius to Fahrenheit, using input from the user.
10) Ask the user for a sentence, then output the sentence in reverse order. For example, if the user enters “Hello, world!”, the script should output “!dlrow ,olleH”.

## SOLUTION
### STEP 1- PREPARING ENVIRONMENT AND CREATING SHELL SCRIPT FILE:
- I created the project folder called shell using the command:
mkdir shell

- Then, I moved into the shell folder using the command:
cd shell

- Then, while in the shell directory, I created a file for the shell script named “script_task.sh” using the command:
touch script_task.sh

- Then, I switched to visual studio so that i could have a window to edit my shell file -”script_task.sh” file and also have a terminal to run command on

![Screenshot from 2023-07-22 08-11-23](https://github.com/AbooHamzah/auxillary-projects/assets/108676700/3fbe7824-3912-4bc0-89df-87e0f433e9c5)


- Then, I made the script file executable by running the command:
chmod +x script_task.sh

### STEP 2- WRITING THE SHELL SCRIPT:
#### The code below would ask the user for their name and age, and output a message with their name and the year they were born.
read -p "Please input your name: " NAME

read -p "Please input your age: " AGE

Thisyear="$(date +%Y)"

YOB="$(($Thisyear - $AGE))"

echo "Your name is $NAME and you were born in the year $YOB"


#### The code below would create a new directory with the name provided above, and navigate into it.
mkdir $NAME

cd $NAME

touch 1.txt 2.txt 3.txt

echo "Hello, World!" > 1.txt


#### The code below would list all files in the current directory, sorted by file size.
ls -lh |

sort -n -r |

while read -r line; do

  echo "$line"

done

#### The code below would count the number of files in the current directory and output the result.
num_files=$(ls -1 | wc -l)

echo "The number of files in the current directory is $num_files"

#### The code below would take a list of numbers as input from the user and output the sum of those numbers.
sum=0

echo "Enter a list of numbers, separated by spaces:"

read -a numbers

for num in "${numbers[@]}"

do

  sum=$(($sum + $num))

done

echo "The sum of the numbers is: $sum"

#### The code below would output a random number between 1 and 100.
echo "A randon number between 1 and 100 is:  $((1 + $RANDOM % 100))"

#### The code below creates a backup of a specified file by copying it to a backup directory with a timestamp in the filename.
echo "Hello, world!" > bola.txt

timestamp=$(date +"%Y-%m-%d_%H-%M-%S")

if [ ! -d ".backups" ]; then

  mkdir .backups

fi

cp bola.txt .backups/bola.txt.$timestamp

echo "The file bola.txt has been backed up to .backups/bola.txt.$timestamp"

#### The command below would check if a website is online and output a message indicating whether it is up or down.
ping -c 1 www.youtube.com > /dev/null

if [ $? -eq 0 ]; then

  echo "The site you are trying to access is up."

else

    echo "The site you are trying to access is down."

fi

#### The code below would convert a temperature in Celsius to Fahrenheit, using input from the user.
read -p "Enter the temperature in Celsius: " CEL

CELM="$(($CEL * 9 / 5))"

FAR="$(($CELM + 32))"

echo "The temperature in Fahrenheit is: $FAR"


#### The code below would ask the user for a sentence, then output the sentence in reverse order. 
read -p "Enter a sentence: " sentence

reversed_sentence=""

for word in $(echo $sentence | tr " " "\n")

do

  reversed_sentence="$word $reversed_sentence"

done

echo "The reversed sentence is: $reversed_sentence"

### BELOW IS A VIDEO DEMONSTRATION OF HOW THE AFOREWRITTEN COMMANDS EXECUTED:

file:///home/aboo-hamzah/Videos/Screencasts/Screencast%20from%2022-07-2023%2007:53:24.mp4

file:///home/aboo-hamzah/Videos/Screencasts/Screencast%20from%2022-07-2023%2007:58:45.mp4


