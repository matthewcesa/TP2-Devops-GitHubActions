# TP DevOps Correction Docker

Correction de la partie Docker du module DevOps. 
Amusez-vous bien avec GitHub Actions !
Now, it's Matthew's repo.
 
## **2-1 Que sont les conteneurs de test ?**
Moteur principal (testcontainers) : Pilote Docker pour créer et détruire automatiquement un conteneur pendant la phase de test.
Connexion simplifiée (jdbc) : Permet de se connecter directement au conteneur via une URL JDBC (jdbc:tc:postgresql:...) sans configurer de code complexe.
Support PostgreSQL (postgresql) : Fournit un conteneur préconfiguré avec l'image PostgreSQL officielle (gestion des utilisateurs, mots de passe et état de démarrage).
Concrètement, ils permettend d'exécuter les test d'intégrations sur une vraie bdd postgreSQL temporaire, identitique à celle créé, puis de tout effacer une fois les test finis.


## **2-2 Dans quel but avons-nous besoin d'utiliser des variables sécurisées ?**
Similaire à un .env mais plus focus cloud et pipelines automatisés. Protège les identifiants et les clés d'accés pour éviter que les personnes ayant accés au repo puisse les voir.

## **2-3 Pourquoi avons-nous spécifié « besoins : construire et tester le backend » pour cette tâche ? Essayez peut-être sans, vous verrez !**
Pour ne pas publier du code cassé : L'image Docker est envoyée sur Docker Hub seulement si les tests passent au vert. Si on l'enlève : Les deux jobs se lancent en même temps. Tu risques de pousser une application buggée sur Docker Hub même si les tests échouent.

## **2-4 Dans quel but devons-nous envoyer des images Docker ?**
On envoie les images Docker sur Docker Hub pour les sauvegarder avant que VM temporaire de GitHub Actions ne soit détruite. Ça permet au serveur de production de télécharger directement cette image prête à l'emploi et de lancer l'application sans avoir à recompiler le code ou réinstaller des outils.

