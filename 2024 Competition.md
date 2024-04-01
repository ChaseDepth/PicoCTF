# Cryptography
Insatalled hxtools
	sudo apt-get install hxtools
	Now I can just do rot13 instead of throwing crazy code
	
	echo "cvpbPGS{arkg_gvzr_V'yy_gel_2_ebhaqf_bs_ebg13_MAZyqFQj}" | rot13
picoCTF{next_time_I'll_try_2_rounds_of_rot13_ZNMldSDw}

# interencdec
base64 has equal signs at the end because ASCI bytes need to end in multiples of 4. Equal signs pad out the rest in case the encryption ends with a byte less than 4. it is padding. You’ll only see none, one, or two. 
original
YidkM0JxZGtwQlRYdHFhR3g2YUhsZmF6TnFlVGwzWVROclgyMHdNakV5TnpVNGZRPT0nCg==
Decodes to
d3BqdkpBTXtqaGx6aHlfazNqeTl3YTNrX20wMjEyNzU4fQ==
which decodes to
wpjvJAM{jhlyh_yk3jy9wa3k_m0212758}
wpjvKAM{jhlyh_yk3njy9wa3k_m0212758}

# ROT19
picoCTF{caera_rd3cr9pt3d_f0212758} 

(all close. I had some outputs with b’’ and it confused all the decryption. Some sites will spit out gibberish until this is removed. 
This is a Caesar encryption. Rotate now
Kind of. remember that if you decode something and it comes out as b’’’ it’s actually a wrapper used by python to encode ASCII data into bytes. This can be the output accidently and needs to be removed before decoding more as appropriate or it’ll tarnish the decryption more. ChatGPT is ALLLLMOOOSTT great at decoding/encoding. 
Tools used
https://www.cachesleuth.com/rot.html
https://www.rapidtables.com/web/tools/base64-decode.html


# Scan surprise
was just a QR code you needed to view from the terminal. A phone camera can do the rest. 

format string 0
okay so learned what a memory leak is and to exploit it, if you come across a system that spits the same info back, you can trick it to say what memory is stored in it with characters like “%x” and “%d”. You’ll need to break it up with . or / because spaces  
okay, back at it. The format system is 64 bit. 

%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.%d.

%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.%x.
402118.0.1f28ea00.0.572880.a347834.1ff27fc0.1f07fe60.1f2a44d0.1.1ff28090.0.0.6f636970.6d316e34.33317937.3431665f.64663533.7.1f2a68d8.7.74307250.6c797453.9.1f2b7de9.1f088098.1f2a44d0.0.1ff280a0.252e7825.2e78252e.78252e78.252e7825.2e78252e.78252e78.252e7825.2e78252e.78252e78.252e7825.2e78252e.78252e78.252e7825.2e78252e.78252e78.252e7825.2e78252e.78252e78.252e7825.2e78252e.78252e78.252e7825.2e78252e.78252e78.252e7825.2e78252e.78252e78.252e7825.2e78252e.78252e78.252e7825.2e78252e.78252e78.252e7825.2e78252e.78252e78.252e7825.2e78252e.78252e78.252e7825.2e78252e.78252e78.252e7825.2e78252e.78252e78.252e7825.2e78252e.78252e78.252e7825.2e78252e.78252e78.252e7825.2e78252e.78252e78.252e7825.2e78252e.78252e78.252e7825.2e78252e.78252e78.252e7825.2e78252e.78252e78.252e7825.2e78252e.78252e78.252e7825.2e78252e.78252e78.252e7825.2e78252e.78252e78.252e7825.2e78252e.78252e78.252e7825.2e78252e.78252e78.252e7825.2e78252e.78252e78.252e7825.2e78252e.78252e78.252e7825.2e78252e.78252e78.252e7825.2e78252e.78252e78.252e7825.2e78252e.78252e78.252e7825.2e78252e.78252e78.252e7825.2e78252e.78252e78.252e7825.2e78252e.78252e78.252e7825.2e78252e.78252e78.252e7825.2e78252e.78252e78.252e7825.2e78252e.78252e78.252e7825.2e78252e.78252e78.252e7825.2e78252e.78252e78.252e7825.2e78252e.78252e78.252e7825.2e78252e.78252e78.252e7825.2e78252e.78252e78.252e7825.2e78252e.0.
570680.1.1f0a1d90.0.4011f6.0.1ff28518.0.5ec70595.1ff28518.4011f6.403e18.1f2e0040.56e50595.644d0595.0.0.0.0.0.b149c900.0.1f0a1e40.1ff28528.403e18.1f2e12e0
.0.0.
401110.1ff28510.0.0.401135.1ff28508.1c.1.1ff28ea6.0.1ff28ec1.1ff28ed4.1ff28edc.1ff28efa.1ff28f05.1ff28f1a.1ff28f37.1ff28f4d.1ff28f61.1ff28f72.1ff28fb4.1ff28fc3.1ff28fd0.0.21.1ff56000.33.e30.10.1f8bfbff.6.1000.11.64.3.400040.4.38.5.d.7.1f2a6000.8.0.9.401110.b.0.c.0.d.0.e.0.17.0.19.1ff28709.1a.2.1f.1ff28fdd.f.1ff28719.1b.1c.1c.20.0.0.49c9df00.cfaf62d0.36387882.
0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.

I need to practice binary exploitation

The flag is in hex. See where the pattern broke and decipher that. 


# verify
I have to check the hash of each file to see if they match the checksum of a hash I already have
OG hash for the flag below. There is a .sh that decrypts I think. It will reveal the flag if I find the correct file.
3ad37ed6c5ab81d31e4c94ae611e0adf2e9e3e6bee55804ebc7f386283e366a4
sudo apt dist-upgrade

sha256sum files/*
this will run sha256sm for everything in the files directory. I can also add | > hash.txt so it would be in a file called hash.txt easily.

files/e018b574 has the matching hash

files/e018b574
DO NOT DOWNLOAD THE FILES. They just don’t work right. Just log in through the shh if they provide it. Stuck for over an hour doing the same thing over and over again. 
It provided a decrypt.sh to decrypt the correct file that hashes matched with the known checksum so just run
./decrypt.sh files/<file_name>


# cipher
DLSeGAGDgBNJDQJDCFSFnRBIDjgHoDFCFtHDgJpiHtGDmMAQFnRBJKkBAsTMrsPSDDnEFCFtIbEDtDCIbFCFtHTJDKerFldbFObFCFtLBFkBAAAPFnRBJGEkerFlcPgKkImHnIlATJDKbTbFOkdNnsgbnJRMFnRBNAFkBAAAbrcbTKAkOgFpOgFpOpkBAAAAAAAiClFGIPFnRBaKliCgClFGtIBAAAAAAAOgGEkImHnIl  

Downloaded visual studio 
sudo dpkg -i <studio visual code download file from website>


# endianness

rolpt
118 114 105 108 105
76 72 69 6c 69


https://cryptii.com/pipes/text-decimal
That site is your best friend to find an endian. You need to convert a text into a hex (which is converted from the ASCII value of a text). For hxkff,  the hex is 68 78 6b 66 66 (which is also the little endian. Big endian is this exact code in reverse so 66 66 6b 78 68)

echo -n "YourText" | xxd -p -e
//for big endian//

echo -n "YourText" | xxd -p | tac | tr -d '\n' && echo ""
//for little endian

# Mob Psycho
find dir/ -type f | xargs grep ‘string’
//to find the string in a mess of directories. Change dir/ to the actual parent directory name like mob/


# stonks
Alright.
A stack is essentially a pile of memory and they are ‘stored’ on top of one another. These can be assorted by types like integers, strings, and hex. Afaik, %X is for hex, %S is strings. 
https://www.tutorialspoint.com/c_standard_library/c_function_sprintf.htm
That has a table of types of memory pointers. 
A the stack of memory can be called a buffer? You want to set parameters around that. If code looks like this
        char *user_buf = malloc(300 + 1);
        printf("What is your API token?\n");
        scanf("%300s", user_buf);
        printf("Buying stonks with token:\n");
        printf(user_buf);
then there’s an issue to be exploited. See the last line. There’s no parameters when you select “buying stonks with token” in this python-designed chat. You can search for hex memory by asking it %X. A parameter to fix this would be printf(“%10X”, user_buf) I believe. This makes sure that there’s a cap of 10 characters that can be revealed.
Create a separate tab, 
	python 
when python opens
	‘%X’ * 100
Paste the output to the chat nc for this challenge when you select “buy some stonks!” It’ll ask what my API token is. This is where the vulnerability is housed. it’ll spit back a bunch of hex gibberish. 
https://www.rapidtables.com/convert/number/hex-to-decimal.html
Convert the hex. You’ll see backward bits hidden in the mess. Copy that. It needs it’s endians reversed. 
Go back to python. VSC or terminal works fine
s = 'ocip{FTC0l_I4_t5m_ll0m_y_y3n4cdbae52ÿÐ}'
the string is stored
	for x in range(0,len(s),4):
     		print(s[x+3]+s[x+2]+s[x+1]+s[x],end='')
Make sure to indent in python. Super important. So this code is giving each hex bit character value up to 4, as bits are stored in 4. Highest value is p, lowest is o with ocip. The print function will print each string value in reversed assigned bit value. Takes a few minutes to process.  

