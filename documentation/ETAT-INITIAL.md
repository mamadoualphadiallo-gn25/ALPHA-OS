# État initial vérifié — ALPHA OS

Date : 2026-11-21

## Dépôt
Le dépôt GitHub ALPHA-OS a été initialisé. Le premier commit contient le README de démarrage.

## Source de développement retrouvée
L'archive de phase 3 retrouvée dans la conversation contient 25 fichiers :
- noyau x86-64 en C et assembleur ;
- initialisation GDT/IDT et exceptions CPU 0 à 31 ;
- allocateur de pages physiques (PMM) ;
- gestion mémoire virtuelle x86-64 à quatre niveaux ;
- tests hôtes et vérification statique ELF ;
- Makefile et workflow CI initial.

## Tests relancés localement
La commande `make clean test` a réussi :
- compilation du noyau ELF64 x86-64 ;
- 14 contrôles statiques du noyau ;
- tests PMM ;
- tests de calcul VM.

## Limites
- Le code source de phase 3 n'a pas encore été importé dans l'arborescence GitHub.
- La cible `make iso` est explicitement inachevée dans le Makefile actuel.
- Aucun démarrage VirtualBox n'a été vérifié.
- Le dépôt ne doit pas être présenté comme un OS installable à ce stade.

## Prochaines étapes
1. Importer l'ensemble des fichiers source de phase 3 dans le dépôt.
2. Corriger le packaging Limine et la cible ISO.
3. Ajouter une CI qui compile, teste et publie l'ISO comme artefact.
4. Démarrer l'ISO dans VirtualBox et vérifier l'affichage série/framebuffer.
