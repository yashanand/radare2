
# crackme0x00
### Information gathering using rabin2


```console
$rabin2 -I crackme0x00
```

![](https://github.com/yashanand/radare2/blob/master/crackme/bin-linux/crackme0x00/0x00/man_rabin2.png)


![](https://github.com/yashanand/radare2/blob/master/crackme/bin-linux/crackme0x00/0x00/info_using_rabin2.png)

The main info is that the given binary is 32-bit and little endian, we can use other linux command like **file** to find the info about the binary file.

### Cracking file using rabin2

```console            
$rabin2 -z crackme0x00
```
![](https://github.com/yashanand/radare2/blob/master/crackme/bin-linux/crackme0x00/0x00/man_rabin2_z.png)

*rabin2* with *-z* parmeter extract all the strings from binary file, it is like the linux **strings** command.

![](https://github.com/yashanand/radare2/blob/master/crackme/bin-linux/crackme0x00/0x00/using_rabin2.png)

Lets analyse the output of the command, we got 5 strings lets try to figure out by executing the binary file.

* *IOLI Crackme Level 0x00* :- This is first strings which will print when we run the program.
* *Password* :- This wil prompt the password to enter which will futher check if it's correct or not.
* *Invalid Password!* :- This will prompt when the password is wrong , bad luck :(
* *Password OK :)* :- This will be prompt when the password is correct :) [assumption]
* *250382* :- This is the number which appears, but no idea what is used for ,lets try to put this as a passw0rd maybe the strings *250382* is compared with the given input.

![](https://github.com/yashanand/radare2/blob/master/crackme/bin-linux/crackme0x00/0x00/crack_pass.png)

### Cracking file using radare2

```console 
$radare2 crackme0x00
[0x08048360]> aaa
[0x08048360]> pdf @ main
```

* aa:- analyze all.
* aaa:- analyze all with more info.
* pdf:- print disassemble function.

![](https://github.com/yashanand/radare2/blob/master/crackme/bin-linux/crackme0x00/0x00/man_radare2.png)


![](https://github.com/yashanand/radare2/blob/master/crackme/bin-linux/crackme0x00/0x00/main_function.png)


![](https://github.com/yashanand/radare2/blob/master/crackme/bin-linux/crackme0x00/0x00/%40main_using_radare2.png)

Lets try to analyse the above snap.

At *0x08048469* address there is a strings cmp between **s1** and **s2**.Lets try to find out what is the s1 and s2 variable.
At *0x0804845e* string *250382* is moved into the variable s2 and s1 will be the our input which we give as a password. 

### cracking with pasmov dword [s2], str.250382sw0rd

```console
$./crackme0x00 
Password: 250382
```

![](https://github.com/yashanand/radare2/blob/master/crackme/bin-linux/crackme0x00/0x00/crack_pass.png)

