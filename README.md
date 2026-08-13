# loc4loc-livrets

Hébergement public des livrets d'accueil LOC4LOC, servis en **accès direct** aux
URL encodées dans les **QR codes imprimés** présents dans les logements.

## Livrets publiés

| Fichier | URL publique (encodée dans le QR) |
|---|---|
| `castel-fr.pdf` | https://jonathan-bougouin.github.io/loc4loc-livrets/castel-fr.pdf |
| `castel-en.pdf` | https://jonathan-bougouin.github.io/loc4loc-livrets/castel-en.pdf |

Castel Saint-Nicolas — La Baule-Escoublac. Version française et version anglaise.

## ⚠️ Règle de permanence — à lire avant toute modification

Les QR codes sont **imprimés et posés dans les logements**. Ils encodent l'URL,
et l'URL est construite à partir du **nom du fichier**.

> **Ne jamais renommer, déplacer ou supprimer un PDF déjà publié.**
> Toute mise à jour de contenu se fait en **écrasant le fichier au même nom**.

Un fichier renommé = tous les QR imprimés correspondants deviennent morts, sans
aucun moyen de les corriger à distance.

### Mettre à jour un livret

1. Régénérer le PDF **en conservant le QR code existant** (le QR pointe vers le
   fichier lui-même : il ne doit pas changer, seul le contenu autour évolue).
2. Remplacer le fichier à la racine, **au même nom exact**.
3. Commiter et pousser sur `main`.

La publication est automatique : GitHub Pages sert la branche `main` et se
rafraîchit environ une minute après le push. L'URL reste identique — les QR
imprimés restent valables.

### Ajouter un nouveau livret

Déposer le PDF à la racine avec un nom stable et explicite, en minuscules et sans
accent, suffixé par la langue : `<logement>-<langue>.pdf`
(ex. `castel-fr.pdf`, `castel-en.pdf`). Générer ensuite le QR code sur l'URL
correspondante **avant impression**, puis vérifier par décodage que le QR renvoie
bien l'URL exacte.

## Contraintes techniques du dispositif

- La publication repose sur **GitHub Pages en mode « Deploy from a branch »**,
  branche `main`, dossier `/ (root)` — réglage à conserver tel quel
  (Settings → Pages). Aucun workflow n'est nécessaire : c'est volontaire, pour
  que le dispositif ne dépende d'aucune brique susceptible de casser.
- Le fichier `.nojekyll` désactive le moteur Jekyll et garantit que les PDF sont
  servis tels quels. **Ne pas le supprimer.**
- Le dépôt doit rester **public** : GitHub Pages sur dépôt privé exige un plan payant.
- Les PDF sont servis en `Content-Type: application/pdf`, sans page intermédiaire,
  sans redirection et sans authentification — le scan du QR ouvre directement le document.
- Les URL ne sont ni signées ni expirantes : elles sont valables indéfiniment.

## Charte des QR codes

Modules **#121A2C** (bleu nuit LOC4LOC) sur fond blanc, coins arrondis,
correction d'erreur niveau **H**. Taille d'impression recommandée : **30 mm minimum**
(en deçà de ~24 mm, la marge de lecture devient insuffisante en lumière faible).
