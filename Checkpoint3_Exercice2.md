Partie 1 : Gestion des utilisateurs

Q.2.1.1

![Capture d'écran 2025-03-07 110540](https://github.com/user-attachments/assets/86e4b831-68ab-4503-9721-643284370749)

Q.2.1.2

* Choisir un mot de passe sécurisé.
* Désactiver l'accès direct à l'utilisateur root.
* Changer régulièrement de mot de passe pour renforcer la sécurité

Partie 2 : Configuration de SSH

Q.2.2.1 

![Capture d'écran 2025-03-07 111258](https://github.com/user-attachments/assets/bcbe575e-b9e6-4d5a-a341-6738440730fd)


Pour appliquer le changement sur le serveur sshd

![Capture d'écran 2025-03-07 111530](https://github.com/user-attachments/assets/bf181851-3b10-4765-9055-b84905a418ec)

Q.2.2.2 


![Capture d'écran 2025-03-07 111752](https://github.com/user-attachments/assets/027bf2b1-16b3-4018-9d1e-fa863b5b8889)

![Capture d'écran 2025-03-07 111834](https://github.com/user-attachments/assets/92161744-30e1-45fc-8b58-e543187a1dfd)

Q.2.2.3


![Capture d'écran 2025-03-07 112214](https://github.com/user-attachments/assets/5ef1eeac-63cf-48b8-941e-d2d4eda43459)


Partie 3 : Analyse du stockage

Q.2.3.1


![Capture d'écran 2025-03-07 112528](https://github.com/user-attachments/assets/e74d24bf-6e0b-4960-985d-9665b8dfb677)

Q.2.3.2


![Capture d'écran 2025-03-07 112720](https://github.com/user-attachments/assets/d1033d7f-7862-4230-8437-6b2162843c98)

Q.2.3.3

![Capture d'écran 2025-03-07 114059](https://github.com/user-attachments/assets/1dcd06c6-5372-4d9e-b85d-0397bfaa92a7)


![Capture d'écran 2025-03-07 114128](https://github.com/user-attachments/assets/35022f03-d43b-4692-afa3-163dd83640ec)




Pour ajouter le disque au RAID il faut utiliser cette commande : mdadm --manage /dev/md0 --add  /dev/sdb1 


![Capture d'écran 2025-03-07 114619](https://github.com/user-attachments/assets/9fab332c-f31b-4f84-968f-2bdda293374f)
