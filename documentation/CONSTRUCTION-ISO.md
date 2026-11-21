# Construction de l'image ALPHA OS

La cible ISO utilise Limine comme chargeur de démarrage. Le noyau ALPHA OS reste un noyau indépendant en C et assembleur.

## Dépendances

Clang, LLD, GCC, Make, Git, Python 3 et xorriso. La version Limine binaire est épinglée à `v12.9.6` dans le Makefile.

## Commandes

```sh
make clean test
make iso
```

La cible `make iso` récupère Limine, prépare une image hybride BIOS/UEFI, génère l'image avec xorriso et applique `limine bios-install`. L'image attendue est `build/alpha-os.iso`.

La compilation de l'ISO ne garantit pas à elle seule que le noyau démarre sur chaque configuration. Le démarrage et les sorties série/framebuffer doivent encore être vérifiés dans VirtualBox.
