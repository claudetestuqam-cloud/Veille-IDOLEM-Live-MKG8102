# Veille IDOLEM Live

Prototype de veille marketing individuel. MKG8102, Veille marketing, ESG UQAM, automne 2026.
Titulaire : Zakaria Jouahi. Version 1.0, 7 octobre 2026.

## Ce que fait le dispositif

Il surveille les concurrents québécois du yoga en ligne et en studio pour éclairer une décision de la Direction générale d'IDOLEM Live : ce qui est inclus dans l'abonnement 2027, et à quel prix.

**KIQ-1.** D'ici le 30 novembre 2026, les concurrents québécois du yoga en ligne et en studio déplacent-ils leur offre de rétention vers un accès aux cours virtuels inclus sans supplément et sans engagement annuel, et à quel prix affiché?

Trois hypothèses rivales, écrites avant la collecte : H1 statu quo, H2 bascule, H3 déplacement vers l'essai gratuit et la souplesse d'annulation.

## Architecture

Claude raisonne, Airtable mémorise, les serveurs MCP exécutent.

| Étape du cycle | Outil | Ce qui se passe |
|---|---|---|
| Besoin | Table KIQ | La question, les hypothèses, les indicateurs, l'angle mort |
| Sourcing | Tables Acteurs et Sources | Une page par ligne, avec son biais connu et sa grille de fiabilité P, I, H |
| Collecte | Firecrawl (MCP) | Une passe par source, le mardi, par tâche planifiée à 11 h 30 |
| Traitement | Claude et la Skill `fiche-de-veille-idolem-live` | Un fait par fiche, extrait mot pour mot, cotation, rattachement à une hypothèse |
| Mémoire | Airtable (MCP) | Cinq tables reliées, une ligne au Journal par passage |
| Validation | Humain | Statut, Validé par et Motif de rejet ne sont jamais écrits par le modèle |
| Diffusion | Tâche planifiée Claude et Gmail (MCP) | Alerte par courriel quand un seuil est franchi, fiches validées seulement |

## Contenu du dépôt

- `SKILL.md` : la Skill qui transforme une page collectée en fiche de veille conforme. Elle est exécutable seule : mandat, méthode pas à pas, champs exacts, règles de cotation, biais à nommer, cas d'erreur, exemple conforme.
- `journal-de-collecte.md` : les dix passages consignés au 7 octobre 2026, réussis ou non.
- `grille-fiabilite.md` : la méthode de cotation des sources et les notes P, I, H de chaque source.
- `incidents-connus.md` : les pannes, les erreurs et les défauts rencontrés, avec ce qui a été fait.
- `gabarit-brief.md` : le gabarit de brief BLUF et le gabarit d'alerte.
- `declaration-usage-IA.md` : ce que l'IA a fait, ce qu'elle n'a pas fait, et l'exception à déclarer.
- `README.md` : ce document.

## Ce qui ne vit pas ici

Les fiches, les sources et le journal vivant sont dans Airtable. Ce dépôt documente la méthode, Airtable est le résultat vivant. État de la base au 7 octobre 2026 : 8 sources (4 actives, 3 à vérifier, 1 écartée), 10 passages au Journal, 8 fiches (7 validées, 1 rejetée pour motif hors KIQ).

## La base Airtable

Base « Veille MKG8102 - IDOLEM Live », cinq tables.

| Table | Une ligne égale |
|---|---|
| KIQ | une question |
| Acteurs | un acteur surveillé |
| Sources | une page |
| Fiches de veille | un fait |
| Journal de collecte | un passage |

Chaque fiche est reliée à sa Source, son Acteur, sa KIQ et sa Collecte d'origine. On remonte d'une affirmation jusqu'à la page en quatre clics.

La table Sources calcule la performance du dispositif à partir du Journal : passages consignés, passages réussis, taux de réussite, éléments retenus cumulés. Un passage Partiel ou en Erreur ne compte pas comme une réussite.

Une interface « Veille IDOLEM Live » présente les cinq tables, les lignes colorées selon leur statut.

## Les deux points de contrôle humain

1. **Avant la base.** Toute fiche naît au statut `À valider`. Une fiche non validée n'est ni citée, ni déclencheuse d'alerte. Les motifs de rejet sont une liste fermée : date inventée, citation inexacte, hors KIQ.
2. **Avant la diffusion.** Une alerte ne se rédige qu'à partir de fiches au statut `Validée`.

## Seuils d'alerte

- une fiche validée de pertinence 4 ou 5 rattachée à H2;
- une variation de plus de 15 % du prix mensuel affiché par rapport au relevé de référence du 13 octobre 2026;
- l'apparition de la mention « inclus » ou « sans supplément » associée à l'accès en ligne;
- un allongement de la durée d'essai gratuit affichée.

La tâche d'alerte tourne chaque jour de semaine. Elle n'envoie rien quand aucun seuil n'est franchi, et elle marque chaque fiche déjà signalée pour ne pas l'envoyer deux fois.

## Reproduire le dispositif

1. Créer un projet Claude et y coller les instructions du projet (mandat, KIQ, règles de cotation, règles de qualité).
2. Téléverser la Skill : compresser le dossier qui contient `SKILL.md`, puis Claude, Personnaliser, Skills, téléverser.
3. Activer les connecteurs Firecrawl, Airtable et Gmail.
4. Copier la base modèle du cours, puis remplir KIQ, Acteurs et Sources.
5. Lancer une collecte : « Collecte [adresse exacte] avec Firecrawl. Fais-en une fiche pour KIQ-1, statut à valider, et ajoute la ligne au Journal. »
6. Valider ou rejeter chaque fiche à la main dans Airtable.
7. Créer deux tâches planifiées : la collecte hebdomadaire du mardi, et l'alerte par courriel des jours de semaine.

Aucune clé d'accès, aucun jeton et aucun mot de passe ne figure dans ce dépôt, dans la Skill ou dans la base.

## Limites connues

- **Pas de clé d'unicité sur les fiches.** Relancer une collecte le même jour sur la même source peut créer un doublon. Le Journal, lui, est protégé par sa convention d'identifiant `JC-AAAAMMJJ-CODESOURCE`.
- **Une source protégée par un anti-robot** (Oasis Yoga). Le connecteur reçoit un écran de vérification. L'échec est consigné au Journal, aucun contournement n'est tenté, le relevé se fait à la main.
- **Relevés de montage.** Les relevés des 6 et 7 octobre 2026 ont été faits pendant la construction du dispositif. Le relevé de référence est celui du premier passage automatisé, le mardi 13 octobre 2026.
- **Angles morts assumés.** Les raisons réelles de départ des membres relèvent de données internes, exclues par principe. Les professeurs indépendants vendent par messagerie privée et bouche-à-oreille : seul un échantillon nommé est observable.
- **Sources ouvertes seulement.** Aucune donnée interne, aucune donnée personnelle, aucun contenu derrière une authentification.

## Usage de l'IA

Le prototype est opéré au niveau AIAS 4. La Skill, ce document et les fiches sont rédigés avec Claude. Les validations, les rejets et les décisions de périmètre sont humains.
