# Controle documentaire RAJA NEXT - version navigateur

Analyse un export HTML d'une page Confluence directement dans le navigateur, sans serveur, sans jeton Atlassian et sans connexion a Confluence. La page d'entree est [navigateur.html](navigateur.html).

## Utilisation

1. Ouvrez la page Confluence a relire et attendez son chargement. Enregistrez-la avec `Ctrl+S` au format **Page Web HTML uniquement** (`.html` ou `.htm`).
2. Ouvrez [navigateur.html](navigateur.html), selectionnez ce fichier, puis cliquez sur **Analyser la page**. Taille maximale : 12 Mo.
3. Consultez les points **A corriger**, **A verifier**, **Detectes** et **Non applicables**. Utilisez les filtres, **Telecharger TXT** ou **Enregistrer en PDF** (impression du navigateur).

Le fichier selectionne est lu localement par JavaScript et n'est pas envoye a un serveur. Un export "HTML uniquement" peut omettre les images et des metadonnees de macros Confluence : les controles correspondants doivent etre confirmes sur la page source. Un rapport favorable ne valide ni l'exactitude metier ni l'etat Review dans Comala.

## Publication sur GitHub Pages

Utilisez de preference un **depot dedie** a cette version statique, contenant uniquement :

- [navigateur.html](navigateur.html)
- [style.css](style.css)
- [Raja-removebg-preview.png](Raja-removebg-preview.png)
- ce fichier de notice, renomme `README.md` dans le depot dedie

Sur GitHub, creez le depot et ajoutez ces fichiers a sa racine. Dans **Settings > Pages**, choisissez **Deploy from a branch**, la branche `main`, puis le dossier `/(root)` et enregistrez. Une fois le site publie, ouvrez `https://VOTRE-COMPTE.github.io/NOM-DU-DEPOT/navigateur.html`. Les liens de la page sont relatifs pour fonctionner sous ce chemin.

**Ne publiez jamais** `token.txt`, de pages exportees, des rapports internes ou d'autres donnees confidentielles. Verifiez les regles de votre organisation avant de publier : selon la configuration du depot et de Pages, le site peut etre accessible publiquement. Un fichier deja publie doit etre considere comme expose, meme s'il est supprime plus tard.

## Limites

- La version navigateur ne lit pas une URL Confluence et ne verifie pas les droits, les etiquettes, l'arborescence ni l'etat du workflow.
- Les statuts `VERIFY` signalent des points a relire, et non une non-conformite prouvee.
- GitHub Pages heberge la page statique, mais n'execute pas les scripts PowerShell de la version locale.
