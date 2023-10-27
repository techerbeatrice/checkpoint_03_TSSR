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

**1.1 : Liste des comptes des utilisateurs** 

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
 
![image](https://github.com/techerbeatrice/checkpoint_03_TSSR/assets/138071140/04df4f3a-36e2-4e2b-92c8-936ae9f1e026)

___

**Question 1.3 : Recommandations sur le compte wilder**     
Quelles préconisations proposes-tu concernant le compte wilder ?   

**1.3 : Préconisations proposées sur le compte wilder**   

___

## Partie 2 : Le stockage   

___

**Question 2.1 : Analyse des disques**    

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

**2.3 : Ajout d'un nouveau volume logique LVM de 2 Gio pour héberger les sauvegardes bareos.   
Ce volume doit être monté automatiquement à chaque démarrage dans l'emplacement par défaut : /var/lib/bareos/storage.  
Combien d'espace disponible reste-t-il dans le groupe de volume ?**  

![image](https://github.com/techerbeatrice/checkpoint_03_TSSR/assets/138071140/16e7705c-111c-47f0-98a9-d2c86cf7e949)

![image](https://github.com/techerbeatrice/checkpoint_03_TSSR/assets/138071140/43552068-dbfc-4b20-950a-ab7407bc3155)

![image](https://github.com/techerbeatrice/checkpoint_03_TSSR/assets/138071140/2193287c-b4dc-4220-86ee-e83b32b35c42)

**Il reste 2,505 GO**   
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

**Désactiver complètement l'accès à distance de l'utilisateur root**    
![image](https://github.com/techerbeatrice/checkpoint_03_TSSR/assets/138071140/865e0939-5a3e-4657-a2c7-902898e09101)

**Autoriser l'accès à distance à ton compte personnel uniquement.**     
![image](https://github.com/techerbeatrice/checkpoint_03_TSSR/assets/138071140/f55ad5bc-afc6-4cf9-92e5-42526538eb0d)

____

**Question 3.2 : Authentification cryptographique**  

**3.2 : Mettre en place une authentification par clé valide**     
![image](https://github.com/techerbeatrice/checkpoint_03_TSSR/assets/138071140/0d294324-d35c-4bfc-afb7-583485593bb2)

 
**3.2 : Désactiver l'authentification par mot de passe**      
![image](https://github.com/techerbeatrice/checkpoint_03_TSSR/assets/138071140/84401b84-d94d-4b59-9071-e3e95e67bade)

___

## Partie 4 : Filtrage et analyse réseau  
____

**Question 4.1 : Analyse de règles de filtrage**  
  
Quelles sont actuellement les règles appliquées sur Netfilter ?    
Quels types de communications sont autorisées ?       
Et quels types sont interdites ?  

**4.1 : Analyse de règles de filtrage**
Il n'y a aucune règle de filtrage.     
![image](https://github.com/techerbeatrice/checkpoint_03_TSSR/assets/138071140/c1edb17f-8b58-40a7-9447-cfd30d7dcfe5)

![image](https://github.com/techerbeatrice/checkpoint_03_TSSR/assets/138071140/54a3118e-37d2-42b8-931a-3d943b15d961)

___

**Question 4.2 : Paramétrage avec nftables**  

Ajoute les règles nécessaires pour autoriser bareos actuellement installé sur le serveur à  
communiquer avec les clients bareos potentiellement présents sur l'ensemble des machines du réseau local sur lequel se trouve le serveur.   

Rappel : Bareos utilise les ports TCP 9101 à 9103 pour la communication entre ses différents composants.   

**Se déplacer dans le répertoire **etc/bareos** et Création d'un fichier de règles personnalisées pour bareos     
![image](https://github.com/techerbeatrice/checkpoint_03_TSSR/assets/138071140/77dcd543-2db3-40ec-b71a-92596d1d76c5)

___  

## Partie 5 : Sauvegardes**  

Les composants bareos-dir, bareos-sd et bareos-fd sont installés avec une configuration par défaut.    

___

**Question 5.1 : Les composants de bareos**  

Explique succinctement les rôles respectifs des 3 composants bareos installés sur la VM.    

**5.1 : Rôles des composants de bareos**  
Le Bareos Director orchestre l'ensemble du processus de sauvegarde,   
le Bareos Storage Daemon gère les supports de stockage,   
et le Bareos File Daemon collecte et transfère les données à sauvegarder.    
En travaillant ensemble, ces composants permettent la mise en place d'un système de sauvegarde complet et fiable.      

___

**Question 5.2 : Analyse de la configuration**     

**5.2 : Les clients configurés pour être sauvegardés par le serveur    
Liste les sauvegardes actuellement planifiées en précisant :  
Les dossiers et fichiers devant être sauvegardés   
Les planifications associées  
Les clients auxquels elles s'appliquent**    
   
![image](https://github.com/techerbeatrice/checkpoint_03_TSSR/assets/138071140/8b4457eb-4bbb-4fdc-ac93-84d4dcc0a678)

___

**Question 5.3 : Configuration**  

On souhaite que l'ensemble des fichiers, tel que défini dans le FileSet LinuxAll soit sauvegardés sur le client bareos-fd. 
Quelles sont les modifications de configuration à apporter ?  

**5.3a : Ajout de la ligne LinuxAll dans bareos-dir.conf**     
![image](https://github.com/techerbeatrice/checkpoint_03_TSSR/assets/138071140/b2e962fc-eb9b-45f8-9df4-46da190b9e75)

**5.3b : Mise à jour du FileSet**    
![image](https://github.com/techerbeatrice/checkpoint_03_TSSR/assets/138071140/5deda3a8-d0f5-4f3b-ae84-148617221e78)

___

## Partie 6 : Analyse de logs  

___

**Question 6.1 : Les échecs de connexion**   

**6.1 : Liste les 10 derniers échecs de connexion ayant eu lieu sur le serveur en indiquant pour chacun :   
La date et l'heure de la tentative     
L'adresse IP de la machine ayant fait la tentative**    

![image](https://github.com/techerbeatrice/checkpoint_03_TSSR/assets/138071140/9b87b3a1-c17f-419e-a54c-90cb430e17d3)


