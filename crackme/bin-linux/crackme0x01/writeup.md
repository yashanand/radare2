
# crackme0x01
### Information gathering using rabin2


```console
$rabin2 -I crackme0x01
```

![](explain shell )


![](https://github.com/yashanand/radare2/blob/master/crackme/bin-linux/crackme0x01/0x01/rabin2_I.png)

The main info is that the binary is 32-bit little endian , we can use other linux command like **file** to find the info about the bin file.

### Cracking file using rabin2

```console            
$rabin2 -z crackme0x01
```
![](exaplin shell)


![](https://github.com/yashanand/radare2/blob/master/crackme/bin-linux/crackme0x01/0x01/rabin2_z.png)


### Cracking file using radare2

```console 
$radare2 crackme0x01
[0x08048360]> aaa
[0x08048360]> pdf @ main
```

* aa:- analyze all.
* aaa:- analyze all with more info.
* pdf:- print disassemble function.

![](https://github.com/yashanand/radare2/blob/master/crackme/bin-linux/crackme0x00/0x00/man_rabin2.png)


![](https://github.com/yashanand/radare2/blob/master/crackme/bin-linux/crackme0x00/0x00/main_function.png)


![](https://github.com/yashanand/radare2/blob/master/crackme/bin-linux/crackme0x00/0x00/%40main_using_radare2.png)

### cracking with passw0rd

```console
$./crackme0x00 
Password: 250382
```

![](https://github.com/yashanand/radare2/blob/master/crackme/bin-linux/crackme0x00/0x00/crack_pass.png)

