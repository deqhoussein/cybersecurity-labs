# Attaque DTP (Dynamic Trunking Protocol)

**Objectif** : Forcer un switch à établir un trunk VLAN avec l’appareil de l’attaquant pour accéder au trafic de plusieurs VLANs.

**Méthode** : Exploiter le protocole DTP pour activer un trunk sur un port non configuré.

## Étapes et Commandes

1. **Lancer Yersinia en mode interactif** :
   ```bash
   sudo yersinia -I

2.Activer l’attaque DTP :
Dans Yersinia :
Tapez g pour accéder aux protocoles et sélectionnez DTP.
Appuyez sur x pour activer Enable trunking.
Appuyez sur S pour sauvegarder les paquets.
Résultat Attendu et Vérification
Résultat : Le port connecté à Kali Linux doit passer en mode trunk.
Vérification : Sur le switch, utilisez :

show interface <port_number> switchport
Le port doit être en mode trunk et transporter plusieurs VLANs.


---

