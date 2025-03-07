## Partie 1 : Gestion des utilisateurs

Q.2.1.1

![Capture d'écran 2025-03-07 110540](https://github.com/user-attachments/assets/86e4b831-68ab-4503-9721-643284370749)

Q.2.1.2

* Choisir un mot de passe sécurisé.
* Désactiver l'accès direct à l'utilisateur root.
* Changer régulièrement de mot de passe pour renforcer la sécurité

## Partie 2 : Configuration de SSH

Q.2.2.1 

![Capture d'écran 2025-03-07 111258](https://github.com/user-attachments/assets/bcbe575e-b9e6-4d5a-a341-6738440730fd)


Pour appliquer le changement sur le serveur sshd

![Capture d'écran 2025-03-07 111530](https://github.com/user-attachments/assets/bf181851-3b10-4765-9055-b84905a418ec)

Q.2.2.2 


![Capture d'écran 2025-03-07 111752](https://github.com/user-attachments/assets/027bf2b1-16b3-4018-9d1e-fa863b5b8889)

![Capture d'écran 2025-03-07 111834](https://github.com/user-attachments/assets/92161744-30e1-45fc-8b58-e543187a1dfd)

Q.2.2.3


![Capture d'écran 2025-03-07 112214](https://github.com/user-attachments/assets/5ef1eeac-63cf-48b8-941e-d2d4eda43459)


## Partie 3 : Analyse du stockage

Q.2.3.1


![Capture d'écran 2025-03-07 112528](https://github.com/user-attachments/assets/e74d24bf-6e0b-4960-985d-9665b8dfb677)

Q.2.3.2


![Capture d'écran 2025-03-07 112720](https://github.com/user-attachments/assets/d1033d7f-7862-4230-8437-6b2162843c98)

Q.2.3.3

![Capture d'écran 2025-03-07 114059](https://github.com/user-attachments/assets/1dcd06c6-5372-4d9e-b85d-0397bfaa92a7)


![Capture d'écran 2025-03-07 114128](https://github.com/user-attachments/assets/35022f03-d43b-4692-afa3-163dd83640ec)




Pour ajouter le disque au RAID il faut utiliser cette commande : mdadm --manage /dev/md0 --add  /dev/sdb1 


![Capture d'écran 2025-03-07 114619](https://github.com/user-attachments/assets/9fab332c-f31b-4f84-968f-2bdda293374f)


Q.2.3.4 


![Capture d'écran 2025-03-07 120733](https://github.com/user-attachments/assets/2a4abb64-b52e-4fe9-b2fb-d1dfa1490479)


![Capture d'écran 2025-03-07 121033](https://github.com/user-attachments/assets/901cfecb-e0cd-41e9-bae0-6cacf0771e39)


![Capture d'écran 2025-03-07 121411](https://github.com/user-attachments/assets/11e94ba4-359c-42ff-b1a0-43bce6126a38)


![Capture d'écran 2025-03-07 121518](https://github.com/user-attachments/assets/00b988f0-86ef-42f9-9623-0a95745f95ce)

Q.2.3.5


![Capture d'écran 2025-03-07 121518](https://github.com/user-attachments/assets/4c468461-4437-4acf-902f-db9438ffab2e)


## Partie 4 : Sauvegardes

Q.2.4.1

# Rôles et Fonctions des Composants Bareos

## 1. bareos-dir (Directeur de Sauvegarde)
**Rôle** : C'est le cœur du système de gestion des sauvegardes. Il gère l'ensemble des tâches de sauvegarde et de restauration. Il est responsable de la planification, de la gestion des jobs, et de la coordination entre les différents clients et serveurs de stockage.

**Fonctions principales** :
- Planifie et lance les sauvegardes.
- Gère les fichiers de configuration.
- Dirige les demandes de sauvegarde vers les autres composants (Serveur de stockage et Clients de sauvegarde).
- Communique avec la base de données Bareos pour stocker les informations sur les jobs de sauvegarde.

## 2. bareos-sd (Serveur de Sauvegarde)
**Rôle** : Le serveur de stockage est responsable de la gestion des données sauvegardées. Il reçoit les données des clients et les stocke dans un emplacement spécifié.

**Fonctions principales** :
- Reçoit les données envoyées par le client de sauvegarde (bareos-fd).
- Sauvegarde les données sur un disque local, un support externe ou une autre destination configurée.
- Effectue la gestion du stockage (création de volumes, gestion des supports, etc.).
- Peut être configuré pour travailler avec différents types de supports comme des disques, des bandes ou des serveurs de stockage distants.

## 3. bareos-fd (Client de Sauvegarde)
**Rôle** : Le client de sauvegarde est installé sur la machine à sauvegarder (le client). Il gère l'accès aux fichiers et aux données à sauvegarder sur cette machine et envoie ces données au serveur de stockage (bareos-sd) via le directeur (bareos-dir).

**Fonctions principales** :
- Exécute les sauvegardes locales (sauvegarde des fichiers du système local du client).
- Envoie les données sauvegardées au serveur de stockage (bareos-sd).
- Permet la restauration des fichiers en fonction des demandes envoyées par le directeur (bareos-dir).

  

## Partie 5 : Filtrage et analyse réseau

Q.2.5.1


![Capture d'écran 2025-03-07 122859](https://github.com/user-attachments/assets/4d4249be-de42-4234-be1d-4f87c860ab46)

Q.2.5.2

ct state established,related accept : Autorise le trafic faisant partie d'une connexion existante
- lifname "lo" accept : Autorise toutes les communications sur l'interface loopback
- tcp dport 22 accept : Autorise les connexions entrantes en SSH 
- ip protocol icmp accept : Autorise les requêtes ICMP 
- ip6 nexthdr ipv6-icmp accept : Autorise les requêtes ICMPv6


Q.2.5.3

- ct state invalid drop : bloquer les paquets qui sont invalides

Q.2.5.4 


![Capture d'écran 2025-03-07 125642](https://github.com/user-attachments/assets/3ec04ce0-73d4-4716-a2a0-74d034e82e37)

## Partie 6 : Analyse de logs

Q.2.6.1 


![Capture d'écran 2025-03-07 134627](https://github.com/user-attachments/assets/e8f60d87-b724-4937-9534-ed906f78a0c4)


