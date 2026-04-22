<img width="516" height="78" alt="image" src="https://github.com/user-attachments/assets/8d334908-eb63-47ef-9f93-d53db5ae0bb7" />
<img width="980" height="33" alt="image" src="https://github.com/user-attachments/assets/5bbdb65c-571e-493b-a9ba-6f53595aa379" />
<img width="723" height="349" alt="image" src="https://github.com/user-attachments/assets/b73b2953-f388-4afc-bc5f-5b3052f9df0a" />
<img width="698" height="401" alt="image" src="https://github.com/user-attachments/assets/94a0de22-ff02-4d51-aabc-1f9003a43022" />
Nous avons contourné les sécurités de l'application Android "UnCrackable Level 1" en utilisant Frida.

    Configuration : Nous avons relié ton PC à un émulateur Android via ADB et lancé le serveur Frida.

    L'attaque : Nous avons forcé l'application à démarrer en lui injectant trois scripts :

        Un script pour bloquer les vérifications Java (il a menti sur la version du système et la présence de fichiers root).

        Un script pour bloquer les vérifications natives en C/C++ (il a intercepté les appels système profonds).

        Un script pour cacher notre outil Frida.

    Le résultat : L'application a été trompée. Au lieu d'afficher une erreur et de se fermer, elle nous a laissé accéder à son écran principal.

    L'analyse finale : Nous avons utilisé "frida-trace" pour placer l'application sur écoute en temps réel et voir exactement quels chemins de fichiers elle essayait de lire en cachette pour nous détecter.
