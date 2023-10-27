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

## Partie 3 : SSH

Un serveur SSH est lancé sur le port par défaut.   
Il est possible de s'y connecter avec n'importe quel compte, y compris le compte root.  

___

**Question 3.1 : Configuration de SSH**  
Désactiver complètement l'accès à distance de l'utilisateur root.  
Autoriser l'accès à distance à ton compte personnel uniquement.   

**3.1 : Configuration de SSH**  

Désactiver complètement l'accès à distance de l'utilisateur root   
![image](https://github.com/techerbeatrice/checkpoint_03_TSSR/assets/138071140/865e0939-5a3e-4657-a2c7-902898e09101)

Autoriser l'accès à distance à ton compte personnel uniquement.   
![image](https://github.com/techerbeatrice/checkpoint_03_TSSR/assets/138071140/f55ad5bc-afc6-4cf9-92e5-42526538eb0d)

____

**Question 3.2 : Authentification cryptographique**  

 
Mettre en place une authentification par clé valide    
![image](https://github.com/techerbeatrice/checkpoint_03_TSSR/assets/138071140/0d294324-d35c-4bfc-afb7-583485593bb2)

 
Désactiver l'authentification par mot de passe    
![image](https://github.com/techerbeatrice/checkpoint_03_TSSR/assets/138071140/84401b84-d94d-4b59-9071-e3e95e67bade)

___

## Partie 4 : Filtrage et analyse réseau  

____

**Question 4.1 : Analyse de règles de filtrage**  
  
Quelles sont actuellement les règles appliquées sur Netfilter ?    
Quels types de communications sont autorisées ?       
Et quels types sont interdites ?     
Il n'y a aucune règle de filtrage.     
![image](https://github.com/techerbeatrice/checkpoint_03_TSSR/assets/138071140/c1edb17f-8b58-40a7-9447-cfd30d7dcfe5)

![image](https://github.com/techerbeatrice/checkpoint_03_TSSR/assets/138071140/54a3118e-37d2-42b8-931a-3d943b15d961)

___

**Question 4.2 : Paramétrage avec nftables**  

Ajoute les règles nécessaires pour autoriser bareos actuellement installé sur le serveur à communiquer avec les clients bareos potentiellement présents sur l'ensemble des machines du réseau local sur lequel se trouve le serveur.   

Rappel : Bareos utilise les ports TCP 9101 à 9103 pour la communication entre ses différents composants.   

![image](https://github.com/techerbeatrice/checkpoint_03_TSSR/assets/138071140/f1eeb1f8-d6e4-45e6-87e0-1f04c11ff1a4)

