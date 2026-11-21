# ALPHA OS

ALPHA OS est un système d'exploitation expérimental x86-64 développé en C et assembleur, démarré avec le protocole Limine. Le projet est actuellement en phase de noyau et de validation de l'image ISO.

## État actuel

- Noyau freestanding x86-64 et point d'entrée assembleur.
- Initialisation GDT/IDT et gestion des exceptions CPU.
- Allocateur de mémoire physique (PMM).
- Bases de pagination x86-64 à quatre niveaux.
- Journalisation série et affichage framebuffer de base.
- Tests hôtes du PMM et des calculs de mémoire virtuelle.

Les tests locaux du noyau, du PMM et de la VM ont réussi. Le démarrage réel dans VirtualBox doit encore être validé.

## Compilation locale

Dépendances : clang, lld, gcc, make, python3, binutils, git et xorriso.

```sh
make clean
make test
make iso
```

L'image attendue est `build/alpha-os.iso`.

## Compilation GitHub

Le workflow `.github/workflows/build-iso.yml` est configuré pour compiler le projet, exécuter les tests, construire l'ISO et publier un artefact GitHub Actions. Pour le moment, il attend le fichier source `ALPHA-OS-phase4-source.zip` à la racine du dépôt.

Pour publier une version téléchargeable dans l'onglet **Releases**, crée un tag au format `v0.1.0`. Le workflow construit alors l'ISO et l'attache à la Release.

## Limites actuelles

ALPHA OS est un noyau expérimental, pas encore un système d'exploitation de bureau complet. Les pilotes clavier/souris, les processus utilisateur, le système de fichiers, le réseau et l'interface graphique complète restent à développer. L'ISO ne doit pas être considérée comme validée avant un démarrage réussi dans VirtualBox.
