# Eduportail

Portail d'accès aux services numériques pour un établissement scolaire, avec 5 espaces : Élève, Professeur, Parent, Administrateur d'établissement, Super administrateur.

## État actuel

Ce dépôt contient une **maquette front-end statique** (HTML/CSS, sans backend) : la page d'accueil de sélection d'espace et une page de connexion par espace, avec le thème de couleur propre à chacun. Les formulaires de connexion ne sont pas encore reliés à une base de données.

Le détail fonctionnel complet (fiche d'identité élève, gestion des établissements par RNE, recherche de bulletins par INE, Pronote, messagerie, orientation, etc.) est décrit dans [`docs/cahier-des-charges.md`](docs/cahier-des-charges.md).

## Structure du dépôt

```
eduportail/
├── index.html                              # Page d'accueil "Qui êtes-vous ?"
├── css/
│   └── styles.css                          # Styles partagés + thèmes par espace
├── espaces/
│   ├── eleve.html                          # Connexion — thème vert
│   ├── eleve-bureau.html                   # Bureau : Pronote, Messagerie, Mot de passe (EOE), Site du lycée, Bulletins, Orientation
│   ├── professeur.html                     # Connexion — thème bleu
│   ├── professeur-bureau.html              # Bureau : Pronote, Messagerie, Site du lycée
│   ├── parent.html                         # Connexion — thème bleu
│   ├── parent-bureau.html                  # Bureau : Pronote, Messagerie, Site du lycée, Valider l'orientation
│   ├── administrateur.html                 # Connexion — thème violet
│   ├── administrateur-bureau.html          # Bureau : Inscrire élève (INE), Bulletins, Certificat, Professeurs, Parents, Pronote, Messagerie
│   ├── super-administrateur.html           # Connexion — thème bleu cobalt
│   └── super-administrateur-bureau.html    # Bureau : Établissements, Inscription élève, Bulletins (INE), Orientation, Pronote, Livret scolaire, Messagerie
└── docs/
    └── cahier-des-charges.md               # Spécifications fonctionnelles complètes
```

Chaque page de connexion redirige vers son bureau correspondant après soumission du formulaire (redirection uniquement, sans vérification réelle des identifiants — l'authentification reste à brancher sur un backend).

## Prochaines étapes suggérées

- Choisir une stack backend (base de données + authentification) pour remplacer les formulaires statiques.
- Développer les onglets de l'espace Super administrateur (Établissements, Inscription élève, Bulletins officiels, Orientation, Pronote, Livret scolaire).
- Développer les onglets de l'espace Administrateur (inscription élève par INE, Professeurs, Parents, certificat de scolarité).
- Mettre en place la synchronisation des données à l'inscription (copie locale par établissement, cf. cahier des charges).

## Utilisation en local

Ouvrez simplement `index.html` dans un navigateur, ou servez le dossier avec un petit serveur local, par exemple :

```
npx serve .
```
