# Checkpoint 3 TSSR
____

2 comptes sont disponibles pour se connecter :   

Un compte utilisateur - Login : wilder / Password : wcs4ever  
Le compte root - Password : MXtTvqGXmZDf  

___

## Partie 1 : Gestion des utilisateurs 

___

**Question 1.1 : Lister les comptes utilisateurs**     
Faire la liste de l'ensemble des comptes utilisateurs ayant la possibilité de se connecter (d'ouvrir un shell) sur le serveur.   

**1.1 : Lister les comptes des utilisateurs** 

La liste des comptes utilisateurs ayant la possibilité de se connecter (d'ouvrir un shell) sur le serveur :   
root  
daemon  
bin  
sys  
sync  
games  
man  
lp    
mail    
news  
uucp  
proxy  
www-data  
backup  
list  
irc  
gnats  
nobody  
-apt  
systemd-network  
systemd-resolve  
messagebus    
systemd-timesync    
avahi-autoipd    
sshd    
wilder    
systemd-coredump    
bareos   
Debian-exim   
postgres   

___

**Question 1.2 : Création d'un compte utilisateur**   
Créé un compte pour ton usage personnel.   

**1.2 : Création de mon compte utilisateur pour un usage personnel**  

#Passer en **root**  
wilder@cp3:~# su -    
#Renseignement du mot de passe du root     
Mot de passe : MXtTvqGXmZDf   
#Ajout d'un utilisateur    
root@cp3:~# adduser beatrice    
#Renseignement de mon mot de passe     
Nouveau mot de passe :     
Retapez le nouveau mot de passe :   
 
![image](https://github.com/techerbeatrice/checkpoint_03_TSSR/assets/138071140/04df4f3a-36e2-4e2b-92c8-936ae9f1e026)

___

**Question 1.3 : Recommandations sur le compte wilder**     
Quelles préconisations proposes-tu concernant le compte wilder ?   

**1.3 : Préconisations proposées sur le compte wilder**   

___

## Partie 2 : Le stockage   

___

**Question 2.1 : Analyse des disques**    
a - Quels sont les systèmes de fichiers actuellement montés ?  
b - Quel type de système de stockage ils utilisent ?  

**2.1 : Analyse des disques**  
**a - Les systèmes de fichiers actuellement montés**  
**b - Le type de système de stockage ils utilisent** 

![image](https://github.com/techerbeatrice/checkpoint_03_TSSR/assets/138071140/9bff0f53-59a8-44bd-a2c5-058f591c90d2)

___

**Question 2.2 : Gestion du RAID**  
Ajoute un nouveau disque de 8,00 Gio au serveur et réparer le volume RAID   

**2.2 : Ajout d'un nouveau disque de 8,00 Gio au serveur et réparation du volume RAID**  

La commande **slbk** affiche le nouveau disque dur **sdb** de 8 go   
![image](https://github.com/techerbeatrice/checkpoint_03_TSSR/assets/138071140/36a87dcb-fa3b-4f37-9809-8fb80e122697)

La commande **vgextend** ajoute le nouveau disque au groupe de volume **cp3-vg**  
![image](https://github.com/techerbeatrice/checkpoint_03_TSSR/assets/138071140/7d14628e-55b4-46b4-ab41-ef8790cc2c1f)

La commande **vgdisplay** affiche le nouveau volume d'espace de stockage pour **cp3-vg**     
![image](https://github.com/techerbeatrice/checkpoint_03_TSSR/assets/138071140/374eb09e-a65f-4cbd-9a05-824fae5fdf1a)

La commande **mdadm --detail** pour voir **l'état du volume RAID**        
![image](https://github.com/techerbeatrice/checkpoint_03_TSSR/assets/138071140/95198691-be71-46df-a426-390d7406c289)

![image](https://github.com/techerbeatrice/checkpoint_03_TSSR/assets/138071140/aec535e5-e147-4d24-8e03-9e994f3623d1)

![image](https://github.com/techerbeatrice/checkpoint_03_TSSR/assets/138071140/2c41955e-6d6a-45c4-ae74-3c3b9c961831)

![image](https://github.com/techerbeatrice/checkpoint_03_TSSR/assets/138071140/50c0ebdf-8ee2-423b-a761-228d01029d09)

____

**Question 2.3 : Gestion de LVM**   

**2.3 : Ajout d'un nouveau volume logique LVM de 2 Gio pour héberger les sauvegardes bareos. Ce volume doit être monté automatiquement à chaque démarrage dans l'emplacement par défaut : /var/lib/bareos/storage.
Combien d'espace disponible reste-t-il dans le groupe de volume ?**

![image](https://github.com/techerbeatrice/checkpoint_03_TSSR/assets/138071140/16e7705c-111c-47f0-98a9-d2c86cf7e949)

![image](https://github.com/techerbeatrice/checkpoint_03_TSSR/assets/138071140/43552068-dbfc-4b20-950a-ab7407bc3155)

![image](https://github.com/techerbeatrice/checkpoint_03_TSSR/assets/138071140/2193287c-b4dc-4220-86ee-e83b32b35c42)

Il reste 2,505 GO   
![image](https://github.com/techerbeatrice/checkpoint_03_TSSR/assets/138071140/751b17ba-0376-4632-8240-d586b9ae74e0)

___



