
# crackme0x01
### Information gathering using rabin2


```console
$rabin2 -I crackme0x01
```

![](https://github.com/yashanand/radare2/blob/master/crackme/bin-linux/crackme0x01/0x01/explain_rabin2_I.png)


![](https://github.com/yashanand/radare2/blob/master/crackme/bin-linux/crackme0x01/0x01/rabin2_I.png)

The main info is that the binary is 32-bit little endian , we can use other linux command like **file** to find the info about the bin file.

### Cracking file using rabin2

```console            
$rabin2 -z crackme0x01
```
![](https://github.com/yashanand/radare2/blob/master/crackme/bin-linux/crackme0x01/0x01/explain_shell_z.png)


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

![](https://github.com/yashanand/radare2/blob/master/crackme/bin-linux/crackme0x01/0x01/explain_radare2.png)


![]()


![]()

### cracking with passw0rd

```console
$./crackme0x00 
Password:
```

![]()

