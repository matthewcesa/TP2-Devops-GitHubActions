# TP DevOps Correction Docker

Correction de la partie Docker du module DevOps. 
Amusez-vous bien avec GitHub Actions !
Now, it's Matthew's repo.
 
## **2-1 Que sont les conteneurs de test ?**
Moteur principal (testcontainers) : Pilote Docker pour créer et détruire automatiquement un conteneur pendant la phase de test.
Connexion simplifiée (jdbc) : Permet de se connecter directement au conteneur via une URL JDBC (jdbc:tc:postgresql:...) sans configurer de code complexe.
Support PostgreSQL (postgresql) : Fournit un conteneur préconfiguré avec l'image PostgreSQL officielle (gestion des utilisateurs, mots de passe et état de démarrage).
Concrètement, ils permettend d'exécuter les test d'intégrations sur une vraie bdd postgreSQL temporaire, identitique à celle créé, puis de tout effacer une fois les test finis.



