Cranky's Data Virus
========================================
(for educational purpose only!)

This application is used as my demonstration for:
<a href="https://cranklin.wordpress.com/2016/12/26/how-to-create-a-virus-using-the-assembly-language">How to Create a Virus Using the Assembly Language</a>


Description:
------------
This is an educational virus meant for infecting 32-bit ELF executables on Linux.
This virus uses the data segment infection method
This virus only infects ELF executables in the same directory

To assemble:
-----------
```
> nasm -f elf -F dwarf -g cranky_data_virus.asm
> ld -m elf_i386 -e v_start -o cranky_data_virus cranky_data_virus.o
```
`
(base) hz@hz:~/ws/other/cranky-data-virus$ nasm -f elf -F dwarf -g cranky_data_virus.asm
(base) hz@hz:~/ws/other/cranky-data-virus$ ls
cranky_data_virus.asm  cranky_data_virus.o  LICENSE  README.md
(base) hz@hz:~/ws/other/cranky-data-virus$ la
total 40
drwxrwxr-x 78 hz hz  4096 1月   7 11:53 ..
-rw-rw-r--  1 hz hz   674 1月   7 11:53 README.md
-rw-rw-r--  1 hz hz  1066 1月   7 11:53 LICENSE
drwxrwxr-x  8 hz hz  4096 1月   7 11:53 .git
-rw-rw-r--  1 hz hz 13941 1月   7 11:53 cranky_data_virus.asm
-rw-rw-r--  1 hz hz  3040 1月   7 11:57 cranky_data_virus.o
drwxrwxr-x  3 hz hz  4096 1月   7 11:57 .
(base) hz@hz:~/ws/other/cranky-data-virus$ 

(base) hz@hz:~/ws/other/cranky-data-virus$ ld -m elf_i386 -e v_start -o cranky_data_virus cranky_data_virus.o
(base) hz@hz:~/ws/other/cranky-data-virus$ la
total 44
drwxrwxr-x 78 hz hz  4096 1月   7 11:53 ..
-rw-rw-r--  1 hz hz  1066 1月   7 11:53 LICENSE
drwxrwxr-x  8 hz hz  4096 1月   7 11:53 .git
-rw-rw-r--  1 hz hz 13941 1月   7 11:53 cranky_data_virus.asm
-rw-rw-r--  1 hz hz  3040 1月   7 11:57 cranky_data_virus.o
-rw-rw-r--  1 hz hz  1332 1月   7 11:59 README.md
drwxrwxr-x  3 hz hz  4096 1月   7 11:59 .
-rwxrwxr-x  1 hz hz  2776 1月   7 11:59 cranky_data_virus
(base) hz@hz:~/ws/other/cranky-data-virus$ 

`

`
(base) hz@hz:~/ws/other/cranky-data-virus$ nasm -f elf -F dwarf -g cranky_data_virus.asm
(base) hz@hz:~/ws/other/cranky-data-virus$ ls
cranky_data_virus.asm  cranky_data_virus.o  LICENSE  README.md
(base) hz@hz:~/ws/other/cranky-data-virus$ la
total 40
drwxrwxr-x 78 hz hz  4096 1月   7 11:53 ..
-rw-rw-r--  1 hz hz   674 1月   7 11:53 README.md
-rw-rw-r--  1 hz hz  1066 1月   7 11:53 LICENSE
drwxrwxr-x  8 hz hz  4096 1月   7 11:53 .git
-rw-rw-r--  1 hz hz 13941 1月   7 11:53 cranky_data_virus.asm
-rw-rw-r--  1 hz hz  3040 1月   7 11:57 cranky_data_virus.o
drwxrwxr-x  3 hz hz  4096 1月   7 11:57 .
(base) hz@hz:~/ws/other/cranky-data-virus$ 

(base) hz@hz:~/ws/other/cranky-data-virus$ ld -m elf_i386 -e v_start -o cranky_data_virus cranky_data_virus.o
(base) hz@hz:~/ws/other/cranky-data-virus$ la
total 44
drwxrwxr-x 78 hz hz  4096 1月   7 11:53 ..
-rw-rw-r--  1 hz hz  1066 1月   7 11:53 LICENSE
drwxrwxr-x  8 hz hz  4096 1月   7 11:53 .git
-rw-rw-r--  1 hz hz 13941 1月   7 11:53 cranky_data_virus.asm
-rw-rw-r--  1 hz hz  3040 1月   7 11:57 cranky_data_virus.o
-rw-rw-r--  1 hz hz  1332 1月   7 11:59 README.md
drwxrwxr-x  3 hz hz  4096 1月   7 11:59 .
-rwxrwxr-x  1 hz hz  2776 1月   7 11:59 cranky_data_virus
(base) hz@hz:~/ws/other/cranky-data-virus$ 

`

`
iie@iie:~/ws/share/cranky-data-virus/test_dir$ ls -la
total 20
drwxr-xr-x 2 iie iie 4096 1月   7 12:21 .
drwxrwxr-x 4 iie iie 4096 1月   7 12:18 ..
-rw-r--r-- 1 iie iie    5 1月   7 12:20 1.txt
-rw-r--r-- 1 iie iie  111 1月   7 12:21 2.txt
-rwxr-xr-x 1 iie iie 2776 1月   7 12:18 cranky_data_virus
iie@iie:~/ws/share/cranky-data-virus/test_dir$ ./cranky_data_virus 
iie@iie:~/ws/share/cranky-data-virus/test_dir$ ls -la
total 20
drwxr-xr-x 2 iie iie 4096 1月   7 12:21 .
drwxrwxr-x 4 iie iie 4096 1月   7 12:18 ..
-rw-r--r-- 1 iie iie    5 1月   7 12:20 1.txt
-rw-r--r-- 1 iie iie  111 1月   7 12:21 2.txt
-rwxr-xr-x 1 iie iie 2776 1月   7 12:18 cranky_data_virus
iie@iie:~/ws/share/cranky-data-virus/test_dir$ 
`


