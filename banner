#!/bin/bash

########## Banner ##########

banner3="
<BR><font color='#DAA520'>===========================================</BR></font>
<BR><font color='#008080'>******************Servicio Premium******************</BR></font>
<BR><font color='#DAA520'>===========================================</BR></font>
<BR><font color='#1E90FF'>------------------------Llamadas whatsapp ✔---------------------</BR></font>
<BR><font color='#1E90FF'>----------------------------Juegos Online ✔---------------------------</BR></font>
<BR><font color='#1E90FF'>--------------------------------Torrents 🚫--------------------------------</BR></font>
<BR><font color='#DAA520'>===========================================</BR></font>
<BR><font color='#860086'> -------------CONECTANDO AL MUNDO VIRTUAL-------------</BR></font>
<BR><font color='#DAA520'>===========================================</BR></font>
<BR><font color='#1E90FF'> Validando acceso.....</BR></font>
"
sed -i 's%DROPBEAR_BANNER=""%DROPBEAR_BANNER="/etc/issue.net"%g' /etc/default/dropbear
echo "$banner3" > /etc/issue.net
service dropbear restart

sshd_config_bak=$(cat /etc/ssh/sshd_config |grep -v "Banner")
echo "$sshd_config_bak" > /etc/ssh/sshd_config
echo "Banner /etc/bannerssh" >> /etc/ssh/sshd_config
service ssh restart 1>/dev/null 2>/dev/null
service sshd restart 1>/dev/null 2>/dev/null
if [ -f /etc/bannerssh ]
then
banner=$(cat /etc/bannerssh)
else
banner="No hay un banner de momento"
fi
echo "bannerssh" > /etc/bannerssh
service ssh restart 1> /dev/null 2>/dev/null
service sshd restart 1>/dev/null 2>/dev/null

banner2="
<BR><font color='#DAA520'>===============================================</BR></font>
<BR><font color='#008080'>********************Servicio Premium********************</BR></font>
<BR><font color='#DAA520'>===============================================</BR></font>
<BR><font color='#1E90FF'>---------------------------Llamadas whatsapp ✔-------------------------</BR></font>
<BR><font color='#1E90FF'>-------------------------------Juegos Online ✔------------------------------</BR></font>
<BR><font color='#1E90FF'>-----------------------------------Torrents 🚫------------------------------------</BR></font>
<BR><font color='#DAA520'>===============================================</BR></font>
<BR><font color='#860086'> ----------------CONECTANDO AL MUNDO VIRTUAL----------------</BR></font>
<BR><font color='#DAA520'>===============================================</BR></font>
<BR><font color='#1E90FF'> Validando acceso.....</BR></font>
"
echo "$banner2" > /etc/bannerssh
/etc/init.d/ssh restart
echo -e "\033[1;37mTerminado !!!\033[0m"
