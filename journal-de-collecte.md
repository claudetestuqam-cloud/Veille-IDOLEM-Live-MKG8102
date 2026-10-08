# Journal de collecte

Veille IDOLEM Live, MKG8102, automne 2026. Instantané de la table « Journal de collecte » d'Airtable au 7 octobre 2026. Le journal vivant est dans la base : ce fichier en est une copie datée.

Règle du dispositif : une ligne par source et par passage, sans exception. Les échecs se consignent comme les succès. Pas de ligne au journal, pas de collecte.

Opérateur de tous les passages : Zakaria Jouahi. Connecteur de tous les passages : Firecrawl.

## Les dix passages

| Identifiant | Date et heure | Source | Résultat | Retenus | Écartés |
|---|---|---|---|---|---|
| JC-20261006-CAPRDN | 6 oct., 12 h 45 | S3 CAPRDN | Succès | 1 | 2 |
| JC-20261006-VIRTUELYOGASANTE | 6 oct., 12 h 45 | S1 Virtuel Yoga Santé | Succès | 1 | 3 |
| JC-20261006-MONYOGA | 6 oct., 12 h 45 | S5 MonYoga | Partiel | 0 | 4 |
| JC-20261007-OASISYOGA | 7 oct., 12 h 05 | S4 Oasis Yoga | Erreur | 0 | 0 |
| JC-20261007-MONYOGAVIRTUEL | 7 oct., 12 h 05 | S2 Mon Yoga Virtuel | Succès | 1 | 4 |
| JC-20261007-VIRTUELYOGASANTE | 7 oct., 12 h 05 | S1 Virtuel Yoga Santé | Succès | 1 | 1 |
| JC-20261007-NAMASTEYOGA | 7 oct., 12 h 42 | S6 Namaste Yoga Limoilou | Succès | 2 | 6 |
| JC-20261007-NIKETRAININGCLUB | 7 oct., 14 h 15 | S8 Nike Training Club | Succès | 1 | 6 |
| JC-20261007-ALOWELLNESSCLUB | 7 oct., 14 h 15 | S7 ALO Wellness Club | Partiel | 1 | 6 |
| JC-20261007-NAMASTEYOGA-2 | 7 oct., 14 h 15 | S6 Namaste Yoga Limoilou | Succès | 0 | 8 |

Bilan : 10 passages, 7 succès, 2 partiels, 1 erreur. 8 éléments retenus, donc 8 fiches. 40 éléments vus et écartés.

## Mardi 6 octobre 2026

**S3 CAPRDN.** Page collectée entièrement. Retenu : le prix de la session, le format virtuel imposé et l'horaire. La page affiche des champs de gabarit non remplis, « This is some text inside of a div block », à la place de l'âge minimal et de la durée. Ces champs sont laissés vides dans la fiche plutôt que devinés.

**S1 Virtuel Yoga Santé.** L'adresse en .ca redirige vers le .com. Retenu : le prix d'entrée affiché avec sa condition de facturation. Limite consignée : l'adresse inscrite était une page d'accueil, ce que les règles interdisent. La page des abonnements est à substituer au prochain passage.

**S5 MonYoga.** La page a répondu, mais aucun élément ne sert les indicateurs, d'où le résultat Partiel. MonYoga est une école de formation de professeurs et non une plateforme de cours au consommateur. Aucune fiche. Arbitrage humain demandé. Décision du titulaire : source écartée, motif hors périmètre. Elle reste dans la base, on ne supprime pas.

## Mercredi 7 octobre 2026

**S4 Oasis Yoga.** Échec par mur anti-robot. Code 200, mais le contenu rendu est un écran reCAPTCHA « Verifying that you are not a robot ». Aucun contournement tenté, par règle. Un résultat de moteur de recherche indiquait un prix pour cette source : il n'a pas été vu sur la page et n'est inscrit nulle part comme fait. Source basculée au connecteur Manuel.

**S2 Mon Yoga Virtuel.** Premier passage. Retenu : les trois paliers d'abonnement avec leur condition de facturation et la durée de l'essai gratuit. Écartés : les témoignages, la liste des instructeurs, le catalogue et la bande de logos de presse.

**S1 Virtuel Yoga Santé, deuxième passage, adresse corrigée.** La fiche du 6 octobre portait 18 $ par mois, relevé sur la page d'accueil. La page des abonnements montre que 18 $ est le palier annuel et que le mensuel sans engagement est à 25 $. Une page d'accueil ne donne pas le prix, elle donne l'argument de vente.

**S6 Namaste Yoga Limoilou.** Deux faits retenus : le forfait mensuel illimité à 105 $, limité aux cours en studio, et l'offre d'entrée pour nouveaux membres. Le contenu collecté ne contient aucune mention d'un accès en ligne. Deux prix mensuels de référence ne concordent pas sur la page, 105 $ et 95 $ : les deux sont cités tels quels, sans arbitrage.

**S8 Nike Training Club.** Page collectée, mais c'est la version américaine en anglais qui a été servie malgré une session localisée au Canada. Aucun prix, aucune devise, aucun abonnement affiché. La fiche produite a été rejetée par le titulaire, motif hors KIQ.

**S7 ALO Wellness Club.** Résultat Partiel : les questions de la foire aux questions s'affichent sans leur réponse, dont celle sur le coût. Limite d'adresse consignée : l'adresse inscrite est une racine de site, collectée sur consigne explicite du titulaire. Une métadonnée annonce un essai de 14 jours qui contredit le texte affiché : elle n'est inscrite nulle part comme fait.

**S6 Namaste Yoga Limoilou, deuxième passage du même jour.** Fait à la demande du titulaire pour contrôler les doublons. Les deux faits sont identiques à ceux du premier passage : aucune fiche produite, deux éléments écartés pour motif doublon. La convention d'identifiant ne prévoit pas deux passages le même jour : le suffixe -2 a été ajouté.

## Statut de ces relevés

Les relevés des 6 et 7 octobre sont des relevés de montage, faits à la main pendant la construction du dispositif. Ceux du 7 octobre sont faits un mercredi alors que le jour de relevé du dispositif est le mardi. Le relevé de référence est celui du premier passage automatisé, le mardi 13 octobre 2026.

Aucun passage n'a relevé de consigne adressée au modèle dans une page.
