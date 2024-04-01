# Python Wrangling
You need to copy links to command lines so
	wget (the link copy)
It'll download the file in the terminal. Do that for the python script, password txt, and flag txt. The flag txt is encrpyted. That needs to be decrypted. So..
	 python ende.py -d flag.txt.en


# Wave a flag
Multiple ways to complete this. Can save into terminal by 
	wget (link copy). 
cat the file and read through the messages saved in it. OR save the file and open to terminal from file location manually.Mouse and click deal. No terminal initially. It'll take you directly to the terminal from there with that destination. Then play along. Change read, write, and execute permissions for good measure.
	chmod u+rwx ./warm
then
	./warm
and it goes along like I'm executing the file. ./warm -h shows the flag. 

# Nice Netcat
Using netcat, you need to
	nc mercury.picoctf.net 43239
but it only sends a bunch of numbers back. It's actually in decimal. Lucky guess but it made sense. hexadecimal looks like 00xd. The numbers were like 88 112 90. Copied and pasted into a decimal to text converter with ASCII encoding. However, a neat trick...
	tr -d '\n' <./filename       (filename should be txt editor/reader)
relays information back 88 112 90 instead of 
88
112
90

# Static aint always noise
I need to remember to run files when I download them to the terminal to see what it does. 
	./
download both the bash and static. The bash is supposed convert the static file into something else. You can see in the bash file that it spits out strings. So first, 
	chmod u+rwx      (both files so I can execute them)
then
	./ltdis.sh static
to process the static. It'll output two new .txt files, chmod those two, then cat. Look through one of them with .strings. and find the flag hiding in the mess.

# Tab, Tab, Attack
Download file with wget in terminal. Then unzip the file
	unzip <filename>
./<filename>
This folder had long ramblining directories but a neat trick is cd <tab*> so it'll auto pop the available filenames. Ls when I enter each folder until I find a program to run. run it with ./ and it replied with the flag.

# Magikarp Ground Mission
log in with ssh. Done it plenty of times with overthewire. just had to search through files to find the 3 flags. Changed with chmod so I can open some files. Even found a RSA key lol. However, I learned how to navigate through the directories. cd .. to move around or cd ~ to go home or back I believe. 

# Lets warm up
Double check my own typing. Remember picoCTF likes picoCTF{xxx} format. Used a hex to ascii converter but remember that 0x means the following is written in hexadecimal. Imagine $ for saying this is American Dollars. 

Warmed up
Same deal. Convert hexadecimal to decimal. Understand hexadecimal is already in base 16, and decimal is already base 10. Remove 0x in conversion.

# 2Warm
Change '42' in base 10 to base 2
Changing base 10 to binary essentially
Installed bc. BC is basic calculator. the cmd was not installed in my Kali machine but was in Abuntu. Originally solved in abuntu. 
	echo 'obase=2; ibase=10; 42' | bc
		replies with 101010
To install bc, I googled how to install BC for Kali linux. Found that GNU created the BC application. Installed and extracted. Dropped it into the Kali VM. Then wrote
	sudo apt install bc

# Strings it
Download the file with wget from the terminal. Then write the below
strings strings | grep pico     	
picoCTF{5tRIng5_1T_827aee91}
Remember that pipe commands allows you to write two commands. I wrote to (command)strings (file)strings (the file has thousands of code in it. CTRL+F finds it easy but I got lucky my terminal can save all these codes in cache so well. Grep pico just looks for the word pico and returns the line with that. 
https://linux.die.net/man/1/strings

# Bases
Was given a weird string to decode. No files, just a string. The question said it had to do something with bases. Binary is 2-base, Octal is 8, Decimal is 10, hex is 16, and base 32 and 64 are exactly what they sound. 
https://cryptii.com/pipes/base32

# First Grep
Remember piping! Super handy. The file to wget has a ton of code so 
	Cat file | grep pico
Done done
https://ryanstutorials.net/linuxtutorial/grep.php
	has more specific tags that should be helpful

# Codebook
More running python. Helpful to remember. -d is to decrypt btw. Wget both files. Cat code.py shows me it decrypts and I have the codebook.txt so
	Python code.py -d codebook.txt. 

#fixme
Fixed the script. Indentations mean something in python. Read through the code. On Studio Visual Code, it'll blatantly tell you which line is wrong.

#fixme2
= means to give a value to something. like x = 5 will mean x is 5. == checks for (in)equality. so if x==y, true. x=5, y=6. It’ll return false. 

# PW Crack 1
Python scripts can have pw in them. 

# PW Crack 2
http://www.csc.villanova.edu/~tway/resources/ascii-table.html
the PW in the python code is in hex

# PW Crack 3
Alright. Mostly worked with python in this one. You can manipulate the code since the script already knows the password. It has the list of possible passwords in it, so just run it.
Python likes to be tabbed and paragraphed together. If it a code is separate from a desired process, it may not run at all (at least I think so). 
At around line 27, the script says it needs a user_pw to be input but we can # that to make it an unexecutable comment. The real money is just having the code run each possible pw itself. 
	for user_pw in pos_pw_list:
This simple line makes the code run itself in a loop until it finds the correct pw, provided the below is tabbed next
 
add print(user_pw) btw so you can see what it was. The original code didn’t have that.






