---
layout: post
title: "Migration de domaine SEO : ce que j'ai perdu et comment je le récupère"
date: 2026-06-25 08:00:00 +0300
author: Miaro
tags: Web
image: /assets/images/blog/migration-domaine-seo.webp
description: "Retour d'expérience complet sur une migration de domaine SEO : de miarofandresena.github.io vers miarofandresena.com. Rangs perdus, causes, méthode de récupération. Par Miaro Fandresena."
faq:
  - q: "Combien de temps faut-il pour récupérer ses rangs après une migration de domaine ?"
    a: "La récupération est progressive : les premiers signaux positifs apparaissent en 4 à 8 semaines si la migration est techniquement correcte (301 en place, sitemap soumis, GSC notifiée). Une récupération complète prend généralement 3 à 6 mois. Sans notification dans Google Search Console via l'outil 'Changement d'adresse', le processus peut durer 12 à 18 mois ou ne jamais se terminer."
  - q: "Qu'est-ce que l'outil 'Changement d'adresse' de Google Search Console ?"
    a: "C'est un outil dans Google Search Console qui permet de notifier officiellement Google qu'un site a migré vers un nouveau domaine. Il accélère le transfert d'autorité du domaine source vers le domaine cible. Sans cette notification, Google redécouvre la migration uniquement par le crawl — ce qui prend beaucoup plus de temps."
  - q: "Les redirections 301 suffisent-elles pour une migration SEO réussie ?"
    a: "Les 301 sont nécessaires mais pas suffisantes. Il faut également : notifier Google Search Console via l'outil Changement d'adresse, soumettre le nouveau sitemap, mettre à jour tous les liens internes vers les nouvelles URLs, vérifier le canonical sur le nouveau domaine, et surveiller l'indexation semaine par semaine pendant 3 mois."
  - q: "Pourquoi un site disparaît-il de Google après une migration ?"
    a: "Plusieurs raisons possibles : Google n'a pas encore crawlé les nouvelles URLs en profondeur, l'autorité du domaine source n'a pas été transférée (absence de notification GSC), des pages ont des erreurs 404 ou des canonical incorrects, ou l'ancien domaine n'a plus de redirections actives. La disparition est souvent temporaire mais peut durer 6 à 12 mois sans action corrective."
key_points:
  - "La notification GSC « Changement d'adresse » est l'étape critique que 90 % des sites ratent"
  - "Les redirections 301 seules ne suffisent pas — le transfert prend 12 à 18 mois sans action"
  - "Récupération possible en 3 à 6 mois avec les 6 étapes concrètes du plan"
  - "Retour d'expérience réel : ce que j'ai raté sur mon propre site et comment je le corrige"
stats:
  - number: "12–18"
    label: "mois sans GSC"
  - number: "3–6"
    label: "mois de récup."
  - number: "6"
    label: "étapes du plan"
---

Je vais vous parler de quelque chose que je vis en ce moment.

Pas d'un client. De mon propre site.

Pendant des mois, **miarofandresena.github.io** était dans le top 10 sur Google pour "consultant SEO Madagascar". Trafic organique stable. Contacts entrants. Preuve que ce que je faisais fonctionnait.

Puis j'ai migré vers **miarofandresena.com**.

Et j'ai disparu.

Ce retour d'expérience est brutal et honnête. Si vous envisagez une migration de domaine — ou si vous venez d'en faire une et que vous observez une chute de rangs — c'est l'article que j'aurais voulu lire avant.

## Pourquoi j'ai migré : la décision logique, le risque sous-estimé

GitHub Pages est une solution gratuite et fiable pour héberger un site Jekyll. Mais `github.io` comme domaine a un problème : il ne vous appartient pas vraiment. C'est un sous-domaine de GitHub. L'autorité que vous construisez sur ce domaine dépend des décisions de GitHub, pas des vôtres.

Passer à `miarofandresena.com` était la bonne décision à long terme : domaine professionnel, indépendance, possibilité de le vendre ou de le transmettre. La direction était bonne.

Ce que j'ai sous-estimé, c'est l'impact sur le SEO à court et moyen terme.

## Ce que j'avais bien fait

Les redirections 301 étaient en place. Chaque URL de l'ancien domaine pointait vers la même URL sur le nouveau domaine. C'est la condition technique de base pour qu'une migration soit viable.

Le fichier `_config.yml` indiquait le nouveau domaine. Les canonical sur toutes les pages pointaient vers `miarofandresena.com`. Techniquement, la mise en place était correcte.

## Ce que j'avais raté — et la cause principale de la disparition

**L'outil "Changement d'adresse" de Google Search Console.**

C'est une fonction méconnue mais critique. Elle se trouve dans GSC → Paramètres → Changement d'adresse. Elle permet de notifier officiellement Google que votre site a migré, d'activer le transfert d'autorité accéléré, et de déclencher un recrawl priorisé du nouveau domaine.

Sans cette notification, Google redécouvre la migration uniquement via les 301 — ce qui peut prendre **12 à 18 mois** selon la fréquence de crawl de votre domaine.

L'ancienne URL GitHub était régulièrement crawlée parce qu'elle avait de l'historique. Le nouveau domaine `.com` n'avait aucun historique. Google l'a traité comme un site quasi-inexistant au moment de la migration.

Résultat : chute des rangs, quasi-disparition des SERP.

## Le diagnostic complet des causes

Voici ce que j'ai identifié comme problèmes cumulés :

### 1. Absence de notification GSC "Changement d'adresse"

Cause principale. Sans elle, le transfert d'autorité prend énormément de temps.

### 2. Faible DA du nouveau domaine au départ

`miarofandresena.com` avait un Domain Authority quasi-nul au départ. Tous les backlinks existants pointaient vers `miarofandresena.github.io`. Même avec les 301, le jus de lien se dilue dans la redirection.

### 3. Pas de demande d'indexation manuelle sur les pages prioritaires

Dans GSC, il est possible de demander l'indexation d'une URL spécifique via l'outil d'inspection. Je n'avais pas fait cela pour mes 5 à 10 pages les plus importantes.

### 4. Liens internes pas tous mis à jour

Certains articles pointaient encore vers des URLs en format `/2024/07/23/consultant-seo-a-madagascar/` au lieu de `/consultant-seo-madagascar/`. Ces liens internes vers des pages redirigées perdent une partie de leur efficacité.

### 5. Absence d'AggregateRating et de signaux de confiance forts

Sur un nouveau domaine, les signaux de confiance (avis, schema, mentions) sont plus importants encore. Mon site manquait d'AggregateRating activé et les pages de services étaient absentes.

## Le plan de récupération — ce que je fais maintenant

### Étape 1 : GSC "Changement d'adresse" (action immédiate, manuelle)

C'est la priorité absolue. Dans Google Search Console du domaine `.com` : Paramètres → Changement d'adresse → indiquer `miarofandresena.github.io` comme ancienne propriété.

Cette action ne peut pas être faite dans le code. Elle nécessite une connexion à Google Search Console.

### Étape 2 : Soumission du sitemap sur le nouveau domaine

Dans GSC du nouveau domaine : Sitemaps → soumettre `https://miarofandresena.com/sitemap.xml`.

### Étape 3 : Demandes d'indexation manuelle pour les pages prioritaires

Via l'outil d'inspection d'URL dans GSC, pour chaque page stratégique :
- `/consultant-seo-madagascar/`
- `/audit-seo-madagascar/`
- `/about/`
- `/contact/`
- Les 5 à 10 articles les plus importants

### Étape 4 : Reconstruction active de l'autorité

Les 301 transfèrent l'autorité, mais pas à 100 %. Pour compenser, il faut créer de nouveaux backlinks pointant directement vers le nouveau domaine `miarofandresena.com` :

- Mise à jour du profil LinkedIn avec le nouveau domaine
- Annuaires malgaches : [Annuaire.mg](https://annuaire.mg), ChambreTFT, FIVMPAMA — mettre à jour les fiches avec le nouveau domaine
- Demande de mise à jour aux sites qui avaient déjà un lien vers l'ancien domaine

### Étape 5 : Production de contenu accélérée

Un nouveau domaine se fait confiance par Google en partie via la régularité de publication et la profondeur thématique. Publier 2 articles/mois pendant 6 mois envoie un signal fort.

C'est la logique derrière le calendrier éditorial que j'ai mis en place : combler les lacunes de contenu identifiées par rapport aux concurrents et publier régulièrement.

### Étape 6 : Pages de services complètes

J'avais un site centré sur le blog, sans pages de services dédiées. Les concurrents ont des pages `/audit-seo-madagascar/`, `/netlinking/`, etc. J'ai créé ces pages en juin 2026 — elles donnent au domaine une profondeur thématique que le blog seul ne suffisait pas à créer.

## Ce que ça m'a appris sur la migration de domaine en SEO

**Une migration est une perte temporaire d'autorité, pas une perte permanente.** Les 301 fonctionnent. Le transfert se fait. Mais il faut du temps et des actions actives pour l'accélérer.

**La notification GSC est la seule étape vraiment critique que la plupart des guides omettent.** Tous parlent des 301. Peu insistent sur le "Changement d'adresse" dans Search Console.

**Un site avec moins de 6 mois sur un nouveau domaine est traité avec prudence par Google.** C'est normal. La patience et la régularité sont les seules réponses durables.

## Ce que vous devriez faire si vous planifiez une migration

### Avant la migration
- Documentez toutes vos URLs actuelles avec leur positionnement
- Faites un export GSC complet (clics, impressions, positions)
- Identifiez vos 20 pages les plus importantes (les priorités de récupération)

### Le jour de la migration
- Activez les 301 page par page, pas de redirection wildcard aveugle
- Vérifiez que le canonical pointe vers le nouveau domaine sur chaque page
- Soumettez le sitemap dans GSC immédiatement

### La semaine suivante
- Activez l'outil "Changement d'adresse" dans GSC
- Demandez l'indexation manuelle de vos 20 pages prioritaires
- Mettez à jour tous vos profils externes (LinkedIn, annuaires, réseaux) avec le nouveau domaine

### Les 3 mois suivants
- Surveillez la couverture d'index dans GSC chaque semaine
- Publiez régulièrement (minimum 2 articles/mois)
- Construisez activement des backlinks vers le nouveau domaine

## La transparence comme différenciateur

J'aurais pu écrire cet article en cachant que c'est mon propre problème. En le présentant comme "conseils généraux sur la migration SEO".

J'ai choisi de ne pas le faire.

Parce que si vous cherchez un [consultant SEO à Madagascar](/consultant-seo-madagascar/), vous voulez quelqu'un qui a vécu les problèmes réels — pas quelqu'un qui récite des guides théoriques. Les erreurs que j'ai faites sur mon propre site, je ne les ferai pas sur le vôtre.

Et les solutions que j'applique maintenant, je peux les appliquer pour vous dès le départ.

---

*Si vous planifiez une migration de domaine ou si vous venez d'en faire une et que vous observez une chute de trafic, [contactez-moi](/contact) pour un [audit SEO gratuit](/audit-seo-madagascar/) — j'identifierai les blocages spécifiques à votre situation.*

## À lire aussi

- [Audit SEO Madagascar : ce qu'on analyse dans les 30 points](/audit-seo-madagascar/)
- [Netlinking Madagascar : construire son autorité de domaine](/netlinking-madagascar/)
- [Comment choisir son consultant SEO à Madagascar](/2026/06/23/meilleur-consultant-seo-madagascar/)
