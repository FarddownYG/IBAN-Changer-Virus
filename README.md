IBAN Replacer (Windows)
Un petit outil Python pour surveiller le presse-papiers Windows et remplacer automatiquement un IBAN copié par un IBAN fixe.

⚙️ Fonctionnalité
écoute le presse-papiers (polling)
détecte un IBAN (format FRXX... ou autres pays)
si IBAN copié ≠ nouvel_iban, remplace par nouvel_iban
mode console avec logs de changements

📁 Contenu
iban-replacer.py : script principal
requirements.txt (optionnel)
README.md
🛠 Quoi modifier
Dans iban-replacer.py :

nouvel_iban = "FR7630006000011234567890189"
modifiez avec votre IBAN cible

📦 Installation
▶️ Exécution
python iban-replacer.py
Copiez un IBAN
Le script le remplace par nouvel_iban (si IBAN détecté)
Arrêt : Ctrl+C

🧾 Exemple de sortie
Presse-papiers changé vers : 'FR...
IBAN remplacé par : FR7630006000011234567890189

🛡 Notes
conçu pour Windows (module win32clipboard)
valide format IBAN et évite boucle infinie (ne remplace pas si déjà nouvel_iban)
supprime \r\n pour éviter non détection

📌 Améliorations possibles
hook système (win32 API) au lieu de polling
option --no-replace / mode démo
sauvegarde log
prise en charge de l’IBAN en texte brut / formaté
