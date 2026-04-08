[Retour à l'accueil](index.md)

# FAQ — MorseTrainer F6EYO ver. BETA

## Morse trainer F6EYO 1.1
Les améliorations sont :

La réduction de la latence entre le caractère sonore et la frappe au clavier, ce qui améliore la limpidité de la saisie.

Le choix, dans le menu Paramètres, du nombre de séries de 5 caractères (de 5 à 18), soit de 25 à 90 caractères au total.
(La version 1.0 en comptait 5, soit 25 caractères.)

L’affichage des résultats des révisions sous forme de séries de 5 caractères.

La possibilité d’effectuer un copier/coller dans la fenêtre des dictées.

## Le logiciel est-il gratuit ?
Oui, il est entièrement gratuit.

## Pourquoi Windows affiche un avertissement à l’installation ?
Parce que le logiciel n’est pas signé avec un certificat payant.  
C’est normal et sans danger.

## Où sont stockés les fichiers du logiciel ?
Dans ces deux dossiers :

C:\Users\<User>\AppData\Local\MorseTrainerBETA  
C:\Users\<User>\AppData\Roaming\MorseTrainer

## Comment désinstaller MorseTrainer ?
Il suffit d'aller dans panneau de configuration puis de cliquer sur désinstallation de programme, de sélectionner dans la liste Morse trainer BETA ver. x.x puis de le désinstaller comme n'imoorte quel autre programme. 

## Le logiciel fonctionne-t-il hors ligne ?
Oui, tout fonctionne sans connexion Internet.

## Morse Trainer F6EYO fonctionne-t-il sous Linux ou macOS ?
Non, uniquement sous Windows pour le moment.

## Commen résoudre cette erreur au chargement de Morse trainer F6EYO ?
- erreur au lancement : 
- Traceback (most recent call last):
- File "morse_trainer.py", line 910, in <module>
- File "morse_trainer.py", line 907, in generer_bip_long
- File "pygame\sndarray.py", line 92, in make_sound
- ValueError: Array depth must match number of mixer channels

Indications :
La plus part du temps c’est la configuration audio de l’ordinateur qui pose problème.
Et cette erreur PyGame est très typique d’un cas précis.

🎯 Cause la plus fréquente : le mixer PyGame démarre en MONO sur certains PC.

🟦 Comment corriger ce PC en particulier ?

Voici les solutions dans l’ordre, de la plus simple à la plus radicale.

✅ 1. Vérifier le périphérique audio par défaut Sur Windows :

- Clic droit sur l’icône du son
- Paramètres audio
- Vérifier :
- le périphérique de sortie sélectionné
- qu’il n’est pas en mono
- qu’il n’est pas désactivé
- qu’il n’est pas un périphérique HDMI sans audio

👉 Beaucoup de PC basculent sur un “périphérique fantôme” (ex : écran HDMI).

✅ 2. Désactiver les périphériques audio inutiles Toujours dans les paramètres audio → Gérer les périphériques audio :
- désactiver les sorties HDMI inutiles 
- désactiver les casques Bluetooth non connectés 
- désactiver les drivers virtuels (VB-Audio, etc.), PyGame peut se tromper de périphérique si plusieurs sont actifs.
✅ 3. Vérifier que le périphérique n’est pas forcé en mono

Windows permet de forcer la sortie en mono :
Paramètres → Accessibilité → Audio →

👉 Désactiver “Audio mono”
Si cette option est activée, PyGame démarre en mono.

✅ 4. Réinstaller le driver audio
Sur certains PC, le driver Realtek ou USB est corrompu.
- Gestionnaire de périphériques 
- “Contrôleurs audio, vidéo et jeu” 
- Clic droit → Désinstaller 
- Redémarrer → Windows réinstalle automatiquement

🟦 5. Cas particulier : casque USB ou Bluetooth

Certains casques USB déclarent 1 seul canal.
Certains Bluetooth déclarent 2 canaux mais en mode “Hands-Free” (mono compressé).

Solution :

- déconnecter le casque
- relancer ton logiciel
- vérifier si l’erreur disparaît
Si oui → le casque est la cause.

## Autre message d'erreur au chargement de Morse trainer F6EYO ?
Traceback (most recent call last):
-  File "morse_trainer.py", line 910, in <module>
-  File "morse_trainer.py", line 907, in generer_bip_long
-  File "pygame\sndarray.py", line 92, in make_sound
ValueError: Array depth must match number of mixer channels

Solution : Appliquer le même protocole que ci-dessus



[Retour à l'accueil](index.md)

