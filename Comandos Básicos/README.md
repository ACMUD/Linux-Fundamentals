# Comandos Básicos

En este apartado vamos a aprender un poco de Linux e iniciamos con algunos comandos sencillos, algunos apartados van a estar en inglés y otros en español

- Introducción a Linux
  - [Filosofía]()
  - 
# Filosofía

| Principle | Description |
| --- | --- |
| Everything is a file | All configuration files for the various services running on the Linux operating system are stored in one or more text files. |
| Small, single-purpose programs | Linux offers many different tools that we will work with, which can be combined to work together. |
| Ability to chain programs together to perform complex tasks | The integration and combination of different tools enable us to carry out many large and complex tasks, such as processing or filtering specific data results. |
| Avoid captive user interfaces | Linux is designed to work mainly with the shell (or terminal), which gives the user greater control over the operating system. |
| Configuration data stored in a text file | An example of such a file is the /etc/passwd file, which stores all users registered on the system. |


# Comandos básicos

`id` Grupos en los que estamos

`sudo` convertirme en root o hacer cosas como root

`/etc/group` Los grupos que están en 

Ruta absoluta Vs Ruta Relativa

`which` Or `command -v`

`echo $PATH`

Filtros

cat /etc/groups | grep “floppy” -n → Para la linea

`pwd`

`ls` → lsd

`ls -l` → más detalles

`cd`

`/etc/passwd` → Usuarios válidos a nivel de sistema

`/etc/shells` → Shells disponibles

`$` Usuario sin privilegios

`#` Usuario con privilegios root

`ps` Lista el estado de procesos

`lsof` Lista “archivos” abiertos

`ifconfig` Lista los parametros de la red

`man` Manual de las herramientas

`<tool> --help` Para pedir ayuda de una herramienta 

`uname` Imprime información de la máquina

`ssh <username>@<Ip Address>`

## System Information HTB

<details>
<summary>Find out the machine hardware name and submit it as the answer.</summary>

```bash
    :~$ man uname
    -i, --hardware-platform
                  print the hardware platform (non-portable
    :~$ uname -i
    x86_64
```
</details>


<details>
<summary>What is the path to htb-student's home directory?</summary>

   ```bash
    :~$ echo $HOME
    /home/htb-student
   ```
    
</details>


<details>
<summary>What is the path to the htb-student's mail?</summary>
    
  ```bash
    :~$ echo $MAIL
    /var/mail/htb-student
  ```
</details>

<details>
<summary>Which shell is specified for the htb-student user?</summary>
    
  ```bash
    :~$ echo $SHELL
    /bin/bash
  ```
</details>

<details>
<summary>Which kernel version is installed on the system? (Format: 1.22.3)</summary>        
  
  ```bash
    :~$ man uname
    -r, --kernel-release
                  print the kernel release
    :~$ uname -r
    4.15.0-123-generic
  ```
</details>


<details>
<summary>What is the name of the network interface that MTU is set to 1500? (Maximum Transmission Unit)</summary>        
  
   ```bash
    :~$ ifconfig
    ens192: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 1500
   ```
</details>

<details>
<summary>What is the name of the hidden "history" file in the htb-user's home directory?</summary>

```bash
:~$ ls -la
total 32
-rw------- 1 htb-student htb-student    5 Sep 23  2020 .bash_history
```

</details>

<details>
<summary>What is the index number of the "sudoers" file in the "/etc" directory?</summary>

```bash
:/etc$ man ls | grep "index" -C 2
-i, --inode
              print the index number of each file
:/etc$ ls -i /etc/sudoers
147627 /etc/sudoers
```

</details>

<details>
<summary>What is the name of the last modified file in the "/var/backups" directory?</summary>

```bash
:/var/backups$ ls -la
-rw-r--r--  1 root root    41872 Nov 12  2020 apt.extended_states.0
```

</details>

<details>
<summary>What is the inode number of the "shadow.bak" file in the "/var/backups" directory?</summary>

```bash
:/var/backups$ ls -i shadow.bak
265293 shadow.bak
```

</details>











### Referencias

[Hola](https://academy.hackthebox.com/module/18/section/94)
