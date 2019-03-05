"hello world"
# crackme0x00
### Information gathering using rabin2


```console
$rabin2 -I crackme0x00
```

explain shell image

![Screenshot](https://github.com/yashanand/radare2/blob/master/crackme/bin-linux/crackme0x00/0x00/man_rabin2.png)

rabin2 -I  image from termianl 

### Cracking file using rabin2

```console            
rabin2 -z crackme0x00
```
explain shell image
rabin2 -z  image from termianl 


### Cracking file using radare2

```console 
$radare2 crackme0x00
[0x08048360]> aaa
[0x08048360]> pdf @ main
```

explain shell image 

radare2  image from termianl 

