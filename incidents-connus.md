# Incidents connus et solutions de repli

Veille IDOLEM Live, MKG8102, automne 2026. État au 7 octobre 2026.

Ce fichier consigne les pannes, les erreurs et les défauts rencontrés pendant le montage du dispositif, et ce qui a été fait. Un échec est un résultat à consigner, pas un problème à cacher.

## Erreurs de collecte

**6 octobre. Un prix faux relevé sur une page d'accueil.** La première fiche de Virtuel Yoga Santé portait 18 $ par mois, relevé sur la page d'accueil. Le 7 octobre, l'adresse a été corrigée vers la page des abonnements : 18 $ est le palier annuel, le mensuel sans engagement est à 25 $. Ce qui a été fait : adresse corrigée dans la table Sources, nouvelle fiche créée, la fiche du 6 octobre conservée comme trace. Règle tirée : une page d'accueil n'est jamais une cible de collecte.

**6 octobre. Une source hors périmètre.** MonYoga est une école de formation de professeurs, pas une plateforme de cours au consommateur. Passage consigné Partiel, aucune fiche. Ce qui a été fait : source écartée par le titulaire, motif hors périmètre. Elle reste dans la base avec son motif.

**7 octobre. Un mur anti-robot.** Oasis Yoga renvoie un écran reCAPTCHA au lieu du contenu. Passage consigné en Erreur. Ce qui a été fait : aucun contournement, source basculée au connecteur Manuel, relevé à la main requis. Un prix aperçu dans un résultat de moteur de recherche n'a pas été inscrit : un extrait de moteur de recherche n'est pas une source primaire.

**7 octobre. Une page servie dans la mauvaise région.** Nike Training Club : la version américaine a été servie malgré une session localisée au Canada. La disponibilité au Canada n'est donc pas établie par ce passage. La fiche a été rejetée par le titulaire, motif hors KIQ.

**7 octobre. Une lecture incomplète.** ALO Wellness Club : les questions de la foire aux questions reviennent sans leur réponse. Passage consigné Partiel et non Succès.

**7 octobre. Un résumé qui en disait plus que la page.** Le résumé de la fiche CAPRDN interprétait l'horaire. Il a été corrigé pour ne dire que ce que la page affiche : deux plages horaires, sans préciser s'il s'agit d'un cours ou de deux groupes.

## Défauts du dispositif

**Pas de clé d'unicité sur les fiches.** Relancer une collecte le même jour sur la même source peut créer un doublon. Repli actuel : la Skill vérifie les fiches déjà rattachées à la source avant d'écrire. Testé le 7 octobre sur Namaste Yoga Limoilou : le deuxième passage n'a produit aucune fiche. Correction prévue : un champ formule concaténant l'adresse exacte et la date de captation.

**Deux passages le même jour.** La convention `JC-AAAAMMJJ-CODESOURCE` ne le prévoit pas. Repli : suffixe -2. À trancher par le titulaire.

**La formule `Cote proposée` reste vide quand une note vaut 0.** Elle traite 0 comme une case vide. Touche S6, S7 et S8. Repli : cote calculée à la main selon la grille. Correction prévue : tester l'absence de valeur autrement que par la comparaison à vide.

**Le type d'erreur « anti-robot » n'existe pas dans la liste.** Le passage Oasis est classé « Autre ». Correction prévue : ajouter un choix dédié.

**Une ligne vide dans Fiches de veille.** Créée par accident le 7 octobre pendant le montage. À supprimer à la main.

## Changements d'architecture

**Les couleurs des listes de choix.** Le connecteur Airtable ne peut pas modifier la couleur d'une option existante. Les champs à choix ont été recréés avec leurs couleurs le 7 octobre et les valeurs recopiées telles quelles. Les anciens champs portent le suffixe « (ancien) ». Voir l'exception déclarée dans `declaration-usage-IA.md`.

**Les vues et l'ordre des colonnes.** Le connecteur ne peut ni créer une vue, ni masquer, ni déplacer une colonne. Repli : une interface Airtable de cinq pages, une par table, avec les champs dans l'ordre et les lignes colorées par statut.

**Le canal d'alerte.** Le flux n8n prévu au mandat n'a pas été monté. Il est remplacé par une tâche planifiée Claude qui lit les fiches validées et envoie l'alerte par Gmail.

**La tâche planifiée rangée dans le mauvais projet.** La première tâche de collecte apparaissait sous le projet de l'équipe. Elle a été recréée depuis le projet Veille IDOLEM Live, avec le fuseau horaire de Montréal.

## Limite de calendrier

Les relevés des 6 et 7 octobre sont des relevés de montage, étalés sur deux jours. Ils ne forment pas une base de comparaison homogène. Le relevé de référence est celui du mardi 13 octobre 2026. Un taux de réussite calculé sur moins de trois passages n'est pas interprétable.
