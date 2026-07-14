### [2026-07-07T11:08:11Z] | Initialisation du repo split bookivox-docs
- **Contexte :** La documentation devait vivre dans un repo dedie afin de separer sa publication, sa relecture et sa navigation du code produit.
- **Modifications effectuees :**
    - Copie du contenu de `docs/` a la racine de `split-repos/bookivox-docs`.
    - Reecriture du `README.md` pour refleter Mintlify, le perimetre documentaire et les dependances avec l API et le frontend.
- **Decisions Techniques :** Le split conserve la reference API statique incluse dans le repo docs, tout en rappelant que la source de verite reste l OpenAPI publie par l API.
- **Impacts & Dependances :** Nouveau repo interne : `split-repos/bookivox-docs`. Depend de `bookivox-api` pour la spec et de `bookivox-ui` pour les surfaces documentees.
- **Prochaines etapes :** Ajouter ensuite une CI docs dediee, nettoyer les references legacy et sortir ce dossier vers un vrai repo Git autonome.

### [2026-07-07T11:08:11Z] | Reprise a zero du panneau gauche auth en version minimaliste
- **Contexte :** Le panneau gauche des pages d authentification etait juge trop charge. L objectif etait de repartir de zero avec une direction plus calme, plus premium et beaucoup moins dense.
- **Modifications effectuees :**
    - Suppression des listes de benefices et des cartes secondaires dans `ui/src/components/auth/AuthShell.tsx`.
    - Reconstruction du panneau gauche autour de trois elements seulement : logo, promesse principale et ligne d appui.
    - Simplification de la copie de marque dans `ui/src/lib/i18n/dictionaries.ts` pour raccourcir le message et garder uniquement l essentiel.
- **Decisions Techniques :** J ai choisi une composition editoriale minimaliste plutot qu un assemblage de cartes pour diminuer la charge visuelle et renforcer la lisibilite immediate.
- **Impacts & Dependances :** Fichiers touches : `ui/src/components/auth/AuthShell.tsx`, `ui/src/lib/i18n/dictionaries.ts`, `ENGINEERING_LOG.md`. Diagnostics propres.
- **Prochaines etapes :** Si besoin, ajuster ensuite uniquement la typographie ou les espacements fins sans recharger la colonne.

### [2026-07-07T11:04:09Z] | Refonte ciblee du panneau gauche auth
- **Contexte :** La demande etait de corriger les fautes visibles et de revoir uniquement la partie gauche des pages d authentification, sans continuer a modifier le reste des formulaires ou les parcours.
- **Modifications effectuees :**
    - Refonte du panneau gauche dans `ui/src/components/auth/AuthShell.tsx` avec une grande carte hero plus premium, une liste de benefices plus propre et des blocs de preuve plus lisibles.
    - Reecriture des textes de marque dans `ui/src/lib/i18n/dictionaries.ts` pour mettre en avant des conversations plus humaines, les appels entrants et sortants et un pilotage plus clair.
    - Reversion des changements hors panneau gauche pour respecter strictement le perimetre demande.
- **Decisions Techniques :** J ai limite la passe a la seule colonne gauche afin de ne pas destabiliser les parcours login, signup et mot de passe oublie. La nouvelle UI renforce la credibilite percue sans ajouter de complexite visuelle.
- **Impacts & Dependances :** Fichiers touches : `ui/src/components/auth/AuthShell.tsx`, `ui/src/lib/i18n/dictionaries.ts`, `ENGINEERING_LOG.md`. Diagnostics propres sur les fichiers modifies.
- **Prochaines etapes :** Si besoin, harmoniser ensuite la meme direction artistique sur d autres ecrans marketing sans toucher au coeur des formulaires auth.

### [2026-07-07T11:02:01Z] | Repositionnement auth sur les voix plus humaines et la gestion des appels
- **Contexte :** La promesse du panneau gauche devait davantage mettre en avant la qualité perçue des voix et la capacité à gérer les appels entrants et sortants, au lieu de rester trop générique.
- **Modifications effectuees :**
    - Reecriture de la promesse `auth.*` dans `ui/src/lib/i18n/dictionaries.ts` pour mettre en avant des voix plus humaines, la gestion des appels entrants et sortants et un suivi plus lisible.
    - Ajustement des trois preuves de valeur pour mieux refléter le produit : voix, appels et suivi.
- **Decisions Techniques :** J ai conserve la meme structure visuelle et j ai limite le changement a la copie afin de renforcer la perception produit sans destabiliser le design final deja valide.
- **Impacts & Dependances :** Fichiers touches : `ui/src/lib/i18n/dictionaries.ts`, `ENGINEERING_LOG.md`. Diagnostics propres.
- **Prochaines etapes :** Si besoin, decliner ce meme positionnement produit sur d autres surfaces d entree comme la page d accueil ou l onboarding.

### [2026-07-07T10:34:28Z] | Allègement final du panneau gauche auth et suppression du hint superflu
- **Contexte :** Une dernière passe était nécessaire pour rendre la colonne gauche plus premium, plus minimaliste et plus SaaS, tout en retirant le texte d aide superflu sur la page `mot de passe oublie`.
- **Modifications effectuees :**
    - Allègement de `ui/src/components/auth/AuthShell.tsx` avec une hiérarchie plus nette, des blocs plus espacés et des éléments de preuve plus lisibles.
    - Transformation des chips de bénéfices en liste de points plus premium et plus calmes visuellement.
    - Réduction de la densité du bloc de preuves pour garder seulement l essentiel.
    - Suppression du texte d aide initial sur `ui/src/components/auth/ForgotPasswordUnavailable.tsx` pour ne garder que le retour après saisie de l e-mail.
    - Ajustement de la copie FR/EN dans `ui/src/lib/i18n/dictionaries.ts` pour garder une promesse plus directe, plus crédible et moins verbeuse.
- **Decisions Techniques :** J ai privilégié une colonne gauche plus éditoriale et plus respirante au lieu d empiler davantage de cartes ou de labels. La suppression du hint non essentiel sur `mot de passe oublie` permet d éviter la surcharge et de concentrer l attention sur l action utile.
- **Impacts & Dependances :** Fichiers touches : `ui/src/components/auth/AuthShell.tsx`, `ui/src/components/auth/ForgotPasswordUnavailable.tsx`, `ui/src/lib/i18n/dictionaries.ts`, `ENGINEERING_LOG.md`. Diagnostics propres sur les fichiers modifies.
- **Prochaines etapes :** Si besoin, harmoniser ensuite la microcopie des titres login/signup avec cette nouvelle direction encore plus premium.

### [2026-07-07T10:30:48Z] | Formulaire e-mail sur mot de passe oublie et nouvelle passe AIDA SONCAS
- **Contexte :** La page `mot de passe oublie` devait au minimum permettre de renseigner une adresse e-mail, et la partie gauche des pages d authentification devait etre plus propre, plus SaaS et moins verbeuse. L enjeu etait d etre plus persuasif sans tomber dans le texte marketing surcharge.
- **Modifications effectuees :**
    - Ajout d un vrai champ e-mail et d un bouton d action dans `ui/src/components/auth/ForgotPasswordUnavailable.tsx`.
    - Affichage d un retour clair apres saisie de l adresse pour indiquer la suite en mode `local`, sans pretendre qu un e-mail est envoye automatiquement.
    - Extension des cles `auth.forgotPasswordPage.*` dans `ui/src/lib/i18n/dictionaries.ts`.
    - Refonte du contenu du panneau gauche dans `ui/src/components/auth/AuthShell.tsx` avec moins de texte, une promesse plus directe et trois blocs de valeur plus lisibles.
    - Reecriture de la copie de marque dans `ui/src/lib/i18n/dictionaries.ts` avec une logique plus proche de AIDA et SONCAS : attirer l attention, rassurer, simplifier et mettre en avant la valeur.
- **Decisions Techniques :** J ai privilegie une UX honnete en auth locale : l utilisateur peut saisir son e-mail, mais l interface precise ensuite que la suite depend encore d un administrateur ou d un processus interne. Pour la colonne gauche, j ai reduit la densite de texte afin d augmenter la clarte et la perception premium.
- **Impacts & Dependances :** Fichiers touches : `ui/src/components/auth/ForgotPasswordUnavailable.tsx`, `ui/src/components/auth/AuthShell.tsx`, `ui/src/lib/i18n/dictionaries.ts`, `ENGINEERING_LOG.md`. Diagnostics propres sur les fichiers modifies.
- **Prochaines etapes :** Si besoin, brancher plus tard un veritable envoi de reinitialisation cote backend local et poursuivre la meme logique de copywriting sur les ecrans d onboarding.

### [2026-07-07T10:21:55Z] | Deblocage du lien mot de passe oublie en auth locale
- **Contexte :** Le lien `Mot de passe oublie ?` semblait ne rien faire en mode `local` car le middleware redirigeait toute route non publique vers `/auth/login` quand aucun token n est present. La page `/auth/forgot-password` existait, mais etait bloquee.
- **Modifications effectuees :**
    - Ajout de `/auth/forgot-password` aux chemins publics en mode `local` dans `ui/src/middleware.ts`.
- **Decisions Techniques :** Le reset mot de passe est un parcours non authentifie par definition. En mode `local`, il doit rester accessible sans token, exactement comme `login` et `signup`.
- **Impacts & Dependances :** Fichier touche : `ui/src/middleware.ts`, `ENGINEERING_LOG.md`. Diagnostics propres.
- **Prochaines etapes :** Implementer un vrai flux de reinitialisation pour l auth locale si besoin, au lieu de la page informative actuelle.

### [2026-07-07T10:19:07Z] | Correction du lien mot de passe oublie et finition SaaS de l auth
- **Contexte :** Le lien `Mot de passe oublie ?` etait casse car il pointait vers une route inexistante. En parallele, le panneau gauche d authentification devait encore gagner en credibilite et en clarté produit pour paraitre plus SaaS.
- **Modifications effectuees :**
    - Correction du lien `Mot de passe oublie ?` dans `ui/src/app/auth/login/page.tsx` avec routage dynamique selon le provider d authentification.
    - Creation de `ui/src/app/auth/forgot-password/page.tsx` pour offrir un parcours valide en auth locale et rediriger vers `Stack` quand ce provider est actif.
    - Creation de `ui/src/components/auth/ForgotPasswordUnavailable.tsx` pour afficher une page locale claire, compatible i18n, au lieu d une route morte.
    - Extension de `ui/src/lib/i18n/dictionaries.ts` avec les cles `auth.forgotPasswordPage.*` et affinage de la promesse commerciale du panneau gauche en suivant une logique SONCAS plus concrete.
- **Decisions Techniques :** J ai privilegie une correction qui marche dans les deux modes d authentification au lieu d un simple changement de lien. Cette approche supprime l impasse UX, respecte la configuration active du projet et garde une base propre si une vraie reinitialisation locale est ajoutee plus tard.
- **Impacts & Dependances :** Fichiers touches : `ui/src/app/auth/login/page.tsx`, `ui/src/app/auth/forgot-password/page.tsx`, `ui/src/components/auth/ForgotPasswordUnavailable.tsx`, `ui/src/lib/i18n/dictionaries.ts`, `ENGINEERING_LOG.md`. Diagnostics propres sur les fichiers modifies.
- **Prochaines etapes :** Si besoin, brancher ensuite un veritable flux de reinitialisation pour l auth locale afin de remplacer la page informative par une action complete.

### [2026-07-07T10:16:40Z] | Repositionnement marketing du shell auth avec promesse plus credible
- **Contexte :** Le panneau gauche des pages d authentification restait trop froid et trop technique. Il fallait le rendre plus vendeur, plus credible et plus simple, tout en supprimant le bloc enterprise devenu inutile et en adoucissant la profondeur visuelle.
- **Modifications effectuees :**
    - Adoucissement des ombres et de l eclairage dans `ui/src/components/auth/AuthShell.tsx` pour un rendu plus premium et moins agressif.
    - Suppression complete du bloc enterprise du shell auth et nettoyage des usages dans `login`, `signup` et `handler/[...stack]`.
    - Remplacement du badge `Acces securise` par le logo dans la carte formulaire pour une entree en page plus propre.
    - Reecriture de la promesse de marque et des blocs de benefices dans `ui/src/lib/i18n/dictionaries.ts` avec une logique plus proche de SONCAS : securite, confort et retour sur valeur.
    - Suppression du composant devenu inutile `ui/src/components/auth/AuthEnterpriseCTA.tsx`.
- **Decisions Techniques :** J ai conserve la structure generale du split-screen pour ne pas perturber les parcours de connexion, mais j ai simplifie le panneau de marque pour faire monter la credibilite percue sans rajouter de bruit visuel. La nouvelle copie privilegie des benefices concrets et lisibles plutot qu un discours produit trop abstrait.
- **Impacts & Dependances :** Fichiers touches : `ui/src/components/auth/AuthShell.tsx`, `ui/src/app/auth/login/page.tsx`, `ui/src/app/auth/signup/page.tsx`, `ui/src/app/handler/[...stack]/page.tsx`, `ui/src/lib/i18n/dictionaries.ts`, suppression de `ui/src/components/auth/AuthEnterpriseCTA.tsx`, `ENGINEERING_LOG.md`. Diagnostics propres sur les fichiers modifies.
- **Prochaines etapes :** Si besoin, poursuivre la meme logique de copywriting premium sur les pages marketing internes et les autres surfaces visibles de l onboarding.

### [2026-07-07T10:06:11Z] | Nettoyage des tirets longs visibles et i18n des surfaces auth
- **Contexte :** Les pages d authentification contenaient encore plusieurs textes visibles en dur, des formulations non internationalisées et des tirets longs `—` que tu voulais retirer de l interface. Il fallait aussi garder la compatibilite avec les flows auth existants.
- **Modifications effectuees :**
    - Internationalisation complete des surfaces `login`, `signup`, du shell auth partage et du CTA enterprise via `ui/src/lib/i18n/dictionaries.ts`.
    - Ajout de nouvelles cles `auth.*` pour les aides de champs, le panneau de marque, les messages enterprise, le mode local et les textes des boutons.
    - Retrait des tirets longs visibles des textes auth et des libelles auth centralises dans le dictionnaire.
    - Creation de `ui/src/components/auth/LocalAuthMessage.tsx` pour garder le message Stack local compatible avec le provider i18n client sans casser la route serveur `ui/src/app/handler/[...stack]/page.tsx`.
- **Decisions Techniques :** J ai limite la passe aux surfaces auth et aux chaines visibles pour eviter une modification globale trop risquee sur toute la plateforme. Le branchement a ete fait sur le provider i18n deja en place afin de respecter l architecture existante et de ne pas dupliquer la logique de langue.
- **Impacts & Dependances :** Fichiers touches : `ui/src/lib/i18n/dictionaries.ts`, `ui/src/components/auth/AuthShell.tsx`, `ui/src/components/auth/AuthEnterpriseCTA.tsx`, `ui/src/components/auth/LocalAuthMessage.tsx`, `ui/src/app/auth/login/page.tsx`, `ui/src/app/auth/signup/page.tsx`, `ui/src/app/handler/[...stack]/page.tsx`, `ENGINEERING_LOG.md`. Diagnostics propres sur les fichiers modifies, hors deux hints deprecation deja presents sur l API Stack.
- **Prochaines etapes :** Continuer le retrait des tirets longs visibles sur les autres surfaces utilisateur prioritaires en les traitant par lots cohérents pour ne pas embarquer des commentaires techniques ou du code genere inutilement.

### [2026-07-07T10:01:10Z] | Affinage visuel premium du shell d authentification
- **Contexte :** Apres avoir repositionne le formulaire a droite, les pages d authentification restaient fonctionnelles mais encore un peu plates visuellement. L objectif etait d obtenir une presentation plus premium et plus equilibree sans ajouter de bruit ni toucher a la logique des formulaires.
- **Modifications effectuees :**
    - Renforcement du shell partage `ui/src/components/auth/AuthShell.tsx` avec une carte formulaire plus nette, une profondeur visuelle plus propre et un bandeau discret `Acces securise`.
    - Recomposition du panneau de marque avec une promesse produit plus claire, des chips de capacites et trois blocs de confiance courts pour mieux structurer l espace.
    - Refonte du bloc `enterprise` pour lui donner plus de presence tout en gardant un texte concis.
    - Harmonisation du bouton `ui/src/components/auth/AuthEnterpriseCTA.tsx` en francais avec un style plus coherent avec le nouveau panneau.
- **Decisions Techniques :** J ai volontairement limite la passe aux composants partages `AuthShell` et `AuthEnterpriseCTA` afin de faire monter en gamme `login`, `signup` et les formulaires Stack sans modifier les flows, les handlers ni les dependances d authentification. Cette approche reduit fortement le risque de regression fonctionnelle.
- **Impacts & Dependances :** Fichiers touches : `ui/src/components/auth/AuthShell.tsx`, `ui/src/components/auth/AuthEnterpriseCTA.tsx`, `ENGINEERING_LOG.md`. Diagnostics IDE propres sur les deux composants modifies.
- **Prochaines etapes :** Si besoin, faire une troisieme passe sur la microcopie des pages d authentification et l alignement fin du contenu Stack pour obtenir un rendu encore plus homogène entre auth locale et auth cloud.

### [2026-07-07T09:58:36Z] | Repositionnement du formulaire des pages d authentification
- **Contexte :** Les pages d authentification donnaient une hierarchie visuelle peu naturelle avec le formulaire principal place a gauche sur desktop. L objectif etait de remettre le formulaire a droite sans toucher a la logique des pages `login` et `signup`.
- **Modifications effectuees :**
    - Inversion des colonnes desktop dans `ui/src/components/auth/AuthShell.tsx` pour placer le formulaire a droite et le panneau de marque a gauche.
    - Ajustement des proportions du layout, de la bordure separatrice et du halo decoratif pour conserver un rendu equilibre apres l inversion.
- **Decisions Techniques :** J ai limite le changement au shell partage par toutes les pages d authentification afin d eviter toute regression sur les formulaires eux-memes, les imports ou les comportements client. Cette approche centralisee permet de corriger `login` et `signup` en une seule modification faible risque.
- **Impacts & Dependances :** Fichiers touches : `ui/src/components/auth/AuthShell.tsx`, `ENGINEERING_LOG.md`. Diagnostics IDE propres sur le fichier modifie.
- **Prochaines etapes :** Affiner si besoin la composition visuelle du panneau de marque et l alignement vertical du formulaire pour donner un rendu encore plus premium sans surcharger l interface.

### [2026-07-06T13:06:33Z] | Migration runtime Bookivox vers Bookivox avec compatibilite legacy
- **Contexte :** Le backend principal devait commencer le renommage `Bookivox` vers `Bookivox`, y compris au niveau des modules Pipecat, sans casser le projet actuel deja stable. Le risque principal etait un renommage destructif du package `pipecat.services.bookivox`, encore potentiellement importe par du code ou des scripts legacy.
- **Modifications effectuees :**
    - Activation du runtime principal sur `pipecat.services.bookivox` dans `api/services/pipecat/service_factory.py`.
    - Finalisation du nouveau package `pipecat/src/pipecat/services/bookivox/` avec des classes `Bookivox*` et des URL par defaut alignees sur `app.bookivox.com`.
    - Remplacement de l ancienne implementation `pipecat/src/pipecat/services/bookivox/*` par des wrappers de compatibilite qui re-exportent les symboles `Bookivox*` sous les anciens noms `Bookivox*`.
    - Consolidation de la logique de billing/correlation dans `pipecat/src/pipecat/services/bookivox/mps_billing.py` puis re-export depuis le package legacy.
    - Conservation de l alias `DOGRAH_TTFS_P99` dans `pipecat/src/pipecat/services/stt_latency.py` pour eviter une rupture sur d eventuels imports restants.
- **Decisions Techniques :** J ai privilegie une migration par compatibilite transitoire plutot qu un renommage physique destructif du dossier `bookivox`. Cette approche retire la duplication de logique, force le code actif a converger vers `bookivox`, maintient les anciens imports fonctionnels et laisse une porte de sortie propre pour une suppression finale une fois tout le repo et les dependances nettoyes.
- **Impacts & Dependances :** Fichiers touches : `api/services/pipecat/service_factory.py`, `pipecat/src/pipecat/services/bookivox/__init__.py`, `bookivox/llm.py`, `bookivox/stt.py`, `bookivox/tts.py`, `bookivox/flux/stt.py`, `bookivox/mps_billing.py`, `pipecat/src/pipecat/services/bookivox/__init__.py`, `bookivox/llm.py`, `bookivox/stt.py`, `bookivox/tts.py`, `bookivox/mps_billing.py`, `bookivox/flux/__init__.py`, `bookivox/flux/stt.py`, `pipecat/src/pipecat/services/stt_latency.py`, `ENGINEERING_LOG.md`. `compileall` passe, `ruff check` passe et un smoke test d import confirme que `Bookivox*` resolve bien vers `Bookivox*`.
- **Prochaines etapes :** Continuer le renommage hors runtime en priorisant les chemins/fichiers encore nommes `bookivox`, puis supprimer le package legacy uniquement quand plus aucun import interne, test, script ou documentation n en dependra.

### [2026-07-06T11:48:36Z] | Fermeture du reliquat i18n sur le detail tools
- **Contexte :** Le lot `tools` etait presque termine, mais le detail d outil gardait encore un reliquat visible en dur sur la configuration de la calculatrice. Cela cassait la coherence de l internationalisation FR/EN sur une page deja largement migree vers le dictionnaire.
- **Modifications effectuees :**
    - Remplacement dans `ui/src/app/tools/[toolUuid]/page.tsx` du titre et du sous-titre calculatrice hardcodes par `t("tools.detail.calculator.title")` et `t("tools.detail.calculator.subtitle")`.
- **Decisions Techniques :** J ai utilise les cles deja presentes dans `dictionaries.ts` pour fermer proprement le lot sans introduire de nouvelles structures i18n ni dupliquer la copie.
- **Impacts & Dependances :** Fichiers touches : `ui/src/app/tools/[toolUuid]/page.tsx`, `ENGINEERING_LOG.md`. Diagnostics propres et lint cible valide.
- **Prochaines etapes :** Continuer l audit des derniers reliquats visibles sur les pages secondaires de la sidebar, en priorisant les surfaces encore partiellement hors dictionnaire.

### [2026-07-06T11:46:50Z] | Simplification finale de reports et amelioration des graphes
- **Contexte :** Apres la premiere refonte, le retour utilisateur etait clair : trop de texte, un hero trop charge et un etat vide trop bavard sur `reports`. Il fallait epurer la page et ne garder que les elements utiles, tout en ameliorant la qualite visuelle des deux graphes principaux.
- **Modifications effectuees :**
    - Simplification de `ui/src/app/reports/page.tsx` en retirant le hero editorial, les cartes de contexte (date, fuseau, perimetre) et le bloc d etat vide textuel.
    - Eclaircissement de `ui/src/app/reports/components/MetricsCards.tsx` pour garder des cartes plus sobres et plus directes.
    - Remplacement du graphe `Outcome distribution` par un donut plus qualitatif dans `ui/src/app/reports/components/DispositionChart.tsx`, avec une legende laterale compacte.
    - Amelioration de `ui/src/app/reports/components/DurationChart.tsx` avec un histogramme plus net et un recapitulatif discret des buckets.
    - Nettoyage de `ui/src/lib/i18n/dictionaries.ts` pour retirer les cles `reportsPage` devenues inutiles apres cette simplification.
- **Decisions Techniques :** J ai privilegie une reduction nette de la charge visuelle plutot qu une refonte encore plus demonstrative. L objectif etait une page plus calme, plus premium et plus orientee lecture, sans reintroduire de texte ou de chrome inutile.
- **Impacts & Dependances :** Fichiers touches : `ui/src/app/reports/page.tsx`, `ui/src/app/reports/components/MetricsCards.tsx`, `ui/src/app/reports/components/DispositionChart.tsx`, `ui/src/app/reports/components/DurationChart.tsx`, `ui/src/lib/i18n/dictionaries.ts`, `ENGINEERING_LOG.md`. Diagnostics propres et lint cible valide.
- **Prochaines etapes :** Si besoin, harmoniser d autres surfaces analytiques sur cette meme direction minimale : peu de texte, graphes forts et controles compacts.

### [2026-07-06T11:28:28Z] | Refonte visuelle de la page reports
- **Contexte :** La page `reports` restait trop proche du design de départ avec une structure très standard (header + filtres + cartes simples + charts nus). L objectif etait de la rendre plus premium, plus éditoriale et visuellement distincte sans toucher à la logique de reporting.
- **Modifications effectuees :**
    - Refonte de `ui/src/app/reports/page.tsx` avec une vraie carte de pilotage en tete : badge, resume visuel date/fuseau/perimetre, toolbar integree et export mieux mis en scene.
    - Refonte de `ui/src/app/reports/components/MetricsCards.tsx` avec des cartes plus haut de gamme, accent visuel, hierarchie plus nette et indicateur derive du taux de transfert.
    - Refonte de `ui/src/app/reports/components/DispositionChart.tsx` et `ui/src/app/reports/components/DurationChart.tsx` avec headers enrichis, descriptions, chips de lecture rapide, cadres plus propres et etats vides plus soignes.
    - Extension du dictionnaire `ui/src/lib/i18n/dictionaries.ts` pour supporter la nouvelle copie FR/EN de la page reports.
- **Decisions Techniques :** J ai conserve toute la logique de fetch/export intacte et j ai concentre la transformation sur la presentation, afin d obtenir une rupture visuelle nette sans introduire de risque fonctionnel sur les donnees ou les interactions.
- **Impacts & Dependances :** Fichiers touches : `ui/src/app/reports/page.tsx`, `ui/src/app/reports/components/MetricsCards.tsx`, `ui/src/app/reports/components/DispositionChart.tsx`, `ui/src/app/reports/components/DurationChart.tsx`, `ui/src/lib/i18n/dictionaries.ts`, `ENGINEERING_LOG.md`. Diagnostics propres et lint cible valide.
- **Prochaines etapes :** Si besoin, prolonger cette meme direction visuelle sur d autres pages analytiques ou historiques pour renforcer la coherence premium du produit.

### [2026-07-06T11:19:19Z] | Nettoyage des options de creation d outils
- **Contexte :** L utilisateur a demande de retirer de la creation d outils la calculatrice et toutes les options marquees comme bientot disponibles. L objectif etait de nettoyer le flux de creation sans casser l affichage d outils existants deja en base.
- **Modifications effectuees :**
    - Ajout d un flag `availableInCreate` dans `ui/src/app/tools/config.tsx`.
    - Creation de `CREATE_TOOL_CATEGORIES` pour filtrer uniquement les categories autorisees dans la modale de creation.
    - Retrait de `calculator`, `native` et `integration` du select de creation dans `ui/src/app/tools/page.tsx`, tout en conservant leur configuration pour l affichage ou la compatibilite des outils existants.
    - Ajout de la traduction `transfer_call` dans `ui/src/lib/i18n/dictionaries.ts` afin de garder un badge propre sur la liste.
- **Decisions Techniques :** J ai evite de supprimer totalement les categories de la configuration centrale pour ne pas casser le rendu, les icones ou l edition d outils deja existants. Le filtrage est limite au flux de creation, ce qui repond a la demande sans regression produit.
- **Impacts & Dependances :** Fichiers touches : `ui/src/app/tools/config.tsx`, `ui/src/app/tools/page.tsx`, `ui/src/lib/i18n/dictionaries.ts`, `ENGINEERING_LOG.md`. Diagnostics propres et lint cible valide.
- **Prochaines etapes :** Si besoin, on peut ensuite masquer aussi les surfaces de detail associees a ces categories lorsqu elles ne sont plus supportees commercialement.

### [2026-07-06T03:09:45Z] | Corrections orthographe et accents sur recordingsDialog (FR)
- **Contexte :** La modale d enregistrements etait deja internationalisee, mais plusieurs libelles FR restaient sans accents (Modele, Demarrer, Arreter, Acces, etc.) ce qui degradait la qualite linguistique.
- **Modifications effectuees :**
    - Correction des chaines FR dans `ui/src/lib/i18n/dictionaries.ts` sous `recordingsDialog` (accents, apostrophes, ellipses) sans changer les cles.
- **Decisions Techniques :** Corrections uniquement sur les valeurs FR pour eviter tout impact sur les appels `t()` existants et rester compatible avec les fallbacks.
- **Impacts & Dependances :** Fichier touche : `ui/src/lib/i18n/dictionaries.ts`, `ENGINEERING_LOG.md`. Lint cible valide.
- **Prochaines etapes :** Continuer la meme passe linguistique sur les autres blocs i18n FR qui restent en ASCII si besoin, en priorisant les ecrans les plus visibles.

### [2026-07-06T03:02:02Z] | Passe i18n sur la modale RecordingsDialog (workflow editor)
- **Contexte :** Un reliquat de copie et de formats restait visible dans la modale d enregistrements du workflow, notamment une description construite via un split sur `@` (avec un mot francais en dur) et des tailles de fichier affichees avec une unite non localisee.
- **Modifications effectuees :**
    - Extension de `ui/src/lib/i18n/dictionaries.ts` pour `recordingsDialog` avec `descriptionBeforeAt`, `descriptionAfterAt`, `defaultRecordingName` et `units.megabytes` en FR/EN.
    - Mise a jour de `ui/src/app/workflow/[workflowId]/components/RecordingsDialog.tsx` pour supprimer le split sur `@`, localiser le libelle autour du `@` et afficher les tailles de fichier avec un format numerique depend de la locale (`fr-FR` / `en-US`).
- **Decisions Techniques :** Le systeme `t()` ne resolvant que des feuilles de type string, j ai evite les tableaux de segments et j ai prefere deux cles explicites (avant/apres) pour garder un rendu JSX propre autour du symbole `@` sans fragilite.
- **Impacts & Dependances :** Fichiers touches : `ui/src/lib/i18n/dictionaries.ts`, `ui/src/app/workflow/[workflowId]/components/RecordingsDialog.tsx`, `ENGINEERING_LOG.md`. Diagnostics IDE propres et lint cible valide.
- **Prochaines etapes :** Continuer l audit des derniers dialogues workflow qui manipulent encore des formats (dates, tailles, units) pour assurer une coherence totale entre FR et EN.

### [2026-07-06T02:15:45Z] | Passe i18n sur les dialogues de reglages workflow residuels
- **Contexte :** La passe precedente sur `workflow/run` avait reduit le reliquat visible, mais plusieurs dialogues du parcours d edition d agent restaient encore avec de la copie brute, notamment autour du dictionnaire, des variables de contexte et de la detection de messagerie vocale. Ces composants etaient deja proches fonctionnellement du namespace `workflowSettings`, mais n etaient pas encore relies proprement au dictionnaire.
- **Modifications effectuees :**
    - Extension de `ui/src/lib/i18n/dictionaries.ts` avec les cles manquantes dans `workflowSettings.common`, `workflowSettings.variables`, `workflowSettings.voicemail` et `workflowRun.contextDisplay`.
    - Internationalisation de `ui/src/app/workflow/[workflowId]/components/TemplateContextVariablesDialog.tsx` en reutilisant les cles `workflowSettings.variables` et l aria-label de suppression deja defini dans `workflowRun.contextVariables`.
    - Internationalisation de `ui/src/app/workflow/[workflowId]/components/DictionaryDialog.tsx` en s appuyant sur `workflowSettings.dictionary`.
    - Internationalisation de `ui/src/app/workflow/[workflowId]/components/VoicemailDetectionDialog.tsx` en s appuyant sur `workflowSettings.voicemail`.
    - Internationalisation de `ui/src/app/workflow/[workflowId]/run/[runId]/components/ContextDisplay.tsx` pour l etat vide.
- **Decisions Techniques :** J ai volontairement reutilise le namespace `workflowSettings` deja existant plutot que de creer une nouvelle famille de cles pour des reglages qui expriment deja les memes concepts dans l interface. Cela maintient une terminologie stable entre l editeur, les dialogues et les reglages lateraux.
- **Impacts & Dependances :** Fichiers touches : `ui/src/lib/i18n/dictionaries.ts`, `ui/src/app/workflow/[workflowId]/components/TemplateContextVariablesDialog.tsx`, `DictionaryDialog.tsx`, `VoicemailDetectionDialog.tsx`, `ui/src/app/workflow/[workflowId]/run/[runId]/components/ContextDisplay.tsx`, `ENGINEERING_LOG.md`. Diagnostics IDE propres et lint cible valide sans erreur.
- **Prochaines etapes :** Continuer l audit fin des derniers composants workflow encore visibles pour verifier qu il ne reste plus de copy brute dans les dialogues secondaires et les etats vides.

### [2026-07-06T02:09:29Z] | Passe i18n sur les composants workflow run residuels
- **Contexte :** Apres les passes principales sur la sidebar et le lot `campaigns`, l'audit ciblé montrait encore quelques composants visibles du parcours `workflow/run` avec de la copie en dur. Le reliquat se concentrait sur des dialogues d'erreur et des petits panneaux utilitaires, ce qui cassait la cohérence FR/EN malgré un reste du parcours deja traduit.
- **Modifications effectuees :**
    - Extension de `ui/src/lib/i18n/dictionaries.ts` avec de nouvelles cles `workflowRun.connectionStatus`, `workflowRun.configErrorDialog`, `workflowRun.apiKeyErrorDialog` et `workflowRun.contextVariables`.
    - Internationalisation de `ui/src/app/workflow/[workflowId]/run/[runId]/components/WorkflowConfigErrorDialog.tsx`.
    - Internationalisation de `ui/src/app/workflow/[workflowId]/run/[runId]/components/ApiKeyErrorDialog.tsx`, y compris les messages d'aide et les CTA contextuels.
    - Internationalisation de `ui/src/app/workflow/[workflowId]/run/[runId]/components/ConnectionStatus.tsx`.
    - Internationalisation de `ui/src/app/workflow/[workflowId]/run/[runId]/components/ContextVariablesSection.tsx`, y compris le message de cle dupliquee et les labels d'accessibilite.
- **Decisions Techniques :** J'ai traite ce reliquat en lot `workflow/run` plutot que de relancer un scan global trop large. Cela permet de garder un namespace `workflowRun` coherent et de ne pas disperser de nouvelles cles dans des sections i18n sans rapport.
- **Impacts & Dependances :** Fichiers touches : `ui/src/lib/i18n/dictionaries.ts`, `ui/src/app/workflow/[workflowId]/run/[runId]/components/WorkflowConfigErrorDialog.tsx`, `ApiKeyErrorDialog.tsx`, `ConnectionStatus.tsx`, `ContextVariablesSection.tsx`, `ENGINEERING_LOG.md`. Diagnostics IDE propres et lint cible valide sans erreur.
- **Prochaines etapes :** Continuer l'audit des composants secondaires encore rattaches a la navigation principale, surtout autour de `workflow/run` et des derniers dialogues visibles qui peuvent encore contenir des textes en dur.

### [2026-07-06T01:55:08Z] | Passe i18n sur le flux campaigns creation edition et composants
- **Contexte :** Apres la passe sur les pages principales de la sidebar, le reliquat visible du module `campaigns` se concentrait surtout sur les ecrans de creation et d edition ainsi que sur leurs composants associes. Ces surfaces restaient en francais dur, avec des toasts, validations et aides non relies au dictionnaire FR/EN.
- **Modifications effectuees :**
    - Extension de `ui/src/lib/i18n/dictionaries.ts` avec un namespace `campaignsForm` en francais et en anglais pour les formulaires, validations, toasts, source CSV, saisie manuelle et reglages avances.
    - Internationalisation de `ui/src/app/campaigns/new/page.tsx` pour les sections du formulaire, les etats de chargement, les erreurs de validation, la creation de source manuelle, le recapitulatif et les actions.
    - Internationalisation de `ui/src/app/campaigns/[campaignId]/edit/page.tsx` pour le chargement, l edition, les validations, les erreurs et les actions.
    - Internationalisation de `ui/src/app/campaigns/CsvUploadSelector.tsx`, `ManualPhoneNumbersTable.tsx` et `CampaignAdvancedSettings.tsx` afin de mutualiser la copie visible entre creation et edition.
- **Decisions Techniques :** J'ai cree un namespace dedie `campaignsForm` au lieu de recharger `campaignsPage`, afin de separer la liste de campagnes des flux transactionnels de creation et d edition. Les composants partages ont ete relies directement au dictionnaire pour eviter des props de texte redondantes et limiter la dette i18n sur les futures evolutions.
- **Impacts & Dependances :** Fichiers touches : `ui/src/lib/i18n/dictionaries.ts`, `ui/src/app/campaigns/new/page.tsx`, `ui/src/app/campaigns/[campaignId]/edit/page.tsx`, `ui/src/app/campaigns/CsvUploadSelector.tsx`, `ui/src/app/campaigns/ManualPhoneNumbersTable.tsx`, `ui/src/app/campaigns/CampaignAdvancedSettings.tsx`, `ENGINEERING_LOG.md`. Diagnostics IDE propres sur les fichiers modifies et lint cible valide sans erreur.
- **Prochaines etapes :** Continuer le balayage des autres sous-pages secondaires rattachees a la sidebar si des composants de campagne ou de workflow gardent encore des textes visibles en dur, puis faire une derniere passe de coherence linguistique globale.

### [2026-07-06T01:49:37Z] | Passe i18n sur le reliquat sidebar tools billing et campagnes
- **Contexte :** L'utilisateur a demande de naviguer proprement sur les pages reelles de la sidebar, avec une attention explicite sur `/tools`, puis sur les reliquats visibles de `billing` et `campaigns`. Le lot precedent avait deja couvert `reports`, `files` et `recordings`, mais `/tools/[toolUuid]`, `billing` et `campaigns` gardaient encore des textes en dur et des formulations non homogènes.
- **Modifications effectuees :**
    - Extension de `ui/src/lib/i18n/dictionaries.ts` avec les nouvelles sections `tools.detail` completees, `campaignsPage` et `billingPage` en francais et en anglais.
    - Finalisation de `ui/src/app/tools/[toolUuid]/page.tsx` pour les etats introuvables, le retour, le lien documentation, le dialogue de code, la configuration MCP et les messages d'enregistrement.
    - Internationalisation de `ui/src/app/billing/page.tsx` pour le header, les cartes de synthese, les messages de paiement, l'historique de credits, les options de facturation et la grille de tarification, avec prise en compte de la locale pour les dates et montants affiches.
    - Internationalisation de `ui/src/app/campaigns/page.tsx` pour le header, le tableau, les statuts, l'etat vide et l'erreur de chargement.
    - Autofix ESLint cible sur `ui/src/app/tools/[toolUuid]/components/EndCallToolConfig.tsx` et `TransferCallToolConfig.tsx` afin de corriger les derniers warnings d'ordre d'import.
- **Decisions Techniques :** J'ai garde la methode route par route definie plus tot : terminer d'abord le lot `/tools` deja entame, puis brancher `billing` et `campaigns` sur des namespaces dedies plutot que d'eparpiller des textes localises dans les composants. `billing` a aussi ete aligne sur la locale active pour les dates, montants et libelles calcules, afin d'eviter une UI hybride malgre un dictionnaire complet.
- **Impacts & Dependances :** Fichiers touches : `ui/src/lib/i18n/dictionaries.ts`, `ui/src/app/tools/[toolUuid]/page.tsx`, `ui/src/app/billing/page.tsx`, `ui/src/app/campaigns/page.tsx`, `ui/src/app/tools/[toolUuid]/components/EndCallToolConfig.tsx`, `ui/src/app/tools/[toolUuid]/components/TransferCallToolConfig.tsx`, `ENGINEERING_LOG.md`. Diagnostics IDE propres sur les fichiers modifies et lint cible valide via `npm run lint -- --file ...` sans warning ni erreur.
- **Prochaines etapes :** Continuer la navigation sur les autres ecrans de la sidebar si d'autres sous-pages `campaigns/*` ou formulaires associes remontent encore des textes en dur, puis faire une derniere passe de finition sur les flux secondaires.

### [2026-07-06T01:20:33Z] | Passe i18n sur les pages sidebar rapports fichiers et enregistrements
- **Contexte :** L'utilisateur a demande de naviguer proprement entre toutes les pages de la sidebar et de finaliser l'internationalisation sur ce perimetre reel. Un audit cible de la navigation a montre que `reports`, `files` et `recordings` restaient les zones les plus mixtes, avec encore des textes en dur, des dates figees et quelques patterns bruts comme des `alert()`.
- **Modifications effectuees :**
    - Extension de `ui/src/lib/i18n/dictionaries.ts` avec de nouvelles sections `reportsPage`, `files.list`, `files.upload`, `recordings.list` et `recordings.upload` en francais et en anglais.
    - Internationalisation de `ui/src/app/reports/page.tsx` et des composants `MetricsCards.tsx`, `DurationChart.tsx` et `DispositionChart.tsx`.
    - Remplacement des messages de telechargement CSV et des etats vides de `reports` par des textes branches sur l'i18n, avec rendu de date base sur la locale active.
    - Internationalisation de `ui/src/app/files/DocumentList.tsx` et `DocumentUpload.tsx` pour les recherches, statuts, toasts, validations, modes de recuperation, tailles de fichiers et CTA.
    - Internationalisation de `ui/src/app/recordings/RecordingsList.tsx` et `RecordingsUploadDialog.tsx` pour les erreurs, validations, toasts, placeholders, resume et controles audio.
- **Decisions Techniques :** J'ai traite uniquement le perimetre reel de la sidebar au lieu de repartir sur un scan global du frontend. `reports` a aussi ete nettoye sur le plan UX avec le remplacement des `alert()` par des toasts et une presentation de date adaptee a la langue active, ce qui reduit les incoherences visibles sans changer la logique de donnees.
- **Impacts & Dependances :** Fichiers touches : `ui/src/lib/i18n/dictionaries.ts`, `ui/src/app/reports/page.tsx`, `ui/src/app/reports/components/MetricsCards.tsx`, `DurationChart.tsx`, `DispositionChart.tsx`, `ui/src/app/files/DocumentList.tsx`, `DocumentUpload.tsx`, `ui/src/app/recordings/RecordingsList.tsx`, `RecordingsUploadDialog.tsx`, `ENGINEERING_LOG.md`. Diagnostics propres et lint cible valide sans warning ni erreur.
- **Prochaines etapes :** Continuer la meme methode route par route sur le reliquat de la sidebar si necessaire, puis verifier les composants transverses encore exposes depuis ces pages secondaires.

### [2026-07-06T01:13:40Z] | Lot i18n sur la famille tools/http
- **Contexte :** Apres le lot `workflow-tester`, le scan global montrait encore un sous-systeme technique mais coherent avec plusieurs textes visibles en dur : la famille `components/http` utilisee par la configuration des outils HTTP, plus les validations visibles du detail d'outil. Pour eviter une i18n partielle, tout le flux a ete traite dans un seul lot.
- **Modifications effectuees :**
    - Extension de `ui/src/lib/i18n/dictionaries.ts` avec une section `tools.http` couvrant la creation d'identifiants, le selecteur d'identifiants, les editeurs de parametres, l'input URL, la configuration HTTP et les erreurs de validation visibles dans `tools/[toolUuid]`.
    - Internationalisation de `ui/src/components/http/create-credential-dialog.tsx` pour les labels, placeholders, types d'identifiants, erreurs et actions.
    - Internationalisation de `ui/src/components/http/credential-selector.tsx`, `key-value-editor.tsx`, `parameter-editor.tsx` et `url-input.tsx`.
    - Internationalisation de `ui/src/app/tools/[toolUuid]/components/HttpApiToolConfig.tsx` pour les onglets, champs, aides, placeholders et sections de configuration.
    - Branchement minimal de `ui/src/app/tools/[toolUuid]/page.tsx` sur l'i18n pour les erreurs de validation et de sauvegarde du flux HTTP / MCP afin d'eviter un parcours hybride.
- **Decisions Techniques :** `validateUrl()` a ete rendu compatible avec des messages localises sans casser son API existante, ce qui permet a `UrlInput` d'afficher des erreurs traduites tout en conservant un comportement compatible avec les usages deja presents. La page detaillee d'outil n'a pas ete refondue en entier dans ce lot, uniquement les erreurs directement liees au sous-systeme HTTP.
- **Impacts & Dependances :** Fichiers touches : `ui/src/lib/i18n/dictionaries.ts`, `ui/src/components/http/create-credential-dialog.tsx`, `credential-selector.tsx`, `key-value-editor.tsx`, `parameter-editor.tsx`, `url-input.tsx`, `ui/src/app/tools/[toolUuid]/components/HttpApiToolConfig.tsx`, `ui/src/app/tools/[toolUuid]/page.tsx`, `ENGINEERING_LOG.md`. Diagnostics propres et lint cible valide sans warning ni erreur.
- **Prochaines etapes :** Reprendre la methode par lots et choisir le prochain sous-systeme encore rentable, probablement les surfaces auth / lead forms ou les composants tools restants hors HTTP.

### [2026-07-06T01:07:12Z] | Lot i18n dedie au workflow tester
- **Contexte :** Apres les lots sur les dialogues workflow, les medias et le widget embarque, le scan global remontait encore plusieurs textes visibles en dur dans le sous-systeme `workflow-tester`. Comme ces composants partagent une meme experience de test manuel et vocal, il etait plus propre de les traiter ensemble.
- **Modifications effectuees :**
    - Extension de `ui/src/lib/i18n/dictionaries.ts` avec de nouvelles cles `workflowEditor.embeddedTester`, `workflowEditor.chatComposer`, `workflowEditor.shared`, `workflowEditor.aiSimulator` et `workflowEditor.turnActions`.
    - Internationalisation de `ui/src/app/workflow/[workflowId]/components/workflow-tester/EmbeddedVoiceTester.tsx` pour le titre, la description et les etats du bouton principal.
    - Internationalisation de `ui/src/app/workflow/[workflowId]/components/workflow-tester/ChatComposer.tsx` pour le bandeau d'edition, les placeholders et les CTA.
    - Internationalisation de `ui/src/app/workflow/[workflowId]/components/workflow-tester/shared.tsx` pour l'etat de pause et l'etat vide du chat manuel.
    - Internationalisation de `ui/src/app/workflow/[workflowId]/components/workflow-tester/AiSimulatorPlaceholder.tsx` pour le prompt par defaut, la description, le placeholder et le CTA de disponibilite.
    - Internationalisation de `ui/src/app/workflow/[workflowId]/components/workflow-tester/TurnMessageActions.tsx` pour les labels et tooltips d'actions de replay.
- **Decisions Techniques :** J'ai volontairement rattache toute cette copie au namespace `workflowEditor` pour rester coherent avec les autres surfaces deja internationalisees du parcours agent. Le prompt par defaut du simulateur AI est gere via la traduction active, ce qui garde aussi cette zone technique alignée sur la langue choisie.
- **Impacts & Dependances :** Fichiers touches : `ui/src/lib/i18n/dictionaries.ts`, `ui/src/app/workflow/[workflowId]/components/workflow-tester/EmbeddedVoiceTester.tsx`, `ChatComposer.tsx`, `shared.tsx`, `AiSimulatorPlaceholder.tsx`, `TurnMessageActions.tsx`, `ENGINEERING_LOG.md`. Diagnostics propres et lint cible valide sans warning ni erreur.
- **Prochaines etapes :** Reprendre le scan global et choisir le prochain lot partage le plus rentable, probablement certains composants tools / HTTP ou les surfaces auth et formulaires marketing encore en dur.

### [2026-07-06T01:01:47Z] | Lot i18n dedie au widget embarque
- **Contexte :** `EmbedDialog` avait ete volontairement isole du precedent lot workflow/media car cette surface contient beaucoup plus de copy produit, de modes d'integration et d'exemples techniques que les autres dialogues operationnels. Il fallait une passe dediee pour eviter un traitement partiel.
- **Modifications effectuees :**
    - Extension de `ui/src/lib/i18n/dictionaries.ts` avec une section `embedDialog` complete en francais et en anglais.
    - Internationalisation de `ui/src/app/workflow/[workflowId]/components/EmbedDialog.tsx` pour le titre, la description, l'activation, les domaines autorises, les modes d'integration, les options de configuration, les apercus, les instructions et les actions de copie / sauvegarde.
    - Localisation des textes par defaut du widget (`buttonText`, `callToActionText`) selon la langue active.
    - Ajout d'un affichage d'erreur visible pour les echecs de chargement, d'enregistrement et de copie, au lieu de laisser ces retours uniquement dans la console.
    - Remplacement du `onKeyPress` deprecated par `onKeyDown` sur l'ajout de domaines.
- **Decisions Techniques :** J'ai garde les exemples de code dans le composant, mais je les ai rendus dependants de la locale active plutot que de les stocker bruts dans le dictionnaire. Cela conserve un dictionnaire lisible tout en permettant une vraie experience FR/EN sur une surface tres technique.
- **Impacts & Dependances :** Fichiers touches : `ui/src/lib/i18n/dictionaries.ts`, `ui/src/app/workflow/[workflowId]/components/EmbedDialog.tsx`, `ENGINEERING_LOG.md`. Lint cible valide sans warning ni erreur.
- **Prochaines etapes :** Reprendre le scan global pour identifier le prochain lot rentable, probablement les derniers dialogues ou composants partages encore en dur dans les parcours tools, workflow ou media.

### [2026-07-06T00:52:33Z] | Lot i18n sur les dialogues operationnels workflow et media
- **Contexte :** Apres la completion de la famille `filters`, le scan montrait un lot coherent de dialogues operationnels encore semi-traduits ou partiellement en dur autour du parcours workflow : apercu media, appel test, controles audio, enregistrements et configurations rapides. Le dialogue d'embarque web etait volontairement isole pour une passe dediee, car il contient beaucoup de copy et d'exemples d'integration.
- **Modifications effectuees :**
    - Extension de `ui/src/lib/i18n/dictionaries.ts` avec les sections `mediaPreviewDialog`, `audioControls`, `phoneCallDialog`, `configurationsDialog` et `recordingsDialog`.
    - Internationalisation de `ui/src/components/MediaPreviewDialog.tsx` pour le header, les etats de chargement, les sections audio / transcription, l'etat vide et les actions de telechargement.
    - Internationalisation de `ui/src/app/workflow/[workflowId]/run/[runId]/components/AudioControls.tsx` pour les parcours de permission micro, les CTA et les labels d'appel.
    - Internationalisation de `ui/src/app/workflow/[workflowId]/components/PhoneCallDialog.tsx` pour les erreurs, etats de chargement, choix de configuration telephonique, numeros sortants, destination SIP / telephone et actions finales.
    - Internationalisation de `ui/src/app/workflow/[workflowId]/components/ConfigurationsDialog.tsx` pour les sections de nommage, bruit d'ambiance, tours de parole, compaction de contexte et gestion des appels.
    - Internationalisation de `ui/src/app/workflow/[workflowId]/components/RecordingsDialog.tsx` pour les erreurs, l'etat de voix courante, l'import / enregistrement, les fichiers en attente, la transcription et la liste existante.
- **Decisions Techniques :** J'ai garde la methode par sous-lots coherents et j'ai explicitement exclu `EmbedDialog` de cette passe pour ne pas melanger des dialogues operationnels courts avec une surface d'integration plus lourde en copy et en exemples techniques. Cela garde une validation plus fiable et une dette plus visible pour le prochain lot.
- **Impacts & Dependances :** Fichiers touches : `ui/src/lib/i18n/dictionaries.ts`, `ui/src/components/MediaPreviewDialog.tsx`, `ui/src/app/workflow/[workflowId]/run/[runId]/components/AudioControls.tsx`, `ui/src/app/workflow/[workflowId]/components/PhoneCallDialog.tsx`, `ui/src/app/workflow/[workflowId]/components/ConfigurationsDialog.tsx`, `ui/src/app/workflow/[workflowId]/components/RecordingsDialog.tsx`, `ENGINEERING_LOG.md`. Lint cible valide sans warning ni erreur.
- **Prochaines etapes :** Ouvrir un lot dedie a `ui/src/app/workflow/[workflowId]/components/EmbedDialog.tsx`, puis reprendre les autres dialogues et composants medias residuels qui remontent encore dans le scan global.

### [2026-07-05T23:47:52Z] | Methode de finition i18n et completion du lot filtres
- **Contexte :** La fin du chantier i18n devait etre reprise proprement avec une methode stable, car il restait trop de fichiers pour continuer par retouches opportunistes. Les composants de filtres restants etaient un bon lot a traiter car ils sont partages et tres visibles sur plusieurs ecrans.
- **Modifications effectuees :**
    - Formalisation d'une methode de finition par lots : cartographie des textes restants, priorisation des composants partages, validation complete apres chaque lot, puis passage au lot suivant.
    - Extension de `ui/src/lib/i18n/dictionaries.ts` avec des cles dediees a `dateRangeFilter`, `numberFilter`, `numberRangeFilter`, `radioFilter` et `textFilter`.
    - Internationalisation de `ui/src/components/filters/DateRangeFilter.tsx`, `NumberFilter.tsx`, `NumberRangeFilter.tsx`, `RadioFilter.tsx` et `TextFilter.tsx`.
    - Ajustement du format d'affichage des dates dans `DateRangeFilter.tsx` pour suivre la locale active au lieu du format implicite du navigateur.
- **Decisions Techniques :** J'ai choisi de terminer toute la famille `filters` d'un seul tenant apres `FilterBuilder`, `MultiSelectFilter` et `TagInputFilter` afin d'eviter une i18n partielle dans un meme sous-systeme. Les deux hints TypeScript sur `initialFocus` ont ete laisses en l'etat car ils relevent d'une migration API distincte et non d'un probleme de qualite introduit par cette passe.
- **Impacts & Dependances :** Fichiers touches : `ui/src/lib/i18n/dictionaries.ts`, `ui/src/components/filters/DateRangeFilter.tsx`, `ui/src/components/filters/NumberFilter.tsx`, `ui/src/components/filters/NumberRangeFilter.tsx`, `ui/src/components/filters/RadioFilter.tsx`, `ui/src/components/filters/TextFilter.tsx`, `ENGINEERING_LOG.md`. Lint cible valide sans warning ni erreur.
- **Prochaines etapes :** Appliquer la meme methode au prochain lot partage le plus rentable, probablement les dialogues workflow et certains composants media / audio qui ressortent encore dans le scan global.

### [2026-07-05T23:44:51Z] | Passe i18n sur les selecteurs de voix et les filtres partages
- **Contexte :** Le scan global remontait encore plusieurs composants partages avec des placeholders, labels et messages en dur, notamment `VoiceSelector`, `VoiceSelectorModal` et les composants de filtres, ce qui reintroduisait du texte hybride dans plusieurs ecrans pourtant deja passes en i18n.
- **Modifications effectuees :**
    - Extension de `ui/src/lib/i18n/dictionaries.ts` avec des sections dediees a `voiceSelector`, `voiceSelectorModal`, `filterBuilder`, `multiSelectFilter` et `tagInputFilter`.
    - Internationalisation de `ui/src/components/VoiceSelector.tsx` pour les placeholders, etats de chargement, filtres, mode manuel et compteurs.
    - Internationalisation de `ui/src/components/VoiceSelectorModal.tsx` pour les filtres, messages d'erreur d'authentification et de preview, mode manuel, footer et actions de selection.
    - Internationalisation de `ui/src/components/filters/FilterBuilder.tsx`, `MultiSelectFilter.tsx` et `TagInputFilter.tsx` pour les titres, templates, resumes, boutons, placeholders et compteurs.
- **Decisions Techniques :** J'ai traite les composants partages en priorite car ils diffusent leur copie sur plusieurs pages a la fois. Cette approche reduit plus vite les derniers melanges FR/EN que des retouches page par page.
- **Impacts & Dependances :** Fichiers touches : `ui/src/lib/i18n/dictionaries.ts`, `ui/src/components/VoiceSelector.tsx`, `ui/src/components/VoiceSelectorModal.tsx`, `ui/src/components/filters/FilterBuilder.tsx`, `ui/src/components/filters/MultiSelectFilter.tsx`, `ui/src/components/filters/TagInputFilter.tsx`, `ENGINEERING_LOG.md`. Diagnostics IDE propres et lint cible valide sans warning ni erreur.
- **Prochaines etapes :** Continuer sur les autres composants partages encore signales par le scan, notamment certains dialogues workflow, selecteurs audio restants et formulaires techniques autour des outils et de l'embarque.

### [2026-07-05T23:41:28Z] | Audit i18n global sur usage, acces API et detail campagne
- **Contexte :** Un scan large du frontend montrait encore plusieurs surfaces visibles avec un melange de textes en dur, parfois seulement en francais, parfois encore en anglais, notamment sur `usage`, `api-keys` et le detail d'une campagne.
- **Modifications effectuees :**
    - Extension de `ui/src/lib/i18n/dictionaries.ts` avec trois nouvelles sections dediees a `usagePage`, `apiKeysPage` et `campaignDetail`, en francais et en anglais.
    - Internationalisation de `ui/src/app/usage/page.tsx` pour les cartes de synthese, les filtres, le tableau, la pagination, le telechargement de rapport et la gestion du fuseau horaire.
    - Internationalisation de `ui/src/app/api-keys/page.tsx` pour les erreurs, etats, actions, dialogues de creation et de restitution des cles, en corrigeant aussi les formulations et la coherence FR/EN.
    - Internationalisation de `ui/src/app/campaigns/[campaignId]/page.tsx` pour les toasts, le header, les CTA, les cartes de synthese, les reglages, le journal d'activite, le snapshot d'execution et la modale de relance.
- **Decisions Techniques :** J'ai traite en priorite les plus grosses pages operationnelles remontees par l'audit plutot que de disperser de petites retouches sur des composants tres secondaires. Cela permet d'eliminer les gros melanges FR/EN visibles tout en gardant un dictionnaire central coherent pour la suite.
- **Impacts & Dependances :** Fichiers touches : `ui/src/lib/i18n/dictionaries.ts`, `ui/src/app/usage/page.tsx`, `ui/src/app/api-keys/page.tsx`, `ui/src/app/campaigns/[campaignId]/page.tsx`, `ENGINEERING_LOG.md`. Diagnostics IDE propres et lint cible valide sans warning ni erreur sur ce lot.
- **Prochaines etapes :** Continuer la meme methode sur les composants partages encore detectes par le scan, notamment certains dialogues workflow, selecteurs vocaux, filtres et formulaires techniques qui gardent encore des placeholders ou messages en dur.

### [2026-07-05T23:31:25Z] | Passe i18n et correction de copie sur la telephonie
- **Contexte :** La surface `telephony-configurations` restait partiellement en dur avec un melange FR/EN dans la liste, le detail, les dialogues de configuration et la gestion des numeros, ainsi que plusieurs formulations et accents a corriger.
- **Modifications effectuees :**
    - Extension de `ui/src/lib/i18n/dictionaries.ts` avec des cles dediees a la liste telephonie, au detail de configuration, au dialogue de configuration et au dialogue de numero.
    - Internationalisation de `ui/src/app/telephony-configurations/page.tsx` pour les toasts, badges, actions, compteurs, labels de copie et la confirmation de suppression.
    - Internationalisation de `ui/src/app/telephony-configurations/[configId]/page.tsx` pour les statuts, colonnes du tableau, CTA, descriptions, confirmations de suppression et messages de succes/erreur.
    - Internationalisation de `ui/src/components/telephony/ConfigFormDialog.tsx` et `ui/src/components/telephony/PhoneNumberDialog.tsx`, avec correction des textes de formulaire, placeholders, confirmations d'achat et messages de validation.
    - Nettoyage de plusieurs fautes et formulations visibles pour obtenir un francais et un anglais plus propres sur l'ensemble du parcours telephonie.
- **Decisions Techniques :** J'ai centralise tous les nouveaux textes dans le dictionnaire plutot que de patcher localement les composants, afin que la telephonie reste coherente avec le reste de la base i18n et que les futurs ajustements de wording ne soient pas disperses.
- **Impacts & Dependances :** Fichiers touches : `ui/src/lib/i18n/dictionaries.ts`, `ui/src/app/telephony-configurations/page.tsx`, `ui/src/app/telephony-configurations/[configId]/page.tsx`, `ui/src/components/telephony/ConfigFormDialog.tsx`, `ui/src/components/telephony/PhoneNumberDialog.tsx`, `ENGINEERING_LOG.md`. Diagnostics IDE propres et lint cible valide sans warning ni erreur.
- **Prochaines etapes :** Refaire une passe similaire sur les dernieres surfaces operationnelles encore techniques si d'autres composants visibles gardent des textes hybrides ou des formulations moins produit.

### [2026-07-05T23:15:42Z] | Finalisation i18n des configurations de modeles workflow
- **Contexte :** La page `workflow/[workflowId]/settings` et ses sous-composants de configuration avancaient cote shell et sections principales, mais les reglages de modeles gardaient encore des libelles visibles en dur, un melange FR/EN et des fallbacks d'erreur anglais.
- **Modifications effectuees :**
    - Extension de `ui/src/lib/i18n/dictionaries.ts` avec des cles dediees a `LLMConfigSelector`, `ServiceConfigurationForm`, `AIModelConfigurationV2Editor` et aux messages de chargement des configurations d'organisation.
    - Internationalisation de `ui/src/components/LLMConfigSelector.tsx` pour les labels, placeholders et l'option de saisie manuelle du modele.
    - Internationalisation de `ui/src/components/ServiceConfigurationForm.tsx` pour les onglets de services, les aides fournisseur, les placeholders dynamiques, les surcharges, les cles API, le mode temps reel et les erreurs generiques.
    - Internationalisation de `ui/src/components/AIModelConfigurationV2Editor.tsx` pour les onglets `Bookivox` et `BYOK`, les champs du moteur vocal et les etats d'enregistrement.
    - Nettoyage de `ui/src/app/workflow/[workflowId]/settings/page.tsx` pour traduire les derniers `En savoir plus` visibles et fournir des fallbacks d'erreur FR/EN sur le chargement des configurations de modeles.
- **Decisions Techniques :** J'ai etendu l'i18n dans les sous-composants plutot que de laisser la page `settings` porter seule les textes, afin d'eviter les regressions quand ces formulaires sont reutilises ailleurs. Les fallbacks d'erreur passent maintenant par le dictionnaire pour conserver une experience bilingue coherente meme lorsque l'API ne renvoie pas de detail exploitable.
- **Impacts & Dependances :** Fichiers touches : `ui/src/lib/i18n/dictionaries.ts`, `ui/src/components/LLMConfigSelector.tsx`, `ui/src/components/ServiceConfigurationForm.tsx`, `ui/src/components/AIModelConfigurationV2Editor.tsx`, `ui/src/app/workflow/[workflowId]/settings/page.tsx`, `ENGINEERING_LOG.md`. Diagnostics IDE propres et `npm run lint -- --file ...` valide sans warning ni erreur sur les fichiers retouches.
- **Prochaines etapes :** Faire une derniere passe visuelle dans l'application pour reperer d'eventuels textes residuels hors des reglages agent, notamment dans d'autres composants techniques reutilises autour des modeles et du workflow.

### [2026-07-05T23:05:50Z] | Passe i18n sur les reglages d agent et le detail d execution
- **Contexte :** Le parcours workflow restait encore partiellement en dur dans `workflow/[workflowId]/settings`, `workflow/[workflowId]/run/[runId]` et les erreurs de chargement des executions, ce qui cassait la coherence FR/EN demandee.
- **Modifications effectuees :**
    - Extension du dictionnaire i18n avec des cles dediees au shell des reglages d'agent, a la section rapport, aux cartes `Enregistrements` et `Ajouter au site web`, au detail d'execution et aux erreurs de chargement des executions.
    - Internationalisation du shell de `ui/src/app/workflow/[workflowId]/settings/page.tsx` : header sticky, navigation laterale, etats d'erreur, section `Rapport`, cartes `Enregistrements` et `Ajouter au site web`.
    - Internationalisation de `ui/src/app/workflow/[workflowId]/run/[runId]/page.tsx` : resume d'execution, pistes separees, labels de contexte, boutons de copie, telechargements, etat indisponible et tooltip d'onboarding.
    - Internationalisation de `ui/src/app/workflow/[workflowId]/components/WorkflowExecutions.tsx` pour les erreurs de chargement de la liste d'executions.
- **Decisions Techniques :** J'ai priorise les surfaces structurantes et les zones d'action visibles plutot que de traduire en bloc tout `settings/page.tsx`, afin de garder une progression propre et sans regression sur ce composant volumineux. La base de cles dediees permet maintenant d'etendre la meme logique section par section.
- **Impacts & Dependances :** Fichiers touches : `ui/src/lib/i18n/dictionaries.ts`, `ui/src/app/workflow/[workflowId]/settings/page.tsx`, `ui/src/app/workflow/[workflowId]/run/[runId]/page.tsx`, `ui/src/app/workflow/[workflowId]/components/WorkflowExecutions.tsx`, `ENGINEERING_LOG.md`. Diagnostics verifies sans erreur apres autofix ESLint.
- **Prochaines etapes :** Finir l'internationalisation section par section du grand formulaire `workflow/[workflowId]/settings/page.tsx` et etendre la meme discipline aux derniers dialogs secondaires encore en dur.

### [2026-07-05T23:02:28Z] | Passe i18n sur le detail workflow et le testeur
- **Contexte :** Apres la mise en place de l'i18n sur les surfaces principales et le parcours agents, le detail `workflow/[workflowId]` gardait encore beaucoup de textes en dur dans l'editeur, le header, le testeur et les etats d'erreur.
- **Modifications effectuees :**
    - Ajout de nouvelles cles de traduction dans `ui/src/lib/i18n/dictionaries.ts` pour le detail workflow, l'editeur, le testeur, les toasts d'actions et les boites de dialogue de sortie.
    - Internationalisation de `ui/src/app/workflow/[workflowId]/page.tsx` pour les erreurs de chargement et l'etat introuvable.
    - Internationalisation de `ui/src/app/workflow/[workflowId]/components/WorkflowEditorHeader.tsx` pour le renommage, les labels d'accessibilite, l'etat non enregistre, les erreurs de validation et les actions enregistrer/publier.
    - Internationalisation de `ui/src/app/workflow/[workflowId]/components/WorkflowTesterPanel.tsx` pour les onglets, les CTA, les notices de connexion, l'onboarding et les messages de lancement de test.
    - Internationalisation de `ui/src/app/workflow/[workflowId]/RenderWorkflow.tsx` pour les tooltips du canvas, le picker de noeuds, les toasts de duplication/publication, les messages d'etat du testeur, les libelles de version et la modale de sortie sans enregistrement.
- **Decisions Techniques :** J'ai cible en priorite les surfaces les plus visibles et les moins risquées du detail workflow pour conserver une progression propre sans toucher a la logique du canvas ou des runs. Les categories de noeuds sont maintenant resolues via i18n a l'execution plutot que figees en constante statique.
- **Impacts & Dependances :** Fichiers touches : `ui/src/lib/i18n/dictionaries.ts`, `ui/src/app/workflow/[workflowId]/page.tsx`, `ui/src/app/workflow/[workflowId]/RenderWorkflow.tsx`, `ui/src/app/workflow/[workflowId]/components/WorkflowEditorHeader.tsx`, `ui/src/app/workflow/[workflowId]/components/WorkflowTesterPanel.tsx`, `ENGINEERING_LOG.md`. Diagnostics verifies sans erreur ; seul reste un hint TypeScript non bloquant deja connu sur `beforeunload.returnValue`.
- **Prochaines etapes :** Etendre la meme discipline aux pages `workflow/[workflowId]/settings`, aux dialogs secondaires du workflow et a l'ecran `run/[runId]` pour achever la couverture bilingue du detail agent.

### [2026-07-05T22:53:59Z] | Deuxieme passe i18n sur le parcours agents et support SSR
- **Contexte :** Apres la premiere base i18n sur les ecrans principaux, le parcours `workflow` gardait encore beaucoup de textes visibles en dur et les pages serveur ne pouvaient pas suivre la langue choisie dans `Parametres` si elle etait stockee uniquement en local.
- **Modifications effectuees :**
    - Extension du dictionnaire i18n avec une section dediee au parcours agents : liste des agents, creation d'agent, actions de dossier, tableau et toasts associes.
    - Mise a jour de `ui/src/lib/i18n/locale.ts` pour persister aussi la langue dans un cookie, en plus du stockage local.
    - Creation de `ui/src/lib/i18n/server.ts` afin de lire la langue cote serveur et traduire proprement les pages SSR.
    - Internationalisation de `ui/src/app/workflow/page.tsx`, `ui/src/app/workflow/create/page.tsx`, `ui/src/components/workflow/CreateWorkflowButton.tsx`, `ui/src/components/workflow/folders/CreateFolderButton.tsx`, `ui/src/components/workflow/folders/FolderFormDialog.tsx`, `ui/src/components/workflow/WorkflowTable.tsx` et `ui/src/components/workflow/folders/FolderSection.tsx`.
    - Nettoyage de plusieurs messages utilisateur, placeholders, libelles d'actions et toasts pour obtenir un francais et un anglais plus coherents sur tout le parcours agents.
- **Decisions Techniques :** J'ai choisi de synchroniser la langue dans un cookie plutot que de bricoler un fallback uniquement client, car sinon les pages serveur de `workflow` seraient restees figees dans une langue differente du reste de l'interface. Cette approche garde une source de verite simple et compatible avec le routing actuel.
- **Impacts & Dependances :** Fichiers touches : `ui/src/lib/i18n/dictionaries.ts`, `ui/src/lib/i18n/locale.ts`, `ui/src/lib/i18n/server.ts`, `ui/src/app/workflow/page.tsx`, `ui/src/app/workflow/create/page.tsx`, `ui/src/components/workflow/CreateWorkflowButton.tsx`, `ui/src/components/workflow/folders/CreateFolderButton.tsx`, `ui/src/components/workflow/folders/FolderFormDialog.tsx`, `ui/src/components/workflow/WorkflowTable.tsx`, `ui/src/components/workflow/folders/FolderSection.tsx`, `ENGINEERING_LOG.md`. Diagnostics verifies sans erreur apres autofix ESLint.
- **Prochaines etapes :** Etendre la meme logique aux pages detail workflow, aux modales secondaires et aux composants transverses encore en dur pour finaliser la couverture bilingue.

### [2026-07-05T22:41:10Z] | Base i18n et passe linguistique FR/EN sur les ecrans principaux
- **Contexte :** L'utilisateur a demande de corriger les fautes de grammaire et d'orthographe sur la plateforme et de gerer proprement l'internationalisation en francais et en anglais, avec changement de langue depuis `Parametres`.
- **Modifications effectuees :**
    - Extension de `ui/src/lib/i18n/dictionaries.ts` avec une base de libelles FR/EN plus complete pour la navigation, `overview`, `settings`, la documentation, les preferences d'organisation, la telephonie, les outils, les fichiers et les enregistrements.
    - Mise a jour de `ui/src/lib/i18n/I18nProvider.tsx` pour synchroniser aussi l'attribut `lang` du document avec la langue active.
    - Internationalisation de `LanguageSelector`, `DocumentationHelp`, `AppSidebar`, `overview`, `settings`, `OrganizationPreferencesSection`, `telephony-configurations`, `tools`, `files` et `recordings`.
    - Correction de plusieurs formulations visibles et fautes residuelles dans les textes clients des zones touchees pour obtenir un francais et un anglais plus naturels.
    - Conservation du changement de langue dans `Parametres`, avec persistance locale fiable ; aucun champ backend de preference de langue n'etant expose par le schema actuel, aucune synchronisation serveur n'a ete ajoutee artificiellement.
- **Decisions Techniques :** J'ai commence par les composants shell et les ecrans les plus visibles afin que le basculement de langue soit coherent sur les surfaces structurantes. J'ai evite d'inventer un champ `locale` cote backend puisque le type `OrganizationPreferences` ne le supporte pas actuellement.
- **Impacts & Dependances :** Fichiers touches : `ui/src/lib/i18n/dictionaries.ts`, `ui/src/lib/i18n/I18nProvider.tsx`, `ui/src/components/LanguageSelector.tsx`, `ui/src/components/form/DocumentationHelp.tsx`, `ui/src/components/layout/AppSidebar.tsx`, `ui/src/app/overview/page.tsx`, `ui/src/app/settings/page.tsx`, `ui/src/components/OrganizationPreferencesSection.tsx`, `ui/src/app/telephony-configurations/page.tsx`, `ui/src/app/tools/page.tsx`, `ui/src/app/files/page.tsx`, `ui/src/app/recordings/page.tsx`, `ENGINEERING_LOG.md`. Diagnostics verifies sans erreur apres autofix ESLint.
- **Prochaines etapes :** Etendre la meme discipline i18n aux ecrans secondaires et dialogues encore en dur pour atteindre une couverture vraiment exhaustive de toute la plateforme.

### [2026-07-05T21:03:31Z] | Nettoyage global UI docs et references heritagees
- **Contexte :** L'utilisateur a demande un scan de l'UI pour retirer toute trace visible de Bookivox et remplacer les liens directs vers la documentation par un pattern plus propre avec point d'interrogation, explication puis redirection.
- **Modifications effectuees :**
    - Scan de `ui/src` pour verifier les references visibles a `Bookivox` et les liens directs vers `docs.bookivox.com`.
    - Verification qu'aucune occurrence visible de `Bookivox` ne restait dans l'UI.
    - Creation de `ui/src/components/form/DocumentationHelp.tsx` pour standardiser l'aide documentation sous forme de `?` avec explication et lien externe.
    - Remplacement des liens docs affiches en clair sur les pages et composants visibles : telephonie, outils, fichiers, enregistrements, settings, configuration telephonie, sheets de noeuds, dialogue d'erreur API et notices de conversation workflow.
    - Nettoyage ponctuel de quelques libelles visibles relies a ces zones pour garder un rendu coherent apres la conversion.
- **Decisions Techniques :** J'ai centralise le pattern dans un composant dedie plutot que de copier des tooltips partout. Cela limite les regressions de style et garantit que toute nouvelle aide documentation suive le meme comportement produit.
- **Impacts & Dependances :** Fichiers touches : `ui/src/components/form/DocumentationHelp.tsx`, `ui/src/app/telephony-configurations/page.tsx`, `ui/src/app/telephony-configurations/[configId]/page.tsx`, `ui/src/app/tools/page.tsx`, `ui/src/app/files/page.tsx`, `ui/src/app/recordings/page.tsx`, `ui/src/app/settings/page.tsx`, `ui/src/components/telephony/ConfigFormDialog.tsx`, `ui/src/components/flow/nodes/common/NodeEditDialog.tsx`, `ui/src/components/ServiceConfiguration.tsx`, `ui/src/app/workflow/[workflowId]/run/[runId]/components/ApiKeyErrorDialog.tsx`, `ui/src/components/workflow/conversation/NoticeCard.tsx`, `ENGINEERING_LOG.md`. Diagnostics verifies sans erreur apres autofix ESLint.
- **Prochaines etapes :** Une seconde passe plus large peut encore harmoniser les libelles anglais residuels hors perimetre docs si l'objectif devient une francisation complete de l'UI.

### [2026-07-05T20:53:35Z] | Ajustement d alignement des CTA sur overview
- **Contexte :** Apres la refonte de `/overview`, l'utilisateur a precise que le bouton devait etre aligne a droite plutot qu'a gauche pour rester coherent avec le reste de l'interface.
- **Modifications effectuees :**
    - Ajustement du CTA principal de `ui/src/app/overview/page.tsx` pour qu'il reste visuellement aligne a droite dans le header.
    - Alignement a droite des boutons de cartes sur la grille d'explication des sections de la sidebar.
- **Decisions Techniques :** J'ai corrige l'alignement directement au niveau de la page `overview` plutot que de modifier globalement `PageHeader`, afin de ne pas impacter les autres ecrans deja stabilises.
- **Impacts & Dependances :** Fichiers touches : `ui/src/app/overview/page.tsx`, `ENGINEERING_LOG.md`. Diagnostics verifies sans erreur apres la retouche.
- **Prochaines etapes :** Aucun suivi requis sauf si d'autres pages doivent adopter exactement le meme alignement de CTA.

### [2026-07-05T20:41:42Z] | Refonte de overview en guide simple de navigation
- **Contexte :** L'utilisateur a demande d'ameliorer `/overview` pour la rendre plus professionnelle tout en gardant un objectif tres simple : expliquer les differentes options disponibles dans la sidebar sans surcharger la page.
- **Modifications effectuees :**
    - Reprise de `ui/src/app/overview/page.tsx` avec un `PageHeader` plus propre et un positionnement plus clair de la page comme guide d'entree.
    - Ajout d'un bloc `Guide rapide` pour introduire les trois familles de navigation visibles dans la sidebar : `Construire`, `Preparer`, `Piloter`.
    - Remplacement des anciennes cartes generalistes par une grille de cartes qui decrivent directement chaque section importante de la sidebar avec un libelle clair, une courte explication et un CTA associe.
    - Alignement des icones de la page avec la navigation laterale pour renforcer la coherence visuelle et la comprehension.
- **Decisions Techniques :** J'ai volontairement evite d'ajouter des stats, tableaux ou contenus dynamiques ici. La page sert maintenant de point de repere editorial et produit, ce qui reduit la confusion pour un client qui decouvre la plateforme.
- **Impacts & Dependances :** Fichiers touches : `ui/src/app/overview/page.tsx`, `ENGINEERING_LOG.md`. Diagnostics verifies sans erreur apres la retouche.
- **Prochaines etapes :** Si besoin, reduire encore le nombre de cartes visibles en ne gardant que les sections les plus critiques pour une version encore plus minimaliste.

### [2026-07-05T19:44:05Z] | Confirmation avant achat de numero
- **Contexte :** L'utilisateur a demande une confirmation explicite avant l'achat d'un numero Bookivox afin d'indiquer qu'un debit sera effectue sur les credits avant de lancer l'achat.
- **Modifications effectuees :**
    - Ajout d'une modale de confirmation dans `ui/src/components/telephony/PhoneNumberDialog.tsx` avant l'appel API d'achat d'un numero gere par Bookivox.
    - Separation du flux de soumission pour distinguer la validation du formulaire, l'ouverture de la confirmation et l'execution effective de l'achat.
    - Affichage d'un recapitulatif minimal dans la confirmation avec le pays/indicatif et le libelle du numero pour limiter les erreurs de clic.
- **Decisions Techniques :** La confirmation n'est declenchee que pour l'achat d'un numero gere (`managedBookivoxNumber`) et pas pour l'ajout manuel ou l'edition d'un numero existant. Cela limite la friction aux actions qui ont un impact financier direct.
- **Impacts & Dependances :** Fichier touche : `ui/src/components/telephony/PhoneNumberDialog.tsx`, `ENGINEERING_LOG.md`. Diagnostics verifies sans erreur apres la retouche.
- **Prochaines etapes :** Si besoin, afficher ensuite le cout estime ou le tarif mensuel exact dans la confirmation si cette information est exposee de facon fiable par le backend.

### [2026-07-05T19:38:51Z] | Uniformisation de workflow/create avec la creation de campagne
- **Contexte :** L'utilisateur a demande que `workflow/create` soit aligne sur la meme qualite visuelle que `campaigns/new`, avec une page de creation plus propre, mieux structuree et plus cohérente avec les autres formulaires principaux.
- **Modifications effectuees :**
    - Refonte de `ui/src/app/workflow/create/page.tsx` autour du shell `PageHeader` + `PageShell`, avec bouton de retour, grille principale et hiérarchie en cartes comme sur la creation de campagne.
    - Remplacement des aides inline par les patterns `FieldRow` et `FieldHelp` pour compacter les champs `Type d'appel`, `Cas d'usage` et `Description de l'activite`.
    - Ajout d'une carte de conseils avant generation, d'un bloc d'erreur plus propre, d'actions alignees a droite et d'une carte laterale `Resume de l'agent`.
    - Polissage du loader et de la modale de succes pour les aligner au ton plus produit du reste de l'interface.
- **Decisions Techniques :** La logique de creation via template, la redirection post-creation et les etats de chargement restent inchanges. La passe est strictement structurelle et editoriale pour harmoniser l'experience de creation sans toucher a l'API.
- **Impacts & Dependances :** Fichiers touches : `ui/src/app/workflow/create/page.tsx`, `ENGINEERING_LOG.md`. Diagnostics verifies sans erreur sur la page apres retouche.
- **Prochaines etapes :** Si besoin, aligner ensuite encore plus finement les micro-details entre `workflow/create` et `campaigns/new`, par exemple le ton des placeholders ou l'habillage des etats de succes.

### [2026-07-05T19:36:20Z] | Regroupement de l import dans Nouvel agent
- **Contexte :** L'utilisateur a demande que `Importer un agent` ne soit plus un bouton separe, mais une option du menu `Nouvel agent`, avec un changement d'icones pour rendre les actions plus coherentes. Il a ensuite demande la meme attention visuelle pour `Nouveau dossier`.
- **Modifications effectuees :**
    - Refonte de `ui/src/components/workflow/CreateWorkflowButton.tsx` pour integrer directement l'import JSON dans le menu `Nouvel agent`, avec conservation de la modale d'import et du comportement existant.
    - Remplacement des icones du bloc `Nouvel agent` par un set plus explicite pour les trois entrees : creation assistee, canvas vide et import.
    - Suppression du bouton separe d'import dans `ui/src/app/workflow/page.tsx` et suppression du composant devenu inutile `ui/src/components/workflow/UploadWorkflowButton.tsx`.
    - Ajustement de `ui/src/components/workflow/folders/CreateFolderButton.tsx` pour donner a `Nouveau dossier` une icone plus en phase avec les autres CTA de la page.
- **Decisions Techniques :** J'ai privilegie un seul point d'entree pour la creation et l'import d'agent afin de reduire le bruit dans le header. La logique d'import reste intacte, mais son acces est maintenant mieux hierarchise.
- **Impacts & Dependances :** Fichiers touches : `ui/src/components/workflow/CreateWorkflowButton.tsx`, `ui/src/app/workflow/page.tsx`, `ui/src/components/workflow/folders/CreateFolderButton.tsx`, suppression de `ui/src/components/workflow/UploadWorkflowButton.tsx`, `ENGINEERING_LOG.md`. Diagnostics verifies sans erreur sur les fichiers conserves.
- **Prochaines etapes :** Si besoin, harmoniser ensuite encore davantage les CTA du header `/workflow` en affinant seulement leur taille, leur ordre ou leur contraste.

### [2026-07-05T19:33:03Z] | Uniformisation de la page workflow avec Campagnes
- **Contexte :** L'utilisateur a signale que `/workflow` n'etait pas au meme niveau d'uniformite que `campaigns`, avec une structure de page moins coherente et encore plusieurs libelles anglais ou hétérogènes.
- **Modifications effectuees :**
    - Reprise de `ui/src/app/workflow/page.tsx` pour aligner la page sur le schema `PageHeader` + cartes principales deja utilise sur `campaigns/page.tsx`, avec description, etats vides et chargement plus coherents.
    - Ajout d'une carte principale `Tous les agents` et d'une carte `Archives` pour mieux segmenter les contenus sans changer la logique de chargement des agents et des dossiers.
    - Francisation et harmonisation des actions et messages visibles dans `ui/src/components/workflow/CreateWorkflowButton.tsx`, `ui/src/components/workflow/UploadWorkflowButton.tsx`, `ui/src/components/workflow/folders/CreateFolderButton.tsx`, `ui/src/components/workflow/folders/FolderSection.tsx` et `ui/src/components/workflow/WorkflowTable.tsx`.
- **Decisions Techniques :** J'ai privilegie une passe de structure et de wording plutot qu'une refonte du systeme de dossiers. Le but etait d'aligner la perception produit de `/workflow` avec les autres pages principales sans casser les comportements de tri, d'archivage, de deplacement ou d'import.
- **Impacts & Dependances :** Fichiers touches : `ui/src/app/workflow/page.tsx`, `ui/src/components/workflow/CreateWorkflowButton.tsx`, `ui/src/components/workflow/UploadWorkflowButton.tsx`, `ui/src/components/workflow/folders/CreateFolderButton.tsx`, `ui/src/components/workflow/folders/FolderSection.tsx`, `ui/src/components/workflow/WorkflowTable.tsx`, `ENGINEERING_LOG.md`. Diagnostics verifies sans erreur sur les fichiers modifies.
- **Prochaines etapes :** Verifier ensuite si la creation d'agent (`/workflow/create`) merite la meme passe de normalisation pour garder une continuité parfaite avec la liste `/workflow`.

### [2026-07-05T17:30:21Z] | Ajustement de clarte sur la section Construire
- **Contexte :** Apres la passe de copywriting sur la sidebar, l'utilisateur a signale que les nouveaux libelles de la section `Créer` etaient moins clairs et pouvaient preter a confusion pour un client final.
- **Modifications effectuees :**
    - Remplacement du nom de section `Créer` par `Construire` dans `ui/src/components/layout/AppSidebar.tsx`.
    - Retour a des intitules plus immediats pour les trois entrees principales : `Agents vocaux`, `Campagnes`, `Outils & integrations`.
- **Decisions Techniques :** J'ai privilegie la clarte produit sur l'originalite editoriale. Sur une navigation primaire, un libelle familier et immediat vaut mieux qu'un terme plus marque mais ambigu.
- **Impacts & Dependances :** Fichiers touches : `ui/src/components/layout/AppSidebar.tsx`, `ENGINEERING_LOG.md`. Diagnostics verifies sans erreur apres ajustement.
- **Prochaines etapes :** Continuer a valider le wording section par section avec la meme regle : ne changer un nom que s'il gagne vraiment en comprehension cote client.

### [2026-07-05T17:15:07Z] | Repositionnement copywriting et icones de la sidebar
- **Contexte :** L'utilisateur voulait une nouvelle passe sur la sidebar pour l'eloigner encore du projet d'origine, en gardant la navbar haute intacte mais en changeant cette fois les textes visibles et tout le set d'icones.
- **Modifications effectuees :**
    - Reecriture des sections et libelles de `ui/src/components/layout/AppSidebar.tsx` pour une navigation plus produit et moins generique (`Vue d'ensemble`, `Studio agents`, `Diffusion`, `Connexions`, `Voix & modeles`, `Lignes & SIP`, `Base de connaissances`, `Captures`, `Activite`, `Syntheses`, `Credits`, `Acces API`).
    - Remplacement complet des icones de navigation par un set plus distinctif et plus editorial, sans changer les routes ni l'ordre global de la sidebar.
    - Ajout d'un traitement plus signe sur chaque entree avec une vignette d'icone discrete, un etat actif plus premium et un footer utilisateur legerement reworde (`Preferences`, `Organisation`, `Espace equipe`).
- **Decisions Techniques :** La passe reste concentree dans `AppSidebar.tsx` pour ne pas toucher au shell global. Le wording a ete raccourci et clarifie pour mieux coller a une lecture produit moderne, tandis que le nouvel habillage conserve les mecanismes existants de collapse, mobile et warning telephonie.
- **Impacts & Dependances :** Fichiers touches : `ui/src/components/layout/AppSidebar.tsx`, `ENGINEERING_LOG.md`. Diagnostics verifies sans erreur sur la sidebar apres retouche et autofix des imports.
- **Prochaines etapes :** Verifier le rendu en contexte sur quelques pages clefs pour confirmer que les nouveaux libelles restent immediatement compréhensibles une fois la sidebar reduite ou ouverte.

### [2026-07-05T17:06:48Z] | Passe minimale affinee sur la sidebar
- **Contexte :** L'utilisateur voulait toujours eloigner la sidebar du projet d'origine, mais sans refaire son design. L'objectif est devenu une passe tres mesuree, plus proche d'un polissage que d'une refonte.
- **Modifications effectuees :**
    - Ajustement des densites et espacements dans `ui/src/components/layout/AppSidebar.tsx` pour une lecture plus calme.
    - Remplacement de l'etat actif bleu par un etat plus neutre et plus premium.
    - Polissage discret du header, du trigger de reduction et du footer utilisateur pour mieux s'aligner avec le reste de l'application.
- **Decisions Techniques :** La structure et la logique de navigation restent intactes ; seule la perception visuelle est ajustee via des classes Tailwind locales a `AppSidebar.tsx`.
- **Impacts & Dependances :** Fichiers touches : `ui/src/components/layout/AppSidebar.tsx`, `ENGINEERING_LOG.md`. Diagnostics verifies sans erreur sur la sidebar apres retouche.
- **Prochaines etapes :** Observer le rendu en contexte reel pour decider si une ultime micro-passe sur l'etat actif ou les espacements est encore utile.

### [2026-07-05T17:05:19Z] | Recentrage sobre de la sidebar
- **Contexte :** La passe d'identite precedente sur la sidebar a ete jugee trop presente visuellement. L'objectif est revenu a une amelioration beaucoup plus legere, sans transformer la perception generale de navigation.
- **Modifications effectuees :**
    - Retrait de la variante flottante et retour a une base plus proche de la sidebar precedente dans `ui/src/components/layout/AppSidebar.tsx`.
    - Suppression des blocs de sections trop cartes, de l'accent lateral actif et du footer utilisateur trop editorialise.
    - Retour a une hierarchie plus neutre avec seulement des micro-ajustements conserves sur les libelles et l'equilibre global.
- **Decisions Techniques :** Le choix privilegie une intervention plus minimale pour respecter une UI deja bonne plutot que d'imposer une nouvelle signature visuelle trop forte.
- **Impacts & Dependances :** Fichiers touches : `ui/src/components/layout/AppSidebar.tsx`, `ENGINEERING_LOG.md`. Diagnostics verifies sans erreur apres recentrage.
- **Prochaines etapes :** Si besoin, retoucher ensuite la sidebar uniquement par micro-ajustements unitaires : densite, couleurs actives ou espaces, sans refaire sa structure.

### [2026-07-05T16:56:17Z] | Passe d identite sur la sidebar
- **Contexte :** L'utilisateur a demande une passe "magique" sur la sidebar pour qu'elle ne rappelle plus trop le projet d'origine, tout en gardant la navbar du haut inchangée et sans ajouter de bruit visuel.
- **Modifications effectuees :**
    - Refonte visuelle de `ui/src/components/layout/AppSidebar.tsx` avec une sidebar en style flottant plus premium.
    - Transformation des groupes de navigation en blocs plus distincts, avec fond leger, bordure douce et meilleur rythme vertical.
    - Reprise du lien actif avec un traitement plus sobre : contraste plus discret, accent lateral et meilleure hierarchie icone/texte.
    - Polissage du header de marque et du footer utilisateur pour supprimer l'effet trop generique et donner une identite plus produit.
- **Decisions Techniques :** Le changement reste concentre dans `AppSidebar.tsx` pour limiter le rayon d'impact et conserver la logique actuelle de navigation, de collapse et de mobile.
- **Impacts & Dependances :** Fichiers touches : `ui/src/components/layout/AppSidebar.tsx`, `ENGINEERING_LOG.md`. Diagnostics verifies sans erreur sur la sidebar apres retouche.
- **Prochaines etapes :** Si besoin, micro-ajuster ensuite les couleurs et densites des etats `hover` et `actif` apres revue visuelle en contexte reel.

### [2026-07-05T16:41:03Z] | Deuxieme passe sur les statuts residuels en majuscules
- **Contexte :** L'utilisateur a valide une deuxieme passe plus large pour capter les derniers statuts visibles encore non uniformises en majuscules sur les ecrans secondaires.
- **Modifications effectuees :**
    - Passage en majuscules du badge de disposition sur `ui/src/app/superadmin/runs/page.tsx`.
    - Uniformisation du statut de tool call dans `ui/src/components/workflow/conversation/ToolCallCard.tsx` avec `RUNNING` et `COMPLETED`.
- **Decisions Techniques :** La passe reste selective et ne touche que les derniers rendus clairement assimilables a des statuts, afin d'eviter un effet systematique sur des badges qui servent a autre chose.
- **Impacts & Dependances :** Fichiers touches : `ui/src/app/superadmin/runs/page.tsx`, `ui/src/components/workflow/conversation/ToolCallCard.tsx`, `ENGINEERING_LOG.md`. Diagnostics verifies sans erreur sur les fichiers modifies.
- **Prochaines etapes :** Surveiller au fil des retouches futures les nouveaux badges ajoutes, pour garder cette regle de majuscules coherente dans toute l'interface.

### [2026-07-05T16:38:47Z] | Statuts UI uniformises en majuscules
- **Contexte :** L'utilisateur a demande que les valeurs de statut et les etats de plateforme soient affiches en majuscules dans l'interface.
- **Modifications effectuees :**
    - Passage en majuscules des badges d'etat sur les campagnes (`ui/src/app/campaigns/page.tsx`, `ui/src/app/campaigns/[campaignId]/page.tsx`).
    - Passage en majuscules des badges de statut sur les outils, documents et cles API (`ui/src/app/tools/page.tsx`, `ui/src/app/files/DocumentList.tsx`, `ui/src/app/api-keys/page.tsx`).
    - Passage en majuscules des etats visibles sur la telephonie et les executions (`ui/src/app/telephony-configurations/[configId]/page.tsx`, `ui/src/components/workflow-runs/WorkflowRunsTable.tsx`, `ui/src/app/usage/page.tsx`).
    - Harmonisation du badge de statut dans l'historique des versions workflow (`ui/src/app/workflow/[workflowId]/components/VersionHistoryPanel.tsx`).
- **Decisions Techniques :** La passe reste ciblee sur les badges servant vraiment a afficher un statut ou un etat, afin d'eviter de forcer en majuscules des badges purement categoriels ou descriptifs.
- **Impacts & Dependances :** Fichiers touches : `ui/src/app/campaigns/page.tsx`, `ui/src/app/campaigns/[campaignId]/page.tsx`, `ui/src/app/tools/page.tsx`, `ui/src/app/files/DocumentList.tsx`, `ui/src/app/api-keys/page.tsx`, `ui/src/app/telephony-configurations/[configId]/page.tsx`, `ui/src/components/workflow-runs/WorkflowRunsTable.tsx`, `ui/src/app/usage/page.tsx`, `ui/src/app/workflow/[workflowId]/components/VersionHistoryPanel.tsx`, `ENGINEERING_LOG.md`. Diagnostics verifies sans erreur sur les fichiers modifies.
- **Prochaines etapes :** Si besoin, etendre la meme regle a d'autres ecrans secondaires encore non aligns si l'utilisateur repere des statuts residuels hors de cette passe.

### [2026-07-05T14:57:55Z] | Uniformisation des aides sur les booleens des sheets de noeuds
- **Contexte :** L'utilisateur a precise que, dans les sheets de configuration des noeuds, toutes les explications devaient suivre le meme pattern avec point d'interrogation, y compris pour les switch et checkbox.
- **Modifications effectuees :**
    - Mise a jour de `ui/src/components/flow/renderer/PropertyInput.tsx` pour que les champs booleens n'affichent plus leur description en texte inline.
    - Passage des booleens sur le meme schema que les autres champs : libelle + aide `FieldHelp`, avec un conteneur plus propre et un switch aligne a droite.
- **Decisions Techniques :** Le changement reste centralise dans le renderer commun pour couvrir tous les booleens rendus dans les sheets sans modifier chaque noeud individuellement.
- **Impacts & Dependances :** Fichiers touches : `ui/src/components/flow/renderer/PropertyInput.tsx`, `ENGINEERING_LOG.md`. Diagnostics verifies sans erreur sur le renderer.
- **Prochaines etapes :** Si besoin, faire une passe encore plus fine sur certains selecteurs de contenu pour reduire aussi les micro-aides visibles non essentielles a l'interieur des listes.

### [2026-07-05T13:12:15Z] | Reorganisation logique des champs dans les sheets de noeuds
- **Contexte :** L'utilisateur a precise que l'ordre des champs dans les sheets de configuration devait etre plus logique et coherent, notamment pour eviter de retrouver le nom du noeud en fin de formulaire.
- **Modifications effectuees :**
    - Ajout d'une priorisation commune dans `ui/src/components/flow/renderer/NodeEditForm.tsx` pour remonter les champs d'identite (`name`, `title`, `label`, variantes `*_name`) en tete.
    - Remontee des champs de contenu structurants (`prompt`, `instruction`, `message`, `description`) avant les champs secondaires.
    - Deplacement des credentials, secrets et toggles `enabled` plus bas dans le formulaire pour une lecture plus naturelle.
    - Mise a jour du titre de configuration dans `ui/src/components/flow/nodes/GenericNode.tsx` pour passer de `Edit ...` a `Configurer ...`.
- **Decisions Techniques :** Le tri reste stable et conserve l'ordre d'origine entre les champs d'une meme priorite, afin d'ameliorer l'UX sans casser les schemas ni produire d'effets de bord sur les formulaires existants.
- **Impacts & Dependances :** Fichiers touches : `ui/src/components/flow/renderer/NodeEditForm.tsx`, `ui/src/components/flow/nodes/GenericNode.tsx`, `ENGINEERING_LOG.md`. Diagnostics verifies sans erreur sur les fichiers modifies.
- **Prochaines etapes :** Si besoin, affiner ensuite certains cas specifiques par type de noeud si un formulaire merite encore un ordre plus editorial que generique.

### [2026-07-05T13:08:33Z] | Conversion des configurations de noeuds en sheets
- **Contexte :** L'utilisateur a demande que les modales de configuration des noeuds deviennent des sheets plus propres et plus coherents avec les autres panneaux lateraux du workflow.
- **Modifications effectuees :**
    - Conversion de `ui/src/components/flow/nodes/common/NodeEditDialog.tsx` d'une `Dialog` vers un `Sheet` lateral.
    - Refonte de la structure avec header fixe, corps scrollable et footer stable pour les actions.
    - Harmonisation du wording visible (`Annuler`, `Enregistrer`, `Lecture seule`) et francisation de la confirmation d'abandon.
- **Decisions Techniques :** Le changement passe par le composant commun utilise par `GenericNode`, ce qui permet de basculer la majorite des formulaires de noeuds sans retoucher la logique de chaque type de noeud individuellement.
- **Impacts & Dependances :** Fichiers touches : `ui/src/components/flow/nodes/common/NodeEditDialog.tsx`, `ENGINEERING_LOG.md`. Diagnostics verifies sans erreur sur `NodeEditDialog.tsx` et `GenericNode.tsx`.
- **Prochaines etapes :** Si besoin, appliquer la meme logique aux dialogues d'edition d'aretes pour aligner aussi les conditions de transition sur le meme pattern de sheet.

### [2026-07-05T12:56:23Z] | Popup compacte pour l ajout de noeud
- **Contexte :** L'utilisateur a demande que le clic dans le canvas n'affiche plus un simple bouton `Ajouter un noeud`, mais une petite popup propre avec une barre de recherche et la liste des noeuds disponibles.
- **Modifications effectuees :**
    - Refonte de l'ajout rapide dans `ui/src/app/workflow/[workflowId]/RenderWorkflow.tsx` pour ouvrir une popup compacte directement au point de clic.
    - Ajout d'un champ de recherche, d'une liste filtree, des icones correspondantes par type de noeud et des badges de categorie.
    - Alignement du bouton `+` du rail flottant sur ce meme comportement pour garder une seule UX d'ajout.
    - Fermeture propre sur clic exterieur ou touche `Echap`, avec focus automatique sur le champ de recherche.
- **Decisions Techniques :** La logique d'ajout de noeud reste la meme (`handleNodeSelect`), seul le point d'entree UI change. Les contraintes de nombre maximal par noeud continuent d'etre respectees dans la popup.
- **Impacts & Dependances :** Fichier touche : `ui/src/app/workflow/[workflowId]/RenderWorkflow.tsx`, `ENGINEERING_LOG.md`. Diagnostics verifies sans erreur bloquante ; seul le hint standard sur `beforeunload.returnValue` reste present.
- **Prochaines etapes :** Si besoin, raffiner encore cette popup avec navigation clavier plus poussee ou categories repliables sans changer l'experience actuelle.

### [2026-07-05T12:50:12Z] | Repositionnement de Tester l agent
- **Contexte :** L'utilisateur a demande de changer l'icone de `Tester l'agent` et de remettre cette action egalement dans la navbar, tout en conservant la logique `Enregistrer / Publier`.
- **Modifications effectuees :**
    - Remplacement de l'icone de test par une icone `Play` plus directe dans `ui/src/app/workflow/[workflowId]/RenderWorkflow.tsx`.
    - Ajout de `Tester l'agent` dans `ui/src/app/workflow/[workflowId]/components/WorkflowEditorHeader.tsx` sous forme de bouton icone discret dans la navbar.
- **Decisions Techniques :** `Tester l'agent` redevient visible dans deux points d'acces coherents, mais reste une action secondaire visuellement plus legere que `Enregistrer` et `Publier`.
- **Impacts & Dependances :** Fichiers touches : `ui/src/app/workflow/[workflowId]/components/WorkflowEditorHeader.tsx`, `ui/src/app/workflow/[workflowId]/RenderWorkflow.tsx`, `ENGINEERING_LOG.md`. Diagnostics verifies sans erreur bloquante ; seul le hint standard sur `beforeunload.returnValue` reste present.
- **Prochaines etapes :** Ajuster encore la densite ou le contraste du bouton de test si l'utilisateur souhaite une hierarchie visuelle encore plus marquée.

### [2026-07-05T12:49:10Z] | Retour de Tester l agent dans le rail workflow
- **Contexte :** L'utilisateur a precise que `Tester l'agent` devait rester accessible en permanence pour ouvrir le panneau de test, meme apres la simplification des actions principales.
- **Modifications effectuees :**
    - Reintroduction de l'action `Tester l'agent` dans le rail flottant gauche de `ui/src/app/workflow/[workflowId]/RenderWorkflow.tsx`.
    - Ajout d'un tooltip explicite et conservation du blocage automatique quand le brouillon n'est pas enregistrable ou testable.
- **Decisions Techniques :** `Tester l'agent` reste une action secondaire permanente et ne revient pas dans la barre principale, ce qui preserve la logique `Enregistrer` puis `Publier` tout en gardant un acces rapide au test.
- **Impacts & Dependances :** Fichiers touches : `ui/src/app/workflow/[workflowId]/RenderWorkflow.tsx`, `ENGINEERING_LOG.md`. Diagnostics verifies sans erreur bloquante ; seul le hint standard sur `beforeunload.returnValue` reste present.
- **Prochaines etapes :** Continuer a raffiner le rail flottant si d'autres priorites d'usage doivent remonter sans surcharger la barre haute.

### [2026-07-05T12:48:29Z] | Actions principales et garde de sortie dans l editeur workflow
- **Contexte :** L'utilisateur a precise que l'editeur devait conserver seulement deux actions principales visibles, `Enregistrer` puis `Publier`, avec une apparition de `Publier` apres sauvegarde, ainsi qu'une modale de danger lorsqu'on tente de quitter avec des modifications non enregistrees.
- **Modifications effectuees :**
    - Reprise de `ui/src/app/workflow/[workflowId]/components/WorkflowEditorHeader.tsx` pour retirer `Tester l'agent` de la barre principale et faire alterner `Enregistrer` puis `Publier` selon l'etat du brouillon.
    - Mise a jour de `ui/src/app/workflow/[workflowId]/RenderWorkflow.tsx` pour piloter `Publier` depuis le header et retirer cette action du rail flottant.
    - Ajout d'une modale `AlertDialog` de confirmation avant de quitter l'editeur quand des changements non enregistres existent.
    - Protection des sorties principales de l'editeur (`retour`, `reglages`, `executions`, `duplication`) et ajout d'une garde `beforeunload` pour les fermetures/rechargements du navigateur.
- **Decisions Techniques :** La logique de sauvegarde et de publication existante est conservee. Le changement porte sur la hierarchie des actions visibles et sur la prevention de pertes de travail, en suivant le comportement deja etabli sur la page `settings`.
- **Impacts & Dependances :** Fichiers touches : `ui/src/app/workflow/[workflowId]/components/WorkflowEditorHeader.tsx`, `ui/src/app/workflow/[workflowId]/RenderWorkflow.tsx`, `ENGINEERING_LOG.md`. Diagnostics IDE verifies sans erreur bloquante ; seul un hint TypeScript standard reste sur `beforeunload.returnValue`.
- **Prochaines etapes :** Si besoin, etendre la meme garde aux autres parcours d'edition riches qui exposent des modifications locales avant sauvegarde.

### [2026-07-05T12:43:46Z] | Reorientation n8n de l editeur workflow
- **Contexte :** L'utilisateur a demande un editeur `workflow/[workflowId]` moins charge dans la navbar, avec seulement deux actions principales visibles, des actions secondaires en icones flottantes a gauche, une proposition d'ajout de noeud au clic dans le canvas et la suppression des renvois visibles rappelant l'ancien produit.
- **Modifications effectuees :**
    - Recomposition de `ui/src/app/workflow/[workflowId]/components/WorkflowEditorHeader.tsx` pour ne garder que deux CTA principaux dans la barre haute.
    - Reprise de `ui/src/app/workflow/[workflowId]/RenderWorkflow.tsx` avec un rail flottant vertical au milieu a gauche pour les actions secondaires (reglages, versions, appel test, publication, executions et plus d'options) et un prompt `Ajouter un noeud` au clic vide dans le canvas.
    - Extension de `ui/src/app/workflow/[workflowId]/hooks/useWorkflowState.ts` pour permettre d'ajouter un noeud a une position cible choisie dans le canvas au lieu de toujours le centrer.
    - Nettoyage des renvois visibles dans `ui/src/components/flow/AddNodePanel.tsx` et `ui/src/app/workflow/[workflowId]/components/EmbedDialog.tsx`, ainsi que suppression du nudge expert dans l'editeur principal.
- **Decisions Techniques :** La logique de workflow, de sauvegarde, de publication, de duplication et de creation de noeud est conservee. Le changement porte sur la structure d'acces aux actions et sur le placement des nouveaux noeuds pour rapprocher l'experience d'une navigation plus type n8n.
- **Impacts & Dependances :** Fichiers touches : `ui/src/app/workflow/[workflowId]/RenderWorkflow.tsx`, `ui/src/app/workflow/[workflowId]/components/WorkflowEditorHeader.tsx`, `ui/src/app/workflow/[workflowId]/hooks/useWorkflowState.ts`, `ui/src/components/flow/AddNodePanel.tsx`, `ui/src/app/workflow/[workflowId]/components/EmbedDialog.tsx`, `ENGINEERING_LOG.md`. Diagnostics IDE verifies sans erreur sur les fichiers principaux modifies ; `EmbedDialog.tsx` ne conserve qu'un hint TypeScript non bloquant sur `onKeyPress` deja preexistant.
- **Prochaines etapes :** Si l'utilisateur le souhaite, pousser encore la direction n8n en raffinant la densite visuelle du rail flottant et le comportement du prompt d'ajout de noeud selon le zoom ou le niveau de selection.

### [2026-07-05T11:48:19Z] | Conversion de Appel test en sheet
- **Contexte :** L'utilisateur a precise que `Appel test` devait devenir un sheet, car l'apparition de nouvelles actions apres le lancement de l'appel surchargeait la modale classique.
- **Modifications effectuees :**
    - Conversion de `ui/src/app/workflow/[workflowId]/components/PhoneCallDialog.tsx` d'une `Dialog` vers un `Sheet` lateral.
    - Ajout d'une structure plus adaptee avec header fixe, corps scrollable et footer d'actions stable pour absorber les etats `chargement`, `succes` et `recommencer`.
    - Suppression du libelle visible `Mode manuel` dans `ui/src/app/workflow/[workflowId]/components/WorkflowTesterPanel.tsx` pour poursuivre l'epuration de la surface de test.
- **Decisions Techniques :** La logique de chargement, de preferences, de configuration telephonique et de lancement d'appel reste intacte. Le changement est strictement structurel et presentationnel pour mieux gerer l'evolution des actions dans le temps.
- **Impacts & Dependances :** Fichiers touches : `ui/src/app/workflow/[workflowId]/components/PhoneCallDialog.tsx`, `ui/src/app/workflow/[workflowId]/components/WorkflowTesterPanel.tsx`, `ENGINEERING_LOG.md`. Diagnostics IDE verifies sans erreur sur les deux composants modifies.
- **Prochaines etapes :** Si besoin, appliquer la meme logique aux autres modales de workflow qui evoluent fortement selon leur etat.

### [2026-07-05T11:24:56Z] | Harmonisation du formulaire Appel test
- **Contexte :** L'utilisateur a precise que les champs visibles dans la modale `Appel test` devaient suivre les memes regles visuelles que les autres formulaires du site.
- **Modifications effectuees :**
    - Alignement de `ui/src/app/workflow/[workflowId]/components/PhoneCallDialog.tsx` sur les patterns de formulaire internes avec `FieldRow` pour les groupes de champs.
    - Remplacement du `PhoneInput` brut par `PhoneField`, le wrapper interne deja utilise dans le projet, pour harmoniser le rendu du champ telephone avec les autres controles.
    - Simplification des blocs de feedback et remise des espacements/hauteurs de champs sur le meme rythme que les autres modales.
- **Decisions Techniques :** Aucun changement de logique sur la sauvegarde des preferences, la selection de configuration, le choix du numero sortant ou le lancement d'appel. Le travail se limite a reutiliser les composants de formulaire standards du projet.
- **Impacts & Dependances :** Fichiers touches : `ui/src/app/workflow/[workflowId]/components/PhoneCallDialog.tsx`, `ENGINEERING_LOG.md`. Diagnostics IDE verifies sans erreur apres retouche.
- **Prochaines etapes :** Si l'utilisateur le souhaite, appliquer la meme normalisation aux autres modales workflow qui utilisent encore un rythme de champs legerement different.

### [2026-07-05T11:22:35Z] | Polissage de la modale Appel test
- **Contexte :** L'utilisateur a demande d'ameliorer les modales visibles sur la page workflow, en priorite la modale `Appel test`, sans toucher aux sheets ni a la logique.
- **Modifications effectuees :**
    - Reprise de `ui/src/app/workflow/[workflowId]/components/PhoneCallDialog.tsx` avec un header plus propre, une vraie separation entre les zones de configuration et la destination d'appel, et un footer plus net.
    - Ajout d'etats de chargement, succes et erreur mieux presentes dans des blocs visuels sobres au lieu de simples lignes de texte.
    - Compactage et clarification des textes visibles pour rendre la modale plus premium et plus lisible.
- **Decisions Techniques :** Aucun changement fonctionnel n'a ete apporte au chargement des preferences, a la selection de configuration, a la gestion SIP/telephone ou au lancement d'appel. La passe reste strictement presentationnelle.
- **Impacts & Dependances :** Fichier touche : `ui/src/app/workflow/[workflowId]/components/PhoneCallDialog.tsx`, `ENGINEERING_LOG.md`. Diagnostics IDE verifies sans erreur apres retouche.
- **Prochaines etapes :** Si besoin, appliquer la meme finition aux autres modales visibles du workflow pour harmoniser tout le parcours.

### [2026-07-05T11:18:01Z] | Epuration minimale de l editeur workflow
- **Contexte :** L'utilisateur a precise que `workflow/[workflowId]` ne devait pas etre davantage enrichi visuellement, mais au contraire epure pour s'eloigner du rendu Bookivox tout en gardant la navbar et la structure actuelle jugees deja bonnes.
- **Modifications effectuees :**
    - Allégement de `ui/src/app/workflow/[workflowId]/RenderWorkflow.tsx` avec controles flottants plus discrets, fond canvas plus doux et rail de test un peu moins imposant.
    - Simplification de `ui/src/app/workflow/[workflowId]/components/WorkflowEditorHeader.tsx` : badges et etats reduits, actions moins massives, historique/version plus leger, bouton principal moins "marketing".
    - Nettoyage de `ui/src/app/workflow/[workflowId]/components/WorkflowTesterPanel.tsx` pour retirer du texte superflu et garder un panneau de test plus sobre.
    - Raffinement de `ui/src/app/workflow/[workflowId]/components/VersionHistoryPanel.tsx` pour un panneau moins lourd visuellement.
- **Decisions Techniques :** J'ai volontairement evite d'ajouter de nouveaux blocs, cartes ou aides. La passe est strictement subtractive et stylistique pour conserver les flux existants tout en rapprochant l'editeur d'une direction plus minimaliste inspiree des outils d'agents vocaux modernes.
- **Impacts & Dependances :** Fichiers touches : `ui/src/app/workflow/[workflowId]/RenderWorkflow.tsx`, `ui/src/app/workflow/[workflowId]/components/WorkflowEditorHeader.tsx`, `ui/src/app/workflow/[workflowId]/components/WorkflowTesterPanel.tsx`, `ui/src/app/workflow/[workflowId]/components/VersionHistoryPanel.tsx`, `ENGINEERING_LOG.md`. Diagnostics IDE verifies sans erreur sur les composants modifies.
- **Prochaines etapes :** Si l'utilisateur veut aller encore plus loin, la prochaine passe pourra viser un affinage tres subtil des espacements et des poids typographiques du header sans toucher au comportement.

### [2026-07-05T11:04:20Z] | Polissage du testeur workflow et des pages d execution
- **Contexte :** L'utilisateur a demande d'etendre la passe UI/UX a tout le parcours `workflow/` encore brut visuellement, notamment le panneau de test dans l'editeur, la liste des executions et la page `workflow/[workflowId]/run/[runId]`.
- **Modifications effectuees :**
    - Retouche de `ui/src/app/workflow/[workflowId]/components/WorkflowTesterPanel.tsx` avec onglets francises, aides plus claires, CTA plus propres et onboarding reformule.
    - Ajustement de `ui/src/app/workflow/[workflowId]/components/workflow-tester/shared.tsx`, `ManualTextChatPanel.tsx`, `ChatComposer.tsx`, `TurnMessageActions.tsx` et `EmbeddedVoiceTester.tsx` pour lisser les etats vides, les libelles d'action, le wording conversationnel et la presentation du test vocal.
    - Nettoyage de `ui/src/app/workflow/[workflowId]/components/WorkflowExecutions.tsx` pour harmoniser la largeur de page et les messages d'erreur visibles.
    - Reprise de `ui/src/app/workflow/[workflowId]/run/[runId]/page.tsx` avec cartes de synthese plus lisibles, actions regroupees, labels moins techniques, piste audio split plus claire et wording plus client.
- **Decisions Techniques :** La logique de test, de creation d'execution, d'audio et de navigation reste intacte. Les changements portent uniquement sur la copie visible, les alignements, l'habillage des cartes et la structure visuelle afin de limiter tout risque fonctionnel.
- **Impacts & Dependances :** Fichiers touches : `ui/src/app/workflow/[workflowId]/components/WorkflowTesterPanel.tsx`, `ui/src/app/workflow/[workflowId]/components/workflow-tester/shared.tsx`, `ui/src/app/workflow/[workflowId]/components/workflow-tester/ManualTextChatPanel.tsx`, `ui/src/app/workflow/[workflowId]/components/workflow-tester/ChatComposer.tsx`, `ui/src/app/workflow/[workflowId]/components/workflow-tester/TurnMessageActions.tsx`, `ui/src/app/workflow/[workflowId]/components/workflow-tester/EmbeddedVoiceTester.tsx`, `ui/src/app/workflow/[workflowId]/components/WorkflowExecutions.tsx`, `ui/src/app/workflow/[workflowId]/run/[runId]/page.tsx`, `ENGINEERING_LOG.md`. Diagnostics IDE verifies sans erreur sur tous les fichiers modifies.
- **Prochaines etapes :** Si besoin, pousser la meme passe de finition sur les micro-dialogues restants lies aux tests temps reel et aux pages annexes du workflow si l'utilisateur veut une uniformisation encore plus profonde.

### [2026-07-05T10:53:07Z] | Finition UI du workflow et de ses reglages
- **Contexte :** L'utilisateur a demande une passe de finition sur `workflow/[workflowId]` et `workflow/[workflowId]/settings`, sans toucher a la logique existante, afin de mieux aligner les actions a droite, compacter les textes d'aide et lisser le wording.
- **Modifications effectuees :**
    - Retouche de `ui/src/app/workflow/[workflowId]/RenderWorkflow.tsx` avec tooltips francises, panneaux d'actions canvas plus propres et messages de blocage du testeur reformules.
    - Nettoyage de `ui/src/app/workflow/[workflowId]/page.tsx` pour retirer les messages d'erreur anglais visibles.
    - Refonte douce de `ui/src/app/workflow/[workflowId]/settings/page.tsx` : aides inline remplacees par `FieldHelp`, descriptions compactees, copies francisees, CTA secondaires/primaires mieux places a droite et header plus propre avec retour vers l'editeur.
    - Harmonisation des cartes `Rapport`, `Variables`, `Dictionnaire`, `Detection de messagerie`, `Enregistrements`, `Ajouter au site web` et `UUID agent`.
- **Decisions Techniques :** J'ai conserve les composants, les appels API et les flux de sauvegarde existants. Les changements restent strictement presentationnels pour reduire le risque de regression tout en alignant ces ecrans sur le pattern UI deja utilise ailleurs dans l'application.
- **Impacts & Dependances :** Fichiers touches : `ui/src/app/workflow/[workflowId]/page.tsx`, `ui/src/app/workflow/[workflowId]/RenderWorkflow.tsx`, `ui/src/app/workflow/[workflowId]/settings/page.tsx`, `ENGINEERING_LOG.md`. Validation effectuee : diagnostics IDE OK sur les trois fichiers modifies.
- **Prochaines etapes :** Si besoin, prolonger la meme passe de copywriting dans `WorkflowTesterPanel` et dans les ecrans de detail d'execution lies au workflow pour finir d'homogeneiser tout le parcours.

### [2026-07-05T10:45:00Z] | Suppression des identifiants visibles dans l UI
- **Contexte :** L'utilisateur a demande qu'aucun identifiant interne utilise pour les routes ou la navigation ne soit plus affiche a l'ecran cote client.
- **Modifications effectuees :**
    - Suppression des colonnes `ID` et des valeurs `#{id}` dans les tableaux de `usage`, `campaigns`, `workflow-runs` et `superadmin/runs`.
    - Retrait des identifiants affiches dans les listes de selection et liens de `campaigns/new`, `telephony-configurations/[configId]` et `PhoneNumberDialog`.
    - Remplacement des liens `Campaign #{id}`, `Configuration #{id}` et `workflow_run_id` par des libelles orientés action ou par des noms quand ils existent.
    - Suppression de l'affichage de l'ID de configuration dans `ConfigFormDialog` et du `source_id` brut dans le detail de campagne.
    - Retrait de l'identifiant visible dans le header du sheet `MediaPreviewDialog` et dans le header des noeuds du canvas.
- **Decisions Techniques :** J'ai conserve tous les identifiants necessaires au routage, aux appels API et aux interactions internes, mais je les ai retires de l'affichage ou remplaces par des libelles utiles pour l'utilisateur final.
- **Impacts & Dependances :** Fichiers touches : `ui/src/app/usage/page.tsx`, `ui/src/components/MediaPreviewDialog.tsx`, `ui/src/app/campaigns/new/page.tsx`, `ui/src/app/campaigns/[campaignId]/page.tsx`, `ui/src/app/billing/page.tsx`, `ui/src/app/telephony-configurations/[configId]/page.tsx`, `ui/src/components/telephony/PhoneNumberDialog.tsx`, `ui/src/components/workflow-runs/WorkflowRunsTable.tsx`, `ui/src/app/superadmin/runs/page.tsx`, `ui/src/app/campaigns/page.tsx`, `ui/src/components/workflow/WorkflowTable.tsx`, `ui/src/components/flow/nodes/common/NodeContent.tsx`, `ui/src/components/telephony/ConfigFormDialog.tsx`, `ENGINEERING_LOG.md`.
- **Prochaines etapes :** Une occurrence technique subsiste dans `ui/src/components/flow/MentionTextarea.tsx` avec `RECORDING_ID`, qui semble faire partie de la syntaxe fonctionnelle des mentions et non d'un identifiant de route affiche comme meta-donnee UI. A reevaluer separement si l'on veut aussi masquer cette syntaxe sans casser le comportement.

### [2026-07-05T10:35:29Z] | Passe copywriting sur la page usage
- **Contexte :** L'utilisateur a demande un langage plus courant, moins oriente produit interne ou dev, avec un vrai travail de copywriting sur `usage` et sur l'aperçu d'execution.
- **Modifications effectuees :**
    - Reecriture de `ui/src/app/usage/page.tsx` : hero, cartes de synthese, bloc de filtres, resume de selection, titres de section, colonnes de tableau et etat vide.
    - Reecriture de `ui/src/components/DailyUsageTable.tsx` avec un ton plus simple et plus lisible cote client.
    - Ajustement de `ui/src/components/MediaPreviewDialog.tsx` pour un wording plus naturel dans le header, le bloc audio et l'action de telechargement.
- **Decisions Techniques :** J'ai privilegie des formulations courtes, concretes et directement comprehensibles par un utilisateur final, tout en conservant l'information utile et sans introduire de nouvelles notions produit ambiguës.
- **Impacts & Dependances :** Fichiers touches : `ui/src/app/usage/page.tsx`, `ui/src/components/DailyUsageTable.tsx`, `ui/src/components/MediaPreviewDialog.tsx`, `ENGINEERING_LOG.md`. Effet attendu : meilleure comprehension immediate, page plus premium et reduction du ton technique.
- **Prochaines etapes :** Si besoin, etendre la meme logique de copywriting aux pages `reports` et `workflow-runs` pour harmoniser tout le parcours d'analyse.

### [2026-07-05T10:30:51Z] | Simplification du wording sur usage et apercu d execution
- **Contexte :** Apres la refonte de `usage`, certains textes restaient trop demonstratifs ou trop systeme, notamment les cartes de synthese et les blocs `Audio` / `Transcription` en tete du sheet d'apercu.
- **Modifications effectuees :**
    - Simplification des cartes de synthese dans `ui/src/app/usage/page.tsx` avec des libelles plus directs et plus naturels cote utilisateur.
    - Suppression des blocs explicatifs `Audio` et `Transcription` en haut de `ui/src/components/MediaPreviewDialog.tsx`.
- **Decisions Techniques :** J'ai garde la structure visuelle en place et j'ai uniquement allege la copie visible, pour conserver le gain de design sans recharger l'interface avec du texte qui n'apporte pas de valeur immediate.
- **Impacts & Dependances :** Fichiers touches : `ui/src/app/usage/page.tsx`, `ui/src/components/MediaPreviewDialog.tsx`, `ENGINEERING_LOG.md`. Effet attendu : lecture plus fluide, interface plus premium et messages plus adaptes a un usage client.
- **Prochaines etapes :** Si besoin, lisser encore le wording du bloc `Filtres et export` et des titres de colonnes pour aller vers une tonalite encore plus premium.

### [2026-07-05T10:27:37Z] | Refonte de la page usage et de l apercu d execution
- **Contexte :** La page `ui/src/app/usage/page.tsx` manquait de hierarchie visuelle et l'aperçu `Aperçu de l'execution` utilisait encore une modale classique peu adaptee aux transcriptions longues. Le besoin etait de rendre l'ensemble plus premium tout en gardant l'uniformite de l'application.
- **Modifications effectuees :**
    - Recomposition de `ui/src/app/usage/page.tsx` avec cartes de synthese, bloc filtres/export mieux encadre et historique d'executions plus propre visuellement.
    - Refonte de `ui/src/components/DailyUsageTable.tsx` : francisation, libelles plus professionnels et rendu plus coherent avec les cartes du reste de l'application.
    - Conversion de `ui/src/components/MediaPreviewDialog.tsx` d'une modale `Dialog` vers un `Sheet` avec header, corps scrollable, bloc transcription a scroll interne controle et footer fixe.
- **Decisions Techniques :** J'ai conserve les appels API, la pagination et la logique de filtres existantes pour limiter le risque fonctionnel. L'aperçu a ete converti dans le composant partage afin que la meme amelioration profite aussi aux autres tableaux d'executions qui reutilisent deja ce composant.
- **Impacts & Dependances :** Fichiers touches : `ui/src/app/usage/page.tsx`, `ui/src/components/DailyUsageTable.tsx`, `ui/src/components/MediaPreviewDialog.tsx`, `ENGINEERING_LOG.md`. Effet attendu : meilleure lisibilite de `usage`, navigation plus fluide dans les aperçus et meilleur controle des contenus longs.
- **Prochaines etapes :** Si besoin, harmoniser ensuite `ui/src/components/workflow-runs/WorkflowRunsTable.tsx`, qui reutilise deja le nouveau sheet mais conserve encore plusieurs libelles anglais sur son tableau principal.

### [2026-07-05T10:22:04Z] | Francisation du parcours creation et edition de campagne
- **Contexte :** Les ecrans `campaigns/new` et `campaigns/[campaignId]/edit` avaient ete visuellement ameliores, mais ils affichaient encore beaucoup de texte en anglais dans les titres, descriptions, aides, etats de chargement, toasts et composants embarques.
- **Modifications effectuees :**
    - Francisation de `ui/src/app/campaigns/new/page.tsx` : titres, descriptions, placeholders, aides `FieldHelp`, messages de validation, toasts et panneau recapitulatif.
    - Francisation de `ui/src/app/campaigns/[campaignId]/edit/page.tsx` : en-tete, libelles, toasts, messages d'erreur et actions de formulaire.
    - Francisation de `ui/src/app/campaigns/CsvUploadSelector.tsx` et `ui/src/app/campaigns/ManualPhoneNumbersTable.tsx` pour eliminer les textes anglais encore visibles dans le parcours.
- **Decisions Techniques :** J'ai cible uniquement la copie visible cote client sur le flux creation/edition, sans modifier les contrats API ni la logique metier, afin d'ameliorer l'experience percue avec un risque minimal.
- **Impacts & Dependances :** Fichiers touches : `ui/src/app/campaigns/new/page.tsx`, `ui/src/app/campaigns/[campaignId]/edit/page.tsx`, `ui/src/app/campaigns/CsvUploadSelector.tsx`, `ui/src/app/campaigns/ManualPhoneNumbersTable.tsx`, `ENGINEERING_LOG.md`. Effet attendu : parcours campagne plus coherent, plus premium et integralement comprensible en francais.
- **Prochaines etapes :** Si besoin, etendre la meme passe de francisation a `campaigns/[campaignId]` qui contient encore de nombreux libelles et toasts en anglais.

### [2026-07-05T10:18:49Z] | Finition des aides et actions sur creation et edition de campagne
- **Contexte :** La page `campaigns/new` contenait encore un bloc visible `No CSV file?` dans l'onglet de saisie manuelle, alors que le produit adopte deja un pattern d'aide discret par point d'interrogation. L'utilisateur a aussi demande la meme passe de finition sur `campaigns/[campaignId]/edit`.
- **Modifications effectuees :**
    - Suppression du bloc visible d'aide dans l'onglet `Manual entry` de `ui/src/app/campaigns/new/page.tsx` et remplacement par un `FieldHelp` discret.
    - Ajout d'un `FieldHelp` sur le champ `Campaign Name` dans `ui/src/app/campaigns/[campaignId]/edit/page.tsx`.
    - Realignement des actions de bas de formulaire a droite sur l'ecran d'edition, comme sur la creation.
- **Decisions Techniques :** J'ai conserve une retouche minimale et coherente avec le pattern deja applique dans l'application : aide au survol seulement quand l'information n'a pas besoin d'etre visible en permanence, et footer d'actions aligne sur l'usage principal.
- **Impacts & Dependances :** Fichiers touches : `ui/src/app/campaigns/new/page.tsx`, `ui/src/app/campaigns/[campaignId]/edit/page.tsx`, `ENGINEERING_LOG.md`. Effet attendu : formulaires plus legers visuellement et meilleure coherence entre creation et edition.
- **Prochaines etapes :** Si besoin, harmoniser ensuite la copie anglaise restante sur ces pages pour les aligner completement avec le reste de l'UI deja francisee.

### [2026-07-05T09:57:27Z] | Refonte de la page detail campagne
- **Contexte :** Apres l'amelioration de `/campaigns/new`, la page `/campaigns/[campaignId]` restait trop brute et n'exposait pas clairement la source importee, le nombre de contacts, la progression et la lecture rapide du lancement.
- **Modifications effectuees :**
    - Refonte de `ui/src/app/campaigns/[campaignId]/page.tsx` avec `PageShell` / `PageHeader`, cartes de synthese et disposition plus lisible.
    - Ajout de cartes KPI pour les contacts, l'execution, les echecs et le succes courant.
    - Clarification de la zone `Campaign Details` avec `Source Mode`, `Source File`, `Source Key`, progression et compteurs de lignes traitées / en echec.
    - Ajout d'un panneau lateral `Execution Snapshot` avec workflow, import source, telephonie et barre de progression.
    - Detection heuristique du mode d'entree `Manual entry converted to CSV` pour les campagnes creees depuis la nouvelle saisie manuelle, sans introduire de changement backend.
- **Decisions Techniques :** Je n'ai pas change le contrat API. Le detail campagne reutilise strictement les donnees existantes, avec une heuristique sur le nom de fichier pour identifier les imports generes depuis la saisie manuelle. Cela ameliore fortement l'UX sans migration de schema ni divergence de source de verite.
- **Impacts & Dependances :** Fichier touche : `ui/src/app/campaigns/[campaignId]/page.tsx`, `ENGINEERING_LOG.md`. Validation effectuee : diagnostics IDE OK, `npx tsc --noEmit` OK.
- **Prochaines etapes :** Si on veut fiabiliser totalement l'affichage du mode d'entree, ajouter plus tard un metadata explicite du type de source dans la campagne ou dans la source stockee.

### [2026-07-05T09:48:11Z] | Refonte UX de creation de campagne avec saisie manuelle des numeros
- **Contexte :** La page `/campaigns/new` etait tres basique et n'acceptait qu'un fichier CSV deja prepare. Le besoin etait d'ameliorer nettement l'UX et de permettre au client de saisir ses numeros manuellement s'il n'a pas de CSV.
- **Modifications effectuees :**
    - Refonte visuelle de `ui/src/app/campaigns/new/page.tsx` avec une structure plus claire (`PageShell`, cartes separees, panneau recapitulatif).
    - Remplacement du select de source par des onglets `CSV file` / `Manual entry`.
    - Ajout du composant `ui/src/app/campaigns/ManualPhoneNumbersTable.tsx` avec table de numeros, bouton `Add number`, suppression de ligne et compteur de lignes remplies.
    - Ajout du helper partage `ui/src/app/campaigns/sourceUpload.ts` pour centraliser l'upload des sources campagne vers S3/MinIO.
    - Modernisation de `ui/src/app/campaigns/CsvUploadSelector.tsx` pour aligner l'apparence sur la nouvelle page.
    - Implementation d'une generation CSV cote navigateur pour la saisie manuelle, avec validation defensive des numeros avant upload puis reutilisation du flux backend existant `source_type=csv`.
- **Decisions Techniques :** Je n'ai pas ajoute de nouvelle API pour la saisie manuelle. Le frontend convertit les numeros saisis en CSV local puis reutilise le pipeline securise deja existant (presigned upload + validation backend CSV). Cela evite une seconde voie de creation de source plus fragile, garde une seule surface de traitement cote serveur et preserve l'isolement des droits de stockage.
- **Impacts & Dependances :** Fichiers touches : `ui/src/app/campaigns/new/page.tsx`, `ui/src/app/campaigns/CsvUploadSelector.tsx`, `ui/src/app/campaigns/ManualPhoneNumbersTable.tsx`, `ui/src/app/campaigns/sourceUpload.ts`, `ENGINEERING_LOG.md`. Validation effectuee : diagnostics IDE OK, `npx tsc --noEmit` OK.
- **Prochaines etapes :** Verifier visuellement la page `/campaigns/new` en local et tester les deux chemins de creation (CSV et saisie manuelle) avec un workflow et une config telephonie reellement selectionnes.

### [2026-07-05T09:08:06Z] | Demarrage backend dev debloque par allowlist CORS explicite
- **Contexte :** `./scripts/start_services_dev.sh` restait bloque au healthcheck `uvicorn` en local. Le backend plantait a l'import de `api/app.py` parce que `DEPLOYMENT_MODE="saas"` etait actif sans `CORS_ALLOWED_ORIGINS`, ce qui est volontairement refuse pour eviter un mode credentialed trop permissif.
- **Modifications effectuees :**
    - Ajout d'une allowlist locale explicite dans `api/.env` pour `http://localhost:3000` et `http://127.0.0.1:3000`.
    - Documentation de `CORS_ALLOWED_ORIGINS` dans `api/.env.example` avec un exemple de valeur de dev.
    - Redemarrage complet des services via `./scripts/stop_services.sh` puis `UVICORN_BASE_PORT=8001 ./scripts/start_services_dev.sh`.
- **Decisions Techniques :** Je n'ai pas affaibli le garde-fou `app.py` car il protege le mode SaaS contre une configuration CORS unsafe. Le bon correctif est une allowlist explicite, pas un bypass du controle. En dev, la surface d'exposition reste minimale et compatible avec les cookies/credentials du frontend local.
- **Impacts & Dependances :** Fichiers touches : `api/.env` (local), `api/.env.example`, `ENGINEERING_LOG.md`. Validation effectuee : healthcheck `http://127.0.0.1:8001/api/v1/health` OK via `start_services_dev.sh` (`✓ uvicorn healthy (attempt 2)`).
- **Prochaines etapes :** Si l'UI est ouverte sur un autre host/port, l'ajouter explicitement a `CORS_ALLOWED_ORIGINS`. Conserver `DEPLOYMENT_MODE="saas"` seulement si le comportement multi-origine credentialed est bien voulu localement.

### [2026-07-05T09:01:23Z] | Retrait de MPS du mode Bookivox managed moderne
- **Contexte :** Le produit utilise maintenant un billing local Bookivox et des providers managés pilotés par les variables backend. Le runtime moderne `Bookivox managed` ne devait plus dépendre de l'ancien protocole MPS, mais `managed_service_version=2` forçait encore une corrélation MPS meme quand la configuration compilée pointait déjà vers les providers backend réels (`openai`, `deepgram`, `elevenlabs`, etc.).
- **Modifications effectuees :**
    - Ajout de la distinction entre runtime proxy legacy `bookivox` et runtime moderne backend-managed dans `api/services/managed_model_services.py`.
    - Création des helpers `uses_legacy_bookivox_proxy_runtime(...)` et `requires_mps_correlation(...)`.
    - Mise à jour de `ensure_mps_correlation_id(...)` pour n'exiger une corrélation MPS que pour les configurations v2 qui utilisent encore explicitement le provider proxy `bookivox`.
    - Mise à jour de `api/services/quota_service.py` pour ne plus appeler `mps_service_key_client` dans le mode Bookivox managed moderne.
    - Ajout d'un nouveau fichier de tests `api/tests/test_managed_model_services.py` et adaptation de `api/tests/test_quota_service.py` pour verrouiller les deux chemins: moderne sans MPS, legacy avec MPS.
- **Decisions Techniques :** Le bon découpage d'architecture est désormais: billing local Bookivox + runtime backend-managed local pour le mode moderne, avec MPS conservé seulement comme compatibilité legacy quand une config utilise encore explicitement le provider proxy `bookivox` / une `mps_sk`. Cette séparation réduit le couplage, supprime une dépendance externe dans le chemin critique et évite de bloquer les tests/appels quand les secrets MPS ne sont pas présents alors qu'ils ne devraient plus être requis.
- **Impacts & Dependances :** Fichiers touchés : `api/services/managed_model_services.py`, `api/services/quota_service.py`, `api/tests/test_quota_service.py`, `api/tests/test_managed_model_services.py`, `ENGINEERING_LOG.md`. Validation effectuée : diagnostics IDE OK, `python -m pytest --noconftest api/tests/test_quota_service.py api/tests/test_managed_model_services.py` OK (`11 passed`).
- **Prochaines etapes :** Retester `Demarrer le test` et les appels voix avec la configuration backend managée actuelle. Si un flux utilise encore explicitement le provider `bookivox`, prévoir sa migration vers les providers backend réels ou le laisser documenté comme chemin legacy distinct.

### [2026-07-05T02:00:58Z] | Message d'erreur runtime managé rendu actionnable
- **Contexte :** Apres le correctif de correlation MPS, le runtime pouvait encore echouer localement avec le message generique `Could not initialize the managed runtime` quand la configuration backend manquante empechait toute autorisation MPS cote plateforme.
- **Modifications effectuees :**
    - Ajout d'un garde-fou dans `api/services/quota_service.py` pour detecter le mode Bookivox managé sans `BOOKIVOX_MPS_SECRET_KEY` ou avec `DEPLOYMENT_MODE=oss`.
    - Retour d'un message explicite `managed_runtime_not_configured` au lieu d'un echec opaque.
    - Ajout d'un test unitaire couvrant ce cas de configuration absente.
- **Decisions Techniques :** Quand la panne vient d'une variable backend manquante, renvoyer un message generique fait perdre du temps et masque la vraie surface de risque operatoire. Le nouveau message reste sobre, n'expose aucun secret, et guide directement vers la remediation minimale sans melanger cela avec la logique billing.
- **Impacts & Dependances :** Fichiers touches : `api/services/quota_service.py`, `api/tests/test_quota_service.py`, `ENGINEERING_LOG.md`. Validation effectuee : diagnostics IDE OK, `python -m pytest --noconftest api/tests/test_quota_service.py` OK (`9 passed`).
- **Prochaines etapes :** Renseigner `DEPLOYMENT_MODE=saas` et une vraie valeur `BOOKIVOX_MPS_SECRET_KEY` dans `api/.env`, puis redemarrer l'API. Pour les appels voix, verifier aussi que `MANAGED_TTS_API_KEY` n'est pas vide.

### [2026-07-05T01:44:05Z] | Runtime manage des tests agent debloque pour le mode Bookivox
- **Contexte :** Les tests agent pouvaient echouer avec `Could not initialize the managed runtime. Please try again.` meme apres recharge. La panne ne venait pas du ledger credits mais de l'etape de creation du `mps_correlation_id` avant demarrage du runtime managé.
- **Modifications effectuees :**
    - Correction de `api/services/quota_service.py` pour distinguer deux chemins de correlation MPS.
    - Conservation du bearer direct `create_correlation_id(...)` uniquement quand la configuration fournit une vraie service key `mps_sk_...`.
    - Bascule du mode Bookivox managé v2 compile en providers backend vers `authorize_workflow_run_start(...)` scope organisation avec `require_correlation_id=True`, afin de ne plus envoyer par erreur une cle LLM/TTS backend au endpoint MPS des service keys.
    - Ajout d'un test unitaire couvrant exactement le cas `bookivox managed backend v2` ou la config contient des cles provider backend et doit quand meme obtenir une correlation id valide.
- **Decisions Techniques :** Le runtime managé Bookivox ne doit jamais reutiliser une cle provider backend comme si c'etait une service key MPS. C'etait a la fois une cause de panne et une mauvaise separation de responsabilites. Le nouveau flux applique le moindre privilege: les vraies `mps_sk` restent sur le bearer endpoint, tandis que le mode managé plateforme utilise l'autorisation org-side deja prevue pour le SaaS.
- **Impacts & Dependances :** Fichiers touches : `api/services/quota_service.py`, `api/tests/test_quota_service.py`, `ENGINEERING_LOG.md`. Validation effectuee : diagnostics IDE OK, `python -m pytest --noconftest api/tests/test_quota_service.py` OK (`8 passed`).
- **Prochaines etapes :** Retester `Test Chat` et `Test Audio`. Si l'erreur persiste encore apres ce fix, verifier alors uniquement la presence des variables runtime MPS cote backend (`BOOKIVOX_MPS_SECRET_KEY`, `MPS_API_URL`) et les logs de reponse MPS, car le bug de selection de cle est maintenant neutralise.

### [2026-07-05T01:35:00Z] | Retrait du bloc abonnement mensuel du dashboard billing
- **Contexte :** Le dashboard billing affichait encore un bloc `Abonnement mensuel` que l'utilisateur ne souhaite plus voir dans la vue principale.
- **Modifications effectuees :**
    - Suppression du panneau visuel `Abonnement mensuel` dans `ui/src/app/billing/page.tsx`.
    - Conservation du bouton global `Gerer l'abonnement` et des donnees Stripe associees pour ne pas casser la gestion recurrente.
- **Decisions Techniques :** J'ai retire uniquement le bloc de presentation redondant sans toucher a la logique Stripe ni au resume de cycle, afin d'eviter une regression fonctionnelle tout en simplifiant l'interface comme demande.
- **Impacts & Dependances :** Fichiers touches : `ui/src/app/billing/page.tsx`, `ENGINEERING_LOG.md`. Validation effectuee : diagnostics IDE OK, `npx tsc --noEmit` OK.
- **Prochaines etapes :** Si besoin UX, remplacer plus tard la mention d'abonnement restante dans le cycle de facturation par un libelle encore plus discret.

### [2026-07-05T01:26:17Z] | Solde billing aligne sur le vrai solde compte
- **Contexte :** Le `Solde disponible` ne se mettait pas a jour apres une recharge Stripe alors que le ledger local enregistrait bien un solde cumule dans `cached_balance_credits`. La cause racine etait un glissement semantique introduit avec la vue mensuelle: le dashboard retournait le net de la periode courante comme `remaining_credits`, ce qui melangeait "solde disponible du compte" et "activite du mois".
- **Modifications effectuees :**
    - Correction de `get_billing_dashboard(...)` pour exposer `remaining_credits` a partir de `account.cached_balance_credits` au lieu de `period_summary["net_credits"]`.
    - Conservation du resume de periode pour `total_credits_used` et `total_quota`, afin de garder la lecture mensuelle des usages sans perdre le vrai solde rechargeable.
    - Ajustement de `ui/src/app/billing/page.tsx` pour calculer la jauge d'utilisation a partir des credits octroyes sur la periode (`total_quota`) plutot que d'additionner un solde cumule avec une consommation mensuelle.
    - Mise a jour des tests `api/tests/test_billing_service.py` pour verrouiller la distinction entre solde compte et resume mensuel, et isolation d'un test existant qui laissait partir une lecture DB reelle.
- **Decisions Techniques :** Le solde disponible doit etre la verite comptable cumulée du tenant, sinon un client peut payer et voir un montant stale apres refresh, ce qui casse la confiance produit. J'ai garde la notion de periode uniquement pour l'analyse d'usage, afin d'eviter une regression sur la facturation mensuelle tout en restaurant une UX coherent. Cette separation reduit aussi le risque d'abus produit ou de support inutile lie a des soldes apparemment faux.
- **Impacts & Dependances :** Fichiers touches : `api/services/billing.py`, `api/tests/test_billing_service.py`, `ui/src/app/billing/page.tsx`, `ENGINEERING_LOG.md`. Validations effectuees : diagnostics IDE OK, `npx tsc --noEmit` OK, `python -m pytest --noconftest api/tests/test_billing_service.py` OK (`10 passed`). Le repo ne contient pas actuellement `api/.env.test`, donc la validation pytest a ete executee en mode unitaire isole sans `conftest`.
- **Prochaines etapes :** Rejouer un abonnement Stripe test ou rouvrir `/billing` sur un compte deja recharge pour verifier visuellement que `Solde disponible` suit bien le `cached_balance_credits`. Si besoin UX, renommer plus tard les blocs de periode pour rendre explicite la distinction entre "solde compte" et "usage du mois".

### [2026-07-05T03:16:00Z] | Credit initial d'abonnement Stripe fiabilise et montant EUR retire de l'UI
- **Contexte :** Un abonnement mensuel Stripe pouvait apparaître actif dans l'UI sans que le solde de credits soit immediatement augmente. En pratique, l'UI lisait bien l'etat de l'abonnement depuis Stripe, mais le credit initial dependait uniquement de `invoice.paid`, ce qui laissait un trou si l'evenement arrivait en retard, manquait dans la selection webhook ou n'avait pas encore ete traite. L'UI affichait aussi un montant en EUR dans le panneau d'abonnement alors que la consigne produit est d'exposer les usages en credits.
- **Modifications effectuees :**
    - Ajout d'un fallback sur `checkout.session.completed` pour les subscriptions payees avec invoice associee, afin de crediter immediatement le premier cycle sans attendre un second passage.
    - Ajout d'une reconciliation defensive `reconcile_subscription_invoice_credits(...)` appelee depuis le dashboard afin de backfiller les invoices Stripe payees ratees par les webhooks, avec idempotence par invoice Stripe.
    - Centralisation de l'octroi recurrent dans `_grant_subscription_invoice_credits(...)` pour que `checkout.session.completed`, `invoice.paid` et la reconciliation utilisent exactement la meme logique et les memes cles d'idempotence.
    - Suppression de l'affichage du montant EUR dans le bloc `Abonnement mensuel` de l'UI, qui ne montre plus que les credits ajoutes chaque mois.
    - Ajout de tests couvrant le credit initial depuis `checkout.session.completed` et le backfill des invoices payees.
- **Decisions Techniques :** La source de verite reste Stripe pour l'etat de l'abonnement, mais j'ai ajoute une defense en profondeur cote Bookivox pour ne pas dependre d'un unique evenement webhook pour le premier mois. L'idempotence sur `stripe_invoice_paid:{invoice_id}` empeche les doubles credits meme si Stripe renvoie `checkout.session.completed`, `invoice.paid` et si la reconciliation repasse ensuite.
- **Impacts & Dependances :** Fichiers touches : `api/services/billing.py`, `api/tests/test_billing_service.py`, `ui/src/app/billing/page.tsx`, `ENGINEERING_LOG.md`. Validations effectuees : diagnostics IDE OK, `py_compile` cible OK, `pytest api/tests/test_billing_service.py` OK (`10 passed`).
- **Prochaines etapes :** Recharger `/billing` avec le webhook Stripe configure pour verifier que le solde se met bien a jour des le premier abonnement. Si un abonnement test existe deja sans credit associe, rouvrir la page billing pour laisser la reconciliation backfiller l'invoice payee.

### [2026-07-05T01:48:00Z] | Variables Stripe explicites dans api/.env
- **Contexte :** Le backend Stripe etait code et valide, mais `api/.env` ne contenait pas encore explicitement les cles Stripe a l'emplacement pointe par l'operateur. Cela rendait la configuration moins lisible et augmentait le risque d'oublier une variable necessaire lors du demarrage local ou en recette.
- **Modifications effectuees :**
    - Ajout de `STRIPE_SECRET_KEY`, `STRIPE_WEBHOOK_SECRET` et `STRIPE_CURRENCY` dans `api/.env`.
    - Valeurs sensibles laissees vides par defaut pour eviter d'injecter de faux secrets et garder un echec explicite tant que Stripe n'est pas configure.
    - Devise par defaut fixee a `EUR`, ce qui correspond a la grille de credits actuelle.
- **Decisions Techniques :** J'ai prefere des variables presentes mais vides plutot que des commentaires seuls, parce que cela documente clairement la surface de configuration attendue tout en gardant le backend dans un mode safe-fail : sans vraies cles, les endpoints Stripe refusent proprement l'operation au lieu de tenter un paiement partiellement configure.
- **Impacts & Dependances :** Fichiers touches : `api/.env`, `ENGINEERING_LOG.md`. Aucun impact runtime tant que les vraies valeurs Stripe ne sont pas renseignees.
- **Prochaines etapes :** Renseigner les vraies valeurs `sk_test_...` / `whsec_...` ou `sk_live_...` / `whsec_...` selon l'environnement, puis rejouer un achat one-shot et un abonnement mensuel en sandbox.

### [2026-07-05T10:11:19Z] | Nettoyage des aides inline sur la creation de campagne
- **Contexte :** La page `ui/src/app/campaigns/new/page.tsx` etait deja visuellement propre, mais plusieurs champs affichaient encore des textes d'aide sous les inputs, ce qui etait moins coherent avec le pattern `?` deja adopte ailleurs dans l'UI. Les actions de bas de formulaire etaient egalement alignees a gauche.
- **Modifications effectuees :**
    - Ajout de `FieldHelp` sur les champs `Campaign Name`, `Workflow` et `Telephony Configuration`.
    - Suppression des paragraphes d'aide inline situes sous ces champs.
    - Realignement des boutons de bas de formulaire sur la droite avec l'ordre secondaire puis primaire.
- **Decisions Techniques :** J'ai reutilise le composant `FieldHelp` existant pour garder une experience uniforme et eviter d'introduire un nouveau pattern local dans un formulaire deja stable.
- **Impacts & Dependances :** Fichiers touches : `ui/src/app/campaigns/new/page.tsx`, `ENGINEERING_LOG.md`. Effet attendu : formulaire plus compact, plus coherent avec le reste de l'application et footer d'actions plus propre visuellement.
- **Prochaines etapes :** Si besoin, appliquer le meme nettoyage aux autres formulaires de creation ou d'edition de campagnes encore en copie anglaise ou avec aides inline residuelles.

### [2026-07-05T01:40:00Z] | Debit credits sur les tests d'agent, y compris le test chat manuel
- **Contexte :** Le produit doit consommer des credits meme pendant les tests d'agent. Le flux audio etait deja branche via la completion classique des workflow runs, mais le `Test Chat` manuel executait des tours texte sans passer par le point de debit du ledger local.
- **Modifications effectuees :**
    - Ajout d'un resume billing par `workflow_run_id` dans `api/db/billing_client.py` pour pouvoir recalculer un total facture et un breakdown incremental par run.
    - Ajout de `bill_text_chat_turn_usage(...)` dans `api/services/billing.py` pour debiter un tour texte confirme, avec idempotence par `workflow_run_id + turn_id + metric_code`.
    - Branchement du debit juste apres la persistance reussie du tour assistant dans `api/services/workflow/text_chat_session_service.py`, ce qui garantit que seuls les tours completes sont factures.
    - La facturation texte est incrementale et ne repasse pas par la logique "fin d'appel", ce qui evite les trous de facturation sur les sessions texte longues ou jamais explicitement "terminees".
    - Ajout de tests pour verifier le debit incremental des tours texte et l'appel effectif du helper de billing apres execution d'un tour manuel.
- **Decisions Techniques :** J'ai choisi une facturation incremental par tour pour `TEXTCHAT` plutot qu'une facturation en fin de run, car un chat manuel n'a pas de vraie notion fiable de "call completed". Ce choix est plus robuste contre les abandons de session, evite les credits fantomes et reduit le risque de non-facturation des usages de test. L'idempotence par tour protege contre les retries HTTP et les conflits de revision.
- **Impacts & Dependances :** Fichiers touches : `api/db/billing_client.py`, `api/services/billing.py`, `api/services/workflow/text_chat_session_service.py`, `api/tests/test_billing_service.py`, `api/tests/test_text_chat_session_service.py`, `ENGINEERING_LOG.md`. Validations effectuees : `py_compile` cible OK, `pytest api/tests/test_billing_service.py api/tests/test_text_chat_session_service.py api/tests/test_quota_service.py api/tests/test_workflow_run_billing.py` OK (`24 passed`).
- **Prochaines etapes :** Si besoin UX, exposer dans l'UI du tester un micro-indicateur "les tests consomment des credits" pour eviter toute surprise produit. Cote Stripe sandbox, confirmer qu'un run de test long + un renouvellement mensuel de credits ne laissent jamais passer un start sans debit ni quota check.

### [2026-07-05T01:30:00Z] | Stripe recurrent propre via subscription, invoice.paid et customer portal
- **Contexte :** Le flux Stripe existant etait encore un top-up ponctuel (`mode=payment`) alors que le produit demande aussi un renouvellement mensuel propre. Il fallait aligner l'implementation sur les patterns officiels Stripe pour les recurring payments, avec une vraie subscription, des webhooks de facturation et un portail client.
- **Modifications effectuees :**
    - Lecture et verification des patterns officiels Stripe pour Checkout subscriptions, `invoice.paid`, `customer.subscription.*` et le Customer Portal.
    - Ajout de la creation/reutilisation d'un `stripe_customer_id` par organisation dans le billing local pour lier le compte client Bookivox a Stripe sans melanger les tenants.
    - Extension de `create_credit_checkout_session(...)` pour supporter `auto_renew=True` et creer un Checkout Session en `mode="subscription"` avec metadata d'organisation et de credits mensuels.
    - Changement du webhook Stripe : les achats one-shot restent credites sur `checkout.session.completed`, tandis que les abonnements mensuels sont credites sur `invoice.paid` avec idempotence par invoice Stripe.
    - Ajout d'un endpoint de Customer Portal Stripe pour laisser le client gerer son abonnement recurrent sans back-office maison fragile.
    - Exposition dans `/billing` d'un switch `Renouvellement mensuel`, d'un resume d'abonnement actif et d'un bouton `Gerer Stripe`.
- **Decisions Techniques :** J'ai volontairement separe one-shot et recurrent au niveau webhook, car Stripe recommande de piloter les subscriptions avec les evenements d'invoice et de subscription plutot qu'avec le simple succes Checkout. Cela reduit le risque de double-credit, gere correctement les renouvellements futurs et garde la logique d'octroi sur un signal de paiement fiable (`invoice.paid`).
- **Impacts & Dependances :** Fichiers touches : `api/db/billing_client.py`, `api/services/billing.py`, `api/routes/organization_usage.py`, `api/tests/test_billing_service.py`, `ui/src/app/billing/page.tsx`, `ui/src/client/*`, `ENGINEERING_LOG.md`. Validations effectuees : `py_compile` cible OK, `npm exec -- tsc --noEmit` OK, `pytest api/tests/test_billing_service.py api/tests/test_quota_service.py api/tests/test_workflow_run_billing.py` OK (`16 passed`).
- **Prochaines etapes :** Verifier dans Stripe Dashboard que le Customer Portal est active et que le webhook Stripe ecoute au minimum `checkout.session.completed`, `checkout.session.expired`, `invoice.paid`, `invoice.payment_failed`, `customer.subscription.updated` et `customer.subscription.deleted`. Tester ensuite un cycle sandbox complet de souscription, renouvellement, echec de paiement et cancel via portal.

### [2026-07-05T01:20:00Z] | Gestion inline des supplements billing depuis /billing
- **Contexte :** L'UX billing demandait encore un detour par `Settings` pour activer les deux seuls supplements manuels restants (`extra_concurrent_calls` et `extra_campaigns`). L'objectif etait de rendre cette action faisable directement dans `/billing`, sans doubler la logique metier ni introduire une seconde source de verite.
- **Modifications effectuees :**
    - Ajout d'une section `Supplements` dans `ui/src/app/billing/page.tsx` avec switches inline, badges `Actif/Inactif` et sauvegarde immediate.
    - Reutilisation des endpoints existants `GET/PUT /api/v1/organizations/preferences` pour lire et persister `billing_feature_flags`, au lieu de creer un endpoint billing specifique.
    - Synchronisation locale du state billing apres sauvegarde pour reflecter immediatement l'etat des flags dans `pricing.feature_flags`, `concurrent_calls.enabled` et `campaigns.enabled`.
    - Conservation des tooltips courts sur les deux supplements afin de garder l'ecran lisible sans texte long.
- **Decisions Techniques :** J'ai volontairement branche `/billing` sur les preferences d'organisation deja existantes afin d'eviter des divergences entre `Settings` et `Billing`. Cette approche preserve le least surprise pour l'equipe, garde une seule source de verite et limite le risque de drift entre deux modeles de configuration.
- **Impacts & Dependances :** Fichier principal touche : `ui/src/app/billing/page.tsx`. Validation effectuee : diagnostics IDE OK sur le fichier modifie, `npm exec -- tsc --noEmit` OK.
- **Prochaines etapes :** Si l'usage le justifie, factoriser cette mini section inline dans un composant reutilisable partage entre `Settings` et `/billing` pour ne pas dupliquer le rendu des deux switches.

### [2026-07-05T00:55:00Z] | Regles mensuelles credits, minimum de recharge et campagnes supplementaires
- **Contexte :** Le produit doit maintenant presenter les montants client en credits, limiter la recharge Stripe a un minimum de 29 EUR, considerer les credits comme valables sur le cycle mensuel en cours, offrir 2 campagnes gratuites puis facturer les suivantes, et ne debiter les add-ons qu'apres activation manuelle dans les parametres d'organisation.
- **Modifications effectuees :**
    - Passage du dashboard et du controle de quota a un calcul sur la periode mensuelle courante via un resume ledger borne au mois actif, ce qui fait disparaitre le solde exploitable du mois precedent sans casser l'historique complet du ledger.
    - Ajout d'un resume DB par periode dans `api/db/billing_client.py` et filtrage du ledger mensuel retourne par `get_billing_dashboard`.
    - Mise a jour des regles pricing backend : minimum Stripe a `2900` centimes / `2900` credits, bloc campagnes remplace par `2 gratuites puis 1500 credits par campagne supplementaire et par mois`, facturation automatique des numeros Bookivox geres, facturation automatique du stockage recordings/transcripts et debit embedding sans opt-in artificiel.
    - Conservation d'une activation manuelle uniquement pour les vrais supplements restants : slots de concurrence au-dela des 10 inclus et campagnes supplementaires au-dela des 2 incluses.
    - Extension des preferences d'organisation avec `billing_feature_flags` pour exposer ces toggles dans `Settings`, et fallback backend sur `ORGANIZATION_PREFERENCES` pour garder une lecture robuste.
    - Rebranchement de `ui/src/app/billing/page.tsx` pour afficher la grille en credits, la periode mensuelle, le nouveau minimum de recharge, des lignes de pricing plus courtes et des tooltips d'explication.
    - Ajout / mise a jour des tests `api/tests/test_billing_service.py` pour couvrir minimum Stripe, resume mensuel, campagnes gratuites puis payantes, facturation des seuls numeros Bookivox geres et prelevement automatique du stockage.
- **Decisions Techniques :** J'ai volontairement garde Stripe en paiement ponctuel et fait porter la validite sur le cycle mensuel calcule par le ledger local, car cela respecte la contrainte produit sans introduire dans l'urgence une couche abonnement Stripe plus lourde, plus risquee et plus difficile a securiser. Les seuls supplements opt-in restent `extra_concurrent_calls` et `extra_campaigns`, ce qui evite une surfacturation implicite tout en laissant les couts intrinsiques (numero Bookivox, stockage, embedding) se debiter automatiquement quand le client utilise la fonctionnalite. L'affichage client est converti en credits partout sauf sur l'action de recharge Stripe, seule zone ou l'EUR reste necessaire.
- **Impacts & Dependances :** Fichiers touches : `api/enums.py`, `api/schemas/organization_preferences.py`, `api/db/billing_client.py`, `api/services/billing.py`, `api/routes/organization_usage.py`, `api/tests/test_billing_service.py`, `ui/src/app/billing/page.tsx`, `ui/src/components/OrganizationPreferencesSection.tsx`, `ui/src/client/*`, `ENGINEERING_LOG.md`. Validations effectuees : regeneration OpenAPI OK, `py_compile` cible OK, `npm exec -- tsc --noEmit` OK, `pytest api/tests/test_billing_service.py api/tests/test_quota_service.py api/tests/test_workflow_run_billing.py` OK (`14 passed`).
- **Prochaines etapes :** Si un vrai auto-renouvellement Stripe mensuel devient obligatoire, introduire ensuite un flux abonnement Stripe dedie avec webhook `invoice.paid`, gestion du cancel et garde-fous de renouvellement. Sur la partie UX, surveiller simplement si les tooltips billing doivent aussi etre repris sur d'autres vues comme `usage` ou `run details`.

### [2026-07-04T22:35:00Z] | Facturation locale Stripe, ledger client et garde-fous de concurrence
- **Contexte :** L'utilisateur veut sortir de la facturation MPS Bookivox pour passer sur un billing Bookivox local, lie au compte client, avec 10 credits offerts a la creation, achat de credits via Stripe, tarification par defaut commune a tous les comptes et verifications de concurrence avant decrocher/appeler. La phase en cours avait pose l'essentiel du backend mais la chaine n'etait pas encore exploitable de bout en bout.
- **Modifications effectuees :**
    - Finalisation du socle billing local backend : compte billing par organisation, ledger credits, sessions checkout Stripe, evenements webhook idempotents, debit local par usage et par recurrent.
    - Correction du schema SQLAlchemy des nouveaux modeles billing en renommant les attributs ORM reserves `metadata` vers `metadata_json` tout en conservant la colonne SQL `metadata`, ce qui restaure l'import de l'app et la generation OpenAPI.
    - Regeneration du client OpenAPI frontend a partir du schema local de l'application apres ajout du nouvel endpoint `POST /organizations/billing/credits/checkout-session`.
    - Rebranchement de `ui/src/app/billing/page.tsx` sur le billing local : lecture du solde/ledger/pricing, affichage de la grille tarifaire, choix de montant, creation de session Stripe et redirection checkout.
    - Mise a jour des tests `api/tests/test_workflow_run_billing.py` et `api/tests/test_quota_service.py` pour couvrir la logique actuelle : ledger local comme source de verite, credits insuffisants, creation de correlation managed v2, rejet cross-org.
    - Application locale de la migration Alembic `c1a9e7b4d5f2_add_local_billing_tables.py`.
- **Decisions Techniques :** Le ledger Bookivox est la seule source de verite client pour les credits afin d'eviter une dependance produit au billing MPS. Stripe reste limite a l'encaissement prepayé; l'octroi de credits passe ensuite par le webhook signe et idempotent. Le compte billing reste scope organisation pour eviter tout melange inter-tenant. La concurrence continue d'etre gatee avant initiation/decroche pour bloquer le cout et la saturation en amont.
- **Impacts & Dependances :** Fichiers touches : `api/db/models.py`, `api/db/billing_client.py`, `api/services/billing.py`, `api/routes/organization_usage.py`, `api/services/quota_service.py`, `api/routes/telephony.py`, `api/services/telephony/status_processor.py`, `api/tasks/knowledge_base_processing.py`, `api/services/workflow_run_billing.py`, `api/tests/test_quota_service.py`, `api/tests/test_workflow_run_billing.py`, `ui/src/app/billing/page.tsx`, `ui/src/client/*`, `ENGINEERING_LOG.md`. Validations effectuees : import OpenAPI local OK, `npm exec -- tsc --noEmit` OK, `py_compile` cible OK, `pytest api/tests/test_workflow_run_billing.py api/tests/test_quota_service.py` OK, migration Alembic appliquee.
- **Prochaines etapes :** Configurer en exploitation les secrets Stripe definitifs puis tester le webhook Stripe en bout-en-bout avec une vraie session de paiement. Ajouter ensuite, si besoin commercial, un back-office d'override de tarification par organisation et un job planifie de reconciliation mensuelle si l'on veut sortir totalement de la reconciliation lazy a la lecture.

### [2026-07-04T03:25:00Z] | Correction correlation id managed v2 et test chat manuel uniquement
- **Contexte :** Les appels navigateur et le `Test Chat` pouvaient echouer avec `Managed model services v2 requires workflow run authorization before the run starts. Missing correlation id...`. En `oss`, le backend ne creait le `mps_correlation_id` que quand des anciennes cles `bookivox` etaient presentes, ce qui cassait les runs managés v2 backend-owned. En parallele, l'utilisateur ne voulait garder que le mode manuel dans le test chat.
- **Modifications effectuees :**
    - Deplacement de l'autorisation OSS `managed v2` pour qu'elle s'execute avant le fallback legacy base sur `_bookivox_api_keys`, afin de toujours creer et persister un `mps_correlation_id` pour les runs managés v2.
    - Ajout d'un test cible dans `api/tests/test_quota_service.py` pour couvrir le cas `managed_service_version=2` sans provider legacy `bookivox`.
    - Suppression du mode `Simulé` dans le panneau de test workflow pour ne laisser que le chat manuel.
    - Simplification de l'entete du panneau `Test Chat` autour du reset de session manuelle.
- **Decisions Techniques :** Le bon niveau de correction est l'autorisation de demarrage de run, pas une exception locale dans le runner texte ou audio. Cela preserve la meme garantie pour tous les points d'entree runtime et evite de lancer des services managés sans correlation/billing context. Le retrait du mode simule reduit une surface UI qui n'etait pas demandee et clarifie le parcours de validation produit.
- **Impacts & Dependances :** Fichiers touches : `api/services/quota_service.py`, `api/tests/test_quota_service.py`, `ui/src/app/workflow/[workflowId]/components/WorkflowTesterPanel.tsx`, `ui/src/app/workflow/[workflowId]/components/workflow-tester/shared.tsx`, `ENGINEERING_LOG.md`. Validation effectuee : `tsc --noEmit` OK, `py_compile` OK, diagnostics IDE OK. Le lancement `pytest` complet cible n'a pas ete stabilise dans cette session shell, donc la couverture verifiee reste partielle.
- **Prochaines etapes :** Retester manuellement `Test Chat` et `Test Audio` sur un workflow en mode managed. Si un echec persiste, tracer la reponse MPS de creation de correlation et verifier que la cle service resolue par la config effective correspond bien au runtime managed attendu.

### [2026-07-04T03:05:00Z] | Support des BundleSid Twilio manages pour les pays reguliers
- **Contexte :** L'achat d'un numero local FR continuait d'echouer avec l'erreur Twilio `21649` meme apres ajout d'un `AddressSid`. La documentation officielle Twilio indique qu'un `BundleSid` conforme au pays/type de numero doit aussi etre fourni au moment du provisionnement.
- **Modifications effectuees :**
    - Ajout des variables backend `MANAGED_TWILIO_BUNDLE_SID` et `MANAGED_TWILIO_BUNDLE_SIDS_JSON` dans `api/constants.py`.
    - Extension du contrat provider telephonie pour accepter un `bundle_sid` lors de l'achat d'un numero managé.
    - Mise a jour du provider Twilio pour transmettre `BundleSid` a l'API `IncomingPhoneNumbers` quand Bookivox en a un configure.
    - Factorisation cote route organisation d'un resolveur par pays reutilisable pour les `AddressSid` et `BundleSid`.
    - Documentation operateur ajoutee dans `api/.env.example` et dans `api/.env` avec un exemple de map par pays pour les bundles.
- **Decisions Techniques :** Le `BundleSid` reste strictement backend et resolu par pays afin de conserver l'isolation multi-tenant, d'eviter toute exposition des objets de conformite Twilio au client final et de permettre des regles differentes selon la geographie. La resolution a ete factorisee pour limiter la duplication et reduire le risque d'incoherence entre adresses et bundles managés.
- **Impacts & Dependances :** Fichiers touches : `api/constants.py`, `api/routes/organization.py`, `api/services/telephony/base.py`, `api/services/telephony/providers/twilio/provider.py`, `api/.env.example`, `api/.env`, `ENGINEERING_LOG.md`. Validation attendue : compilation Python des fichiers modifies, diagnostics IDE, puis retest apres ajout d'un vrai `BundleSid` et redemarrage backend.
- **Prochaines etapes :** Renseigner un vrai `MANAGED_TWILIO_BUNDLE_SIDS_JSON` pour `FR`, redemarrer le backend, puis retester l'achat. Si Twilio refuse encore, verifier que le bundle est bien approuve et qu'il correspond exactement au type `FR local` et au bon end-user.

### [2026-07-04T02:49:00Z] | Ajout du bloc AddressSid Twilio dans l'environnement local
- **Contexte :** Le support backend des `AddressSid` managés etait en place, mais l'operateur n'avait pas encore les variables correspondantes sous la main dans `api/.env` pour renseigner rapidement les pays reguliers.
- **Modifications effectuees :**
    - Ajout dans `api/.env` des variables `MANAGED_TWILIO_ADDRESS_SID` et `MANAGED_TWILIO_ADDRESS_SIDS_JSON` sous les credentials Twilio managés.
    - Ajout d'exemples commentés prets a remplir pour un fallback global ou une map par pays.
- **Decisions Techniques :** Les exemples restent commentés pour eviter d'injecter par erreur un mauvais `AddressSid` en production ou en local. La map par pays reste la forme recommandee car elle laisse un controle fin sur la conformite telephonique par geographie.
- **Impacts & Dependances :** Fichiers touches : `api/.env`, `ENGINEERING_LOG.md`. Aucun impact runtime tant que les valeurs restent commentées et que le backend n'est pas redemarré avec de nouvelles valeurs.
- **Prochaines etapes :** Remplacer les placeholders `AD...` par les vrais `AddressSid` Twilio Bookivox pour les pays vises, puis redemarrer le backend et retester l'achat.

### [2026-07-04T02:44:00Z] | Support des AddressSid Twilio manages pour les pays reguliers
- **Contexte :** Meme apres avoir filtre les numeros sans exigence d'adresse, certains pays ne proposaient aucun numero achetable dans le flux `Bookivox Number`. Le backend devait pouvoir acheter des numeros regules sans exposer au client les notions Twilio `AddressSid` ou les contraintes de conformite.
- **Modifications effectuees :**
    - Ajout de nouvelles variables d'environnement backend `MANAGED_TWILIO_ADDRESS_SID` et `MANAGED_TWILIO_ADDRESS_SIDS_JSON`.
    - Resolution backend d'un `AddressSid` Bookivox par pays au moment de l'achat d'un numero managé.
    - Extension du contrat provider pour autoriser la recherche/achat avec un `managed_address_sid`/`address_sid`.
    - Mise a jour du provider Twilio pour accepter les numeros `none`, `any` et `local` quand une adresse managée existe, puis transmettre `AddressSid` a l'API Twilio lors du provisionnement.
    - Documentation operateur ajoutee dans `api/.env.example` pour la configuration des adresses managées.
- **Decisions Techniques :** La configuration d'adresse reste strictement backend afin de ne pas exposer des identifiants critiques ni des details de conformite Twilio au client final. Une map par pays est privilegiee sur une selection automatique d'adresses depuis le compte partage, afin d'eviter toute confusion multi-tenant et de garder la maitrise juridique/operationnelle par pays.
- **Impacts & Dependances :** Fichiers touches : `api/constants.py`, `api/routes/organization.py`, `api/services/telephony/base.py`, `api/services/telephony/providers/twilio/provider.py`, `api/.env.example`, `ENGINEERING_LOG.md`. Validation attendue : diagnostics IDE et compilation Python sur les fichiers modifies.
- **Prochaines etapes :** Renseigner dans `api/.env` un `AddressSid` Twilio Bookivox pour les pays vises, redemarrer le backend, puis retester l'achat managé sur ces pays reguliers.

### [2026-07-04T02:36:00Z] | Filtrage des numeros Twilio avec exigence d'adresse dans le flux Bookivox
- **Contexte :** Le flux `Acheter un numéro` restait trop brut pour le mode managé : certains numéros remontés par l'API Twilio exigeaient un `AddressSid`, ce qui provoquait l'erreur `21631` alors que l'UX Bookivox ne doit ni exposer la complexité réglementaire Twilio ni demander des détails d'adresse au client final.
- **Modifications effectuees :**
    - Elargissement de la recherche Twilio locale a plusieurs candidats au lieu de ne prendre que le premier résultat.
    - Filtrage backend des numéros pour ne conserver, dans le flux Bookivox, que ceux dont `address_requirements/addressRequirements == none`.
    - Retour d'une erreur explicite `409` lorsqu'aucun numéro achetable sans adresse n'est disponible pour le pays demandé.
- **Decisions Techniques :** Twilio documente que les numéros disponibles exposent leur niveau `addressRequirements` et que l'erreur `21631` survient lorsqu'un `AddressSid` obligatoire n'est pas fourni. Pour préserver la simplicité produit et l'isolation multi-tenant, il est plus sûr d'écarter ces numéros du flux managé que de collecter ou réutiliser des adresses client dans un compte partagé.
- **Impacts & Dependances :** Fichiers touches : `api/services/telephony/providers/twilio/provider.py`, `ENGINEERING_LOG.md`. Validation effectuee : diagnostics IDE OK, `py_compile` OK. Comportement attendu : moins d'echecs Twilio `21631` dans l'achat managé, avec un fallback propre si le pays choisi ne propose que des numéros soumis a exigence d'adresse.
- **Prochaines etapes :** Si certains pays sont prioritaires commercialement mais ne proposent quasi que des numéros avec adresse, ajouter un back-office Bookivox pour preconfigurer des `AddressSid`/bundles managés par pays sans exposer cette complexité au client.

### [2026-07-04T02:25:00Z] | Garde-fou achat Twilio local et rattrapage du schema quota
- **Contexte :** L'achat de `Bookivox Number` echouait avec un faux symptome CORS. Les logs montraient en realite un `Twilio API 400` parce que `VoiceUrl` pointait vers `http://localhost:8001/...`, non acceptable pour Twilio. En parallele, les endpoints `/organizations/context` et `/user/configurations/user` plantaient car la base etait stampée sur une tete Alembic qui n'incluait pas le schema quota attendu par le code.
- **Modifications effectuees :**
    - Ajout d'une validation backend explicite qui refuse l'achat managé si l'URL webhook Bookivox n'est pas publique et en `https`, avec un message utilisateur clair au lieu d'un `500`.
    - Encapsulation des erreurs Twilio d'achat de numero en `HTTPException` lisible pour eviter les faux diagnostics CORS.
    - Ajout d'une `DialogDescription` cachee dans `PhoneNumberDialog` pour supprimer l'avertissement d'accessibilite Radix.
    - Creation d'une migration de rattrapage `b4c6d8e0f1a2_backfill_missing_quota_schema_on_head.py` afin de reintroduire sur la tete actuelle les colonnes/tables quota attendues par `OrganizationModel`.
    - Application locale de cette migration puis redemarrage complet des services sur `8001`.
- **Decisions Techniques :** En dev local, acheter un numero Twilio sans `VoiceUrl` public produirait un numero partiellement configure et fragile pour l'inbound. Le systeme refuse donc l'achat tant qu'une URL publique TLS n'est pas disponible, ce qui preserve un etat telephonie coherent et evite de facturer un numero inutilisable. Pour le schema, une migration additive sur la tete courante etait plus sure qu'un restamp manuel de la base sur une branche Alembic ancienne.
- **Impacts & Dependances :** Fichiers touches : `api/routes/organization.py`, `ui/src/components/telephony/PhoneNumberDialog.tsx`, `api/alembic/versions/b4c6d8e0f1a2_backfill_missing_quota_schema_on_head.py`, `ENGINEERING_LOG.md`. Validations effectuees : `tsc --noEmit` OK, `py_compile` OK, migration Alembic appliquee, colonne `organizations.quota_bookivox_tokens` confirmee presente, backend relance et sain sur `8001`.
- **Prochaines etapes :** Pour acheter reellement un numero Twilio, configurer `PUBLIC_BASE_URL` ou `BACKEND_API_ENDPOINT` avec une URL publique HTTPS (ou lancer un tunnel) puis retester l'achat managé.

### [2026-07-04T02:15:00Z] | Popup d'achat de numero Bookivox avec pays connu et libelle auto-genere
- **Contexte :** La popup `Acheter un numéro` demandait encore un code pays brut et un champ `Indicatif` saisi manuellement, alors que l'interface connait deja la liste des pays supportes. Le parcours restait plus technique que necessaire pour un mode telephonie entierement géré par Bookivox.
- **Modifications effectuees :**
    - Remplacement du champ texte `Pays` par un `Select` alimente a partir de `react-international-phone` et de sa liste officielle `defaultCountries`.
    - Affichage d'un champ `Indicatif` pre-rempli en lecture seule selon le pays choisi.
    - Generation automatique d'un libelle du type `Numero Bookivox France`, tout en laissant le champ librement editable.
    - Priorisation de quelques pays frequents (`FR`, `US`, `CA`, `GB`, `BE`, `CH`, `DE`, `ES`) en haut de la liste tout en conservant l'ensemble des pays disponibles.
    - Suppression de l'envoi du pseudo `area_code` depuis cette popup, car il ne correspondait pas a l'intention produit exprimee par l'utilisateur.
- **Decisions Techniques :** La liste pays et les indicatifs reutilisent la source de verite deja presente dans le frontend plutot qu'une table maison. Cela reduit la dette de maintenance, garde la coherence UX avec les autres champs telephone du projet et evite d'envoyer au backend des filtres Twilio trompeurs par rapport au wording de la popup.
- **Impacts & Dependances :** Fichier touche : `ui/src/components/telephony/PhoneNumberDialog.tsx`, `ENGINEERING_LOG.md`. Validation effectuee : diagnostics IDE OK, `npm exec -- tsc --noEmit` OK.
- **Prochaines etapes :** Si besoin, ajouter une recherche texte dans le select pays si le volume de pays rend la navigation trop longue pour certains utilisateurs.

### [2026-07-04T02:05:00Z] | Durcissement Bookivox Number et achat managé sans fuite multi-tenant
- **Contexte :** Le flux precedent exposait en mode `Bookivox Number` des elements techniques inutiles (credentials masques, URL webhook, import de numéros Twilio) et, surtout, un inventaire du compte Twilio partagé. Dans un contexte multi-tenant, cela permettait a un client d'apprendre l'existence de numéros pouvant appartenir a d'autres clients.
- **Modifications effectuees :**
    - Ajout d'un endpoint backend `POST /api/v1/organizations/telephony-configs/{config_id}/managed-phone-numbers/purchase` reserve aux configurations `twilio` avec `use_managed_credentials=true`.
    - Ajout dans `TwilioProvider` d'une recherche de numero local disponible et d'un provisionnement avec `VoiceUrl` Bookivox attache des la creation.
    - Blocage explicite de `GET /provider-phone-numbers` pour les configurations `Bookivox Number` afin de fermer l'enumeration du compte Twilio partagé.
    - Masquage complet des credentials managed cote detail de configuration, en ne laissant plus remonter que `use_managed_credentials=true`.
    - Simplification des ecrans `/telephony-configurations`, detail telephonie et `PhoneNumberDialog` : plus de bouton d'import, plus d'URL webhook affichee, plus de champs sensibles, seulement le parcours produit `Acheter un numéro` pour le mode Bookivox.
    - Validation backend des filtres d'achat (`country_code` ISO-2, `area_code` numerique) pour ne pas dependre des controles frontend.
- **Decisions Techniques :** Le provider runtime reste `twilio` en interne pour conserver les webhooks, le routage et la compatibilite existante, mais l'inventaire du compte partagé n'est plus une primitive UI/API en mode managed. Le numero est desormais alloue a la demande pour une configuration precise, ce qui respecte l'isolation inter-clients et simplifie l'UX.
- **Impacts & Dependances :** Fichiers touches : `api/routes/organization.py`, `api/services/telephony/base.py`, `api/services/telephony/providers/twilio/provider.py`, `ui/src/app/telephony-configurations/page.tsx`, `ui/src/app/telephony-configurations/[configId]/page.tsx`, `ui/src/components/telephony/PhoneNumberDialog.tsx`, `ENGINEERING_LOG.md`. Validations effectuees : diagnostics UI OK, `npm exec -- tsc --noEmit` OK, `./venv/bin/python -m py_compile ...` OK, plus verification grep qu'aucun bouton/texte d'import Twilio partage ne reste expose dans `ui/src`.
- **Prochaines etapes :** Revalider en bout-en-bout l'achat reel d'un numero Twilio sur un environnement de test avec credits Twilio suffisants. Si besoin produit, ajouter ensuite un workflow d'annulation/release provider pour les achats abandonnes apres provisionnement.

### [2026-07-04T01:29:00Z] | Alias UI Bookivox Number pour la telephonie geree
- **Contexte :** L'utilisateur ne veut pas exposer `Twilio` au client final pour les numéros managés. Le select de creation de configuration devait afficher une option produit `Bookivox Number`, sans transformer cette valeur en nouveau provider runtime.
- **Modifications effectuees :**
    - Ajout dans `ConfigFormDialog` d'un alias UI `Bookivox Number` mappe vers le provider backend existant `twilio` avec `use_managed_credentials=true`.
    - Le select est reformule en `Type de connexion` au lieu de `Fournisseur`, pour eviter de presenter `Bookivox Number` comme un provider tiers.
    - Le mode cree par defaut une configuration managed quand `twilio` est disponible dans la liste des providers, tout en laissant l'option `Twilio (BYOK)` accessible pour les comptes clients apportant leurs propres credentials.
    - La liste `/telephony-configurations` affiche maintenant `Bookivox Number` au lieu du provider technique pour les configurations managed correspondantes.
- **Decisions Techniques :** Le backend continue a utiliser `twilio` comme provider canonique pour ne pas dupliquer le runtime, les validations webhook et le flux d'import des numéros. L'alias n'existe qu'au niveau UX, ce qui evite les regressions de schema et preserve la compatibilite descendante.
- **Impacts & Dependances :** Fichiers touches : `ui/src/components/telephony/ConfigFormDialog.tsx`, `ui/src/app/telephony-configurations/page.tsx`, `ENGINEERING_LOG.md`. Effet attendu : le client voit `Bookivox Number` comme offre Bookivox, sans exposition du provider sous-jacent.
- **Prochaines etapes :** Uniformiser le meme wording `Bookivox Number` sur les autres vues telephonie detaillee si necessaire pour eviter toute fuite du nom `Twilio` dans l'UX managed.

### [2026-07-04T01:18:00Z] | Badge Bookivox et compteur de numeros importables dans la liste telephonie
- **Contexte :** L'utilisateur avait maintenant les actions directes dans `/telephony-configurations`, mais il manquait encore un signal visuel clair pour distinguer les configurations `Twilio Bookivox` et savoir, avant le clic, si des numéros restaient a importer.
- **Modifications effectuees :**
    - Ajout d'un badge `Twilio Bookivox` sur les configurations `twilio` utilisant `use_managed_credentials`.
    - Ajout d'un chargement frontend des compteurs de numéros encore importables via l'endpoint `provider-phone-numbers` deja expose.
    - Affichage sur chaque carte d'un sous-texte `X numéros Twilio importables` ou `Tous les numéros Twilio de Bookivox sont déjà importés`.
- **Decisions Techniques :** Le compteur est resolu cote frontend a partir de l'endpoint d'inventaire provider deja present, pour eviter d'alourdir davantage le contrat de la liste avec des appels provider synchrones cote backend. Cette approche garde la page reactive et limite la surface de changement.
- **Impacts & Dependances :** Fichiers touches : `ui/src/app/telephony-configurations/page.tsx`, `ENGINEERING_LOG.md`. Effet attendu : comprehension immediate de la nature managed de la configuration et visibilite du stock de numéros importables sans navigation supplementaire.
- **Prochaines etapes :** Si la liste grossit fortement, mutualiser plus tard ces compteurs via un endpoint backend agregé pour reduire le nombre d'appels reseau au chargement de la page.

### [2026-07-04T01:12:00Z] | Actions directes de numero depuis la liste telephonie
- **Contexte :** Meme apres avoir rendu le parcours plus visible, l'utilisateur devait encore entrer dans la page détail d'une configuration pour ajouter un numéro ou lancer l'import Twilio. Cela ajoutait une etape inutile dans un flux frequent.
- **Modifications effectuees :**
    - Extension de `TelephonyConfigurationListItem` pour exposer au frontend les signaux `uses_managed_credentials` et `can_import_provider_phone_numbers`.
    - Enrichissement de `GET /api/v1/organizations/telephony-configs` pour marquer les configurations qui peuvent importer des numéros provider, actuellement `Twilio` en mode géré.
    - Ajout d'un bouton `Ajouter un numéro` directement dans la liste `/telephony-configurations`, ouvrant `PhoneNumberDialog` sans passer par la page détail.
    - Ajout d'un bouton `Importer les numéros Twilio` directement sur les configurations compatibles, avec import direct depuis la liste.
    - Alignement manuel du type frontend genere `ui/src/client/types.gen.ts` pour refleter le nouveau shape de la liste.
- **Decisions Techniques :** Les indicateurs de capabilities sont exposes par l'API de liste pour eviter des fetchs supplementaires par carte et garder une UI reactive. L'import direct continue a reutiliser les endpoints CRUD existants pour conserver les controles de validation, de routage entrant et de dedoublonnage deja en place.
- **Impacts & Dependances :** Fichiers touches : `api/schemas/telephony_config.py`, `api/routes/organization.py`, `ui/src/app/telephony-configurations/page.tsx`, `ui/src/client/types.gen.ts`, `ENGINEERING_LOG.md`. Validation effectuee : diagnostics UI OK, `tsc --noEmit` OK.
- **Prochaines etapes :** Si besoin, etendre la meme logique de capabilities a d'autres providers que Twilio quand un import provider-side sera expose.

### [2026-07-04T00:59:00Z] | Import UI des numeros Twilio geres par Bookivox
- **Contexte :** Le mode `Twilio managed` etait deja accepte cote backend, mais l'UI continuait a demander une saisie manuelle des numéros. Cela rendait le parcours incoherent pour un compte Bookivox qui possede deja des numéros Twilio dans le compte géré.
- **Modifications effectuees :**
    - Ajout dans `TwilioProvider` d'une vraie lecture des `IncomingPhoneNumbers` du compte Twilio via l'API officielle, avec pagination et filtrage des numéros non voice-capable.
    - Ajout d'un endpoint backend `GET /api/v1/organizations/telephony-configs/{config_id}/provider-phone-numbers` qui retourne les numéros du provider et indique s'ils sont deja importes dans Bookivox.
    - Ajout dans la page de detail telephonie d'un bouton `Importer les numéros Twilio` visible pour les configurations `twilio` en mode `use_managed_credentials`.
    - L'import UI cree ensuite les lignes `phone_numbers` manquantes via l'API existante, ce qui preserve toutes les validations backend deja en place (conflits d'inbound routing, dedoublonnage, caller ID par defaut).
- **Decisions Techniques :** L'import passe volontairement par le endpoint CRUD deja existant de creation de numéro plutot que par une insertion bulk cote serveur. Cela evite de dupliquer la logique de validation multi-tenant, limite le risque d'incoherence sur le routage entrant et garde un seul chemin d'ecriture verifie.
- **Impacts & Dependances :** Fichiers touches : `api/services/telephony/base.py`, `api/services/telephony/providers/twilio/provider.py`, `api/routes/organization.py`, `ui/src/app/telephony-configurations/[configId]/page.tsx`, `ENGINEERING_LOG.md`. Validation manuelle effectuee : lecture directe du compte Twilio managed OK, 4 numéros remontes par l'API sur cet environnement local.
- **Prochaines etapes :** Recharger la page de detail d'une configuration `Twilio` gérée puis tester `Importer les numéros Twilio`. Si plusieurs organisations partagent le meme compte Twilio géré, surveiller les erreurs de conflit d'import, qui signalent volontairement un risque de collision de routage inbound.

### [2026-07-04T00:47:00Z] | Fallback preview genere pour voix sans previsualisation native
- **Contexte :** Le client ne pouvait pas choisir proprement certaines voix `Cartesia` et potentiellement `ElevenLabs` quand le provider n'exposait pas de `preview_url`. Le message `Aperçu audio indisponible` etait insuffisant pour une UX de selection commerciale, et les phrases de demo ASCII degradaient la prononciation dans les langues accentuees.
- **Modifications effectuees :**
    - Remplacement de la resolution `Cartesia /voices/{id}` au clic preview par une lecture directe du catalogue deja charge, afin d'eviter un aller-retour provider supplementaire et un point de blocage reseau.
    - Ajout d'un fallback backend de generation TTS pour `Cartesia` et `ElevenLabs` quand une voix n'a pas de `preview_url`, avec cache memoire TTL pour limiter cout et latence.
    - Restriction de la generation aux `voice_id` presents dans le catalogue provider pour reduire l'abus de l'endpoint preview.
    - Mise a jour des textes d'exemple multilingues avec les accents/caracteres reels quand cela influence la prononciation (`aperçu`, `Olá`, `krótka`, etc.).
    - Ajout d'un test unitaire supplementaire pour le fallback `ElevenLabs`.
- **Decisions Techniques :** Le catalogue local devient la source de verite pour savoir si une voix peut reutiliser un preview provider ou doit passer par une generation serveur. Cela reduit la surface reseau, evite un chemin de resolution fragile, preserve les secrets backend et maintient une UX uniforme entre providers managed.
- **Impacts & Dependances :** Fichiers touches : `api/services/managed_voice_catalog.py`, `api/tests/test_managed_voice_catalog.py`, `ENGINEERING_LOG.md`. Validation manuelle effectuee : backend relance sur `8001`, healthcheck OK, preview genere avec succes pour une voix `Cartesia` francaise sans preview natif (`audio/wav`, 649232 octets). Verification catalogue `ElevenLabs` locale : 10 voix chargees, 0 preview manquant sur ce compte au moment du test.
- **Prochaines etapes :** Recharger l'UI et verifier le modal de voix sur des voix `Cartesia` non anglaises. Si certaines voix `ElevenLabs` sans preview apparaissent sur un autre compte/provider region, le fallback backend est deja en place et devra seulement etre revalide en bout-en-bout.

### [2026-07-04T00:38:00Z] | Feedback UI quand une voix n'a pas de preview provider
- **Contexte :** Le preview fonctionnait pour certaines voix `Cartesia` en anglais mais semblait `ne rien faire` pour d'autres langues. Verification faite : plusieurs voix `fr` remontent bien dans le catalogue mais avec `preview_url = null`, donc aucun extrait audio n'est fourni par le provider pour ces voix.
- **Modifications effectuees :**
    - Ajout d'un etat `previewError` dans `ui/src/components/VoiceSelectorModal.tsx`.
    - Affichage explicite d'un message `Aperçu audio indisponible pour cette voix.` quand une voix n'expose pas de preview.
    - Affichage explicite d'un message d'erreur si le fetch de preview echoue ou si la session n'est pas disponible.
    - Validation TypeScript du composant apres modification.
- **Decisions Techniques :** Le comportement silencieux a ete remplace par un feedback explicite. Cela preserve l'integrite de la selection de voix sans inventer de faux previews et clarifie une limite reelle du catalogue provider.
- **Impacts & Dependances :** Fichier touche : `ui/src/components/VoiceSelectorModal.tsx`. Effet attendu : les voix sans preview restent selectionnables pour les appels, mais l'utilisateur comprend immediatement pourquoi l'ecoute n'est pas disponible.
- **Prochaines etapes :** Si l'on veut un preview meme pour ces voix, il faudra generer un extrait TTS serveur temporaire a partir d'un texte neutre, avec controle de couts et rate limiting.

### [2026-07-04T00:33:00Z] | Proxy de preview audio pour Cartesia et TTS manages
- **Contexte :** Les voix `Cartesia` etaient visibles dans l'UI mais leur ecoute echouait. La documentation officielle `Cartesia` indique que `preview_file_url` requiert le meme header `Authorization` que l'API des voix, ce qui explique l'echec du `new Audio(preview_url)` directement depuis le navigateur.
- **Modifications effectuees :**
    - Ajout d'une route backend `GET /api/v1/user/configurations/voices/{provider}/preview?voice_id=...` qui proxy l'audio de preview avec les credentials server-side.
    - Ajout dans `managed_voice_catalog.py` d'une resolution de preview par `voice_id`, avec chemin rapide `Cartesia` via `GET /voices/{id}?expand[]=preview_file_url`.
    - Verrouillage des hosts de preview autorises par provider pour limiter l'exposition SSRF.
    - Remplacement cote UI du `new Audio(preview_url)` direct par un `fetch` authentifie vers le backend, conversion en `blob`, puis lecture locale via `URL.createObjectURL`.
    - Nettoyage memoire des object URLs de preview a l'arret et en fin de lecture.
- **Decisions Techniques :** Le preview est ramene cote serveur pour ne jamais exposer les cles provider au navigateur et pour gerer proprement les providers dont les URLs de preview exigent une authentification explicite. La selection `voice_id` reste la source de verite utilisee ensuite dans la configuration d'appel.
- **Impacts & Dependances :** Fichiers touches : `api/services/managed_voice_catalog.py`, `api/routes/user.py`, `ui/src/components/VoiceSelectorModal.tsx`, `ENGINEERING_LOG.md`. Effet attendu : l'ecoute de preview fonctionne pour `Cartesia` comme pour les autres providers manages. Cote metadata, `genre` reste renseigne quand le provider le fournit; `accent` reste vide si le provider n'en expose pas, sans casser l'UI.
- **Prochaines etapes :** Recharger completement le frontend et verifier la lecture d'un preview `Cartesia`. Si besoin, ajouter un indicateur UI explicite quand une voix n'expose aucun preview.

### [2026-07-04T00:27:30Z] | Rechargement backend pour prise en compte de la clé Cartesia
- **Contexte :** `ElevenLabs` affichait des voix mais `Cartesia` restait vide alors que la clé avait ete renseignee dans `api/.env`. Le catalogue `Cartesia` etait pourtant fonctionnel en execution directe, ce qui pointait vers un backend local demarre avec un ancien environnement.
- **Modifications effectuees :**
    - Arret complet de la stack locale.
    - Redemarrage du backend en rechargeant explicitement `api/.env` avant `./scripts/start_services_dev.sh`.
    - Verification du healthcheck `http://127.0.0.1:8001/api/v1/health` apres redemarrage.
- **Decisions Techniques :** Le backend lit les variables d'environnement au demarrage. Modifier `api/.env` ne suffit pas tant que le process `uvicorn` et ses workers n'ont pas ete relances avec le nouvel environnement shell.
- **Impacts & Dependances :** Aucun changement de code supplementaire. Effet attendu : le provider `Cartesia` visible dans l'UI utilise maintenant la vraie cle locale chargee en memoire par le backend.
- **Prochaines etapes :** Recharger le navigateur et retester le modal de voix `Cartesia`. Si le catalogue reste vide, tracer la reponse HTTP de l'endpoint `/api/v1/user/configurations/voices/cartesia` depuis la session navigateur.

### [2026-07-04T00:19:00Z] | Catalogue de voix local direct ElevenLabs et Cartesia
- **Contexte :** Le selecteur de voix s'ouvrait dans l'UI mais affichait `Impossible de charger les voix`. Le backend pointait encore vers `MPS_API_URL=https://app.bookivox.com` pour `/user/configurations/voices/{provider}`, ce qui ne consommait pas les cles `ElevenLabs` / `Cartesia` definies localement dans `api/.env`.
- **Modifications effectuees :**
    - Creation de `api/services/managed_voice_catalog.py` pour recuperer directement les catalogues de voix `ElevenLabs` et `Cartesia` depuis leurs APIs officielles avec les cles backend locales.
    - Normalisation du payload provider vers le format UI commun (`voice_id`, `name`, `description`, `accent`, `gender`, `language`, `preview_url`).
    - Ajout du filtrage backend par recherche/genre/accent/langue et generation des facettes sur le catalogue complet.
    - Ajout d'un cache memoire court pour limiter les appels repetes au provider et reduire le risque de rate limiting.
    - Branchement de `api/routes/user.py` pour utiliser ce catalogue local sur `elevenlabs` et `cartesia`, avec fallback MPS pour les autres providers.
    - Ajout d'un test cible `api/tests/test_managed_voice_catalog.py`.
- **Decisions Techniques :** Le proxy MPS a ete contourne uniquement pour les providers TTS manages que l'operateur veut alimenter via ses propres cles. Cela preserve la separation BYOK/managed, evite d'exposer les cles au frontend et reduit la dependance a un service externe pour le catalogue de voix.
- **Impacts & Dependances :** Fichiers touches : `api/services/managed_voice_catalog.py`, `api/routes/user.py`, `api/tests/test_managed_voice_catalog.py`, `ENGINEERING_LOG.md`. Validation manuelle effectuee : le service et la route backend renvoient 10 voix `ElevenLabs` avec facettes et URLs d'aperçu. Limite actuelle : `Cartesia` restera indisponible tant que `MANAGED_TTS_CARTESIA_API_KEY` est vide dans `api/.env`.
- **Prochaines etapes :** Recharger l'UI et valider le modal de voix. Si `Cartesia` doit fonctionner dans la meme UX, renseigner `MANAGED_TTS_CARTESIA_API_KEY`, puis valider la pagination et les apercus `preview_file_url`.

### [2026-07-04T00:14:00Z] | Durcissement du modal de voix vis-a-vis de l'auth
- **Contexte :** Le message `Impossible de charger les voix` persistait encore si le modal etait ouvert alors que la session locale n'etait pas encore entierement initialisee.
- **Modifications effectuees :**
    - Blocage explicite des requetes du modal tant que `auth.loading` est actif.
    - Refus explicite des appels quand l'utilisateur n'est pas authentifie.
    - Passage des headers d'auth sous forme d'objet simple `Authorization` pour le SDK genere.
    - Verification TypeScript locale via `npm exec -- tsc --noEmit`.
- **Decisions Techniques :** Le composant gere maintenant lui-meme l'etat minimal de securite du chargement des voix. Cela elimine une classe de courses d'initialisation entre auth locale, interceptors SDK et ouverture du modal.
- **Impacts & Dependances :** Fichier touche : `ui/src/components/VoiceSelectorModal.tsx`. Effet attendu : le catalogue de voix ne tente plus d'etre charge sans session valide, et l'erreur visible ne doit plus apparaitre dans le cas nominal.
- **Prochaines etapes :** Si l'erreur persiste apres rechargement complet du navigateur, tracer la reponse backend MPS `/voice-proxy/{provider}/voices` pour distinguer un probleme d'auth d'un probleme provider/credential.

### [2026-07-04T00:11:00Z] | Correction auth chargement catalogue de voix
- **Contexte :** Le selecteur de voix affichait `Impossible de charger les voix` dans l'UI alors que le backend etait demarre. L'endpoint `/api/v1/user/configurations/voices/{provider}` repondait `401 Authorization header required`.
- **Modifications effectuees :**
    - Ajout d'un envoi explicite du bearer token dans `ui/src/components/VoiceSelectorModal.tsx` pour les requetes de lecture du catalogue et de resolution de la voix selectionnee.
    - Ajout d'un message d'erreur specifique quand la session n'est pas prete ou invalide.
- **Decisions Techniques :** Le composant ne depend plus uniquement de l'intercepteur global du client SDK, ce qui evite les courses d'initialisation entre l'ouverture du modal et l'enregistrement de l'intercepteur d'auth.
- **Impacts & Dependances :** Fichiers touches : `ui/src/components/VoiceSelectorModal.tsx`, `ENGINEERING_LOG.md`. Effet attendu : le chargement des voix fonctionne de maniere fiable depuis la page `/model-configurations`.
- **Prochaines etapes :** Si le catalogue reste vide apres authentification, verifier la reponse MPS `/voice-proxy/{provider}/voices` et les credentials provider (`ElevenLabs`/`Cartesia`) dans `api/.env`.

### [2026-07-04T00:08:13Z] | Correction runtime pipecat bookivox vers bookivox
- **Contexte :** Le backend ne demarrait pas reellement en local. `uvicorn` et les workers etaient lances, mais le process applicatif crashait pendant l'import avec `ModuleNotFoundError: No module named 'pipecat.services.bookivox'`.
- **Modifications effectuees :**
    - Remplacement des imports runtime `pipecat.services.bookivox.*` par des aliases vers les implementations existantes `pipecat.services.bookivox.*` dans `api/services/pipecat/service_factory.py`.
    - Redemarrage complet de la stack locale sur `8001`.
    - Validation du healthcheck via `curl http://127.0.0.1:8001/api/v1/health`.
- **Decisions Techniques :** Le correctif a ete limite au runtime applicatif pour restaurer le demarrage sans toucher au sous-module `pipecat` ni renommer en masse les packages internes. Les symboles exposes cote application restent `Bookivox*`, mais pointent temporairement vers les classes `Bookivox*` deja presentes dans le sous-module.
- **Impacts & Dependances :** Fichiers touches : `api/services/pipecat/service_factory.py`, `ENGINEERING_LOG.md`. Effet attendu : le backend local redemarre correctement, les workers cessent de crasher a l'import, et l'UI peut joindre `http://localhost:8001`.
- **Prochaines etapes :** Realigner plus largement les references `bookivox`/`bookivox` dans les tests et, si necessaire, dans le sous-module `pipecat` pour supprimer ce pont de compatibilite temporaire.

### [2026-07-03T23:47:00Z] | Alignement env local backend 8001 embeddings et Twilio
- **Contexte :** La configuration locale utilise `http://localhost:8001` pour le backend, mais le bloc managed de `api/.env` n'exposait pas encore `embeddings` ni `Twilio`, ce qui rendait la config operateur incomplete et source de confusion au lancement.
- **Modifications effectuees :**
    - Ajout de `MANAGED_EMBEDDINGS_PROVIDER`, `MANAGED_EMBEDDINGS_API_KEY`, `MANAGED_EMBEDDINGS_MODEL`, `MANAGED_EMBEDDINGS_BASE_URL` et `MANAGED_EMBEDDINGS_EXTRA_JSON` dans `api/.env`.
    - Alignement de `api/.env.example` sur `OpenRouter` aussi pour les embeddings managed.
    - Ajout du bloc `MANAGED_TWILIO_ACCOUNT_SID` / `MANAGED_TWILIO_AUTH_TOKEN` dans `api/.env`.
- **Decisions Techniques :** Les embeddings managed restent sur `OpenRouter` pour conserver la meme surface operator que le LLM et eviter d'introduire un provider supplementaire dans le parcours managed. Les variables Twilio sont documentees directement dans l'env local pour rendre explicite la separation entre credentials managed et credentials client.
- **Impacts & Dependances :** Fichiers touches : `api/.env`, `api/.env.example`, `ENGINEERING_LOG.md`. Effet attendu : la configuration locale est plus complete et l'operateur voit immediatement quoi renseigner pour les embeddings et la telephonie managed.
- **Prochaines etapes :** Demarrer le backend sur `8001` avec `UVICORN_BASE_PORT=8001` ou realigner l'UI sur `8000` si tu preferes rester sur les defaults du repo.

### [2026-07-03T23:41:46Z] | Managed providers OpenRouter multi-TTS et ElevenLabs STT
- **Contexte :** Le mode `Bookivox` devait passer sur `OpenRouter` pour le LLM, offrir plusieurs providers TTS manages (`ElevenLabs` et `Cartesia`) avec choix client du provider et de la voix, et utiliser `ElevenLabs` pour le STT en mode managed.
- **Modifications effectuees :**
    - Changement des defaults managed backend vers `MANAGED_LLM_PROVIDER="openrouter"` et `MANAGED_STT_PROVIDER="elevenlabs"` avec ajout de `MANAGED_TTS_PROVIDERS`.
    - Ajout d'une resolution d'env par provider TTS pour supporter simultanement `ElevenLabs` et `Cartesia` via `MANAGED_TTS_<PROVIDER>_*`.
    - Extension du schema `bookivox` pour stocker `tts_provider + voice`, avec compilation runtime vers le provider TTS choisi.
    - Ajout du provider `ElevenLabs STT` dans le registry backend et branchement du service factory Pipecat vers les services realtime/file-based deja presents dans le sous-module `pipecat`.
    - Mise a jour des defaults d'organisation et de l'editeur UI pour laisser le client choisir le provider TTS managed puis la voix correspondante.
    - Ajout du bloc de configuration dans `api/.env` et documentation correspondante dans `api/.env.example`.
- **Decisions Techniques :** Le choix multi-provider a ete limite au TTS managed pour rester conforme au besoin produit sans rouvrir la complexite BYOK. La resolution des secrets TTS se fait par convention de nommage d'env afin d'eviter une structure JSON opaque difficile a operer. Pour `ElevenLabs STT`, le runtime derive l'URL WebSocket a partir d'une base URL HTTP afin de rester compatible avec la doc officielle et les exigences de validation d'URL.
- **Impacts & Dependances :** Fichiers touches : `api/constants.py`, `api/schemas/ai_model_configuration.py`, `api/services/configuration/ai_model_configuration.py`, `api/services/configuration/registry.py`, `api/services/pipecat/service_factory.py`, `api/routes/organization.py`, `api/.env`, `api/.env.example`, `ui/src/components/AIModelConfigurationV2Editor.tsx`, `ui/src/client/types.gen.ts`, `api/tests/test_ai_model_configuration_v2.py`. Effet attendu : `Bookivox` propose `ElevenLabs` ou `Cartesia` en TTS managed, conserve un seul choix simple cote client, et utilise `ElevenLabs` pour le STT managed.
- **Prochaines etapes :** Regenerer le SDK OpenAPI des que le backend demarre correctement dans cet environnement, puis relancer les tests Python unitaires quand `pytest` et les dependances runtime backend seront installes.

### [2026-07-03T21:11:43Z] | Alignement Bookivox managed voices et Twilio manage
- **Contexte :** Le mode `Bookivox` devait devenir un mode managed simplifie ou le client ne choisit que la voix, tandis que la telephonie devait permettre un choix clair entre credentials Twilio du client et credentials Twilio fournis par la plateforme.
- **Modifications effectuees :**
    - Finalisation du contrat `bookivox` cote UI et tests pour un payload `voice-only`, sans `api_key`, `speed` ni `language`.
    - Ouverture du selecteur de voix sur le catalogue complet par defaut en supprimant les filtres implicites `female/us/en` dans `ui/src/components/VoiceSelectorModal.tsx`.
    - Realignement manuel de `ui/src/client/types.gen.ts` pour refleter le nouveau schema `bookivox` et la configuration Twilio avec `use_managed_credentials`.
    - Mise a jour des tests `api/tests/test_ai_model_configuration_v2.py` pour verifier la compilation vers des providers managed backend et la migration legacy vers `voice-only`.
- **Decisions Techniques :** Le catalogue de voix reste resolu dynamiquement via l'endpoint backend des voix afin d'eviter de figer une liste dans les defaults d'organisation. La regeneration automatique du client OpenAPI n'a pas pu etre executee dans cet environnement car l'import backend echoue sur un module `pipecat.services.bookivox` absent; le type client a donc ete aligne manuellement pour debloquer le frontend sans changer le runtime backend.
- **Impacts & Dependances :** Fichiers touches : `ui/src/components/VoiceSelectorModal.tsx`, `ui/src/client/types.gen.ts`, `api/tests/test_ai_model_configuration_v2.py`, ainsi que les fichiers backend/UI deja modifies pour le mode managed et Twilio. Effet attendu : `Bookivox` n'expose plus qu'un choix de voix, le formulaire Twilio supporte clairement le mode managed/BYOK, et le frontend recompile avec le nouveau contrat.
- **Prochaines etapes :** Retablir la regeneration OpenAPI/SDK des que la dependance `pipecat.services.bookivox` est disponible, puis relancer les tests backend unitaires avec `pytest` installe dans l'environnement local.

### [2026-07-04T23:38:58Z] | Completion des explications tarifaires sur Facturation
- **Contexte :** Plusieurs lignes tarifaires principales de `Facturation` (`Plateforme`, `Appels`, `LLM`, `STT`, `TTS`) n'avaient pas encore le meme niveau d'explication au survol que les autres elements de la page.
- **Modifications effectuees :**
    - Ajout d'un tooltip explicatif pour chaque ligne tarifaire principale dans `ui/src/app/billing/page.tsx`.
    - Harmonisation du niveau de detail entre les tarifs de base et les autres lignes deja documentees au survol.
- **Decisions Techniques :** J'ai complete les tooltips directement dans la definition de `pricingRows` afin de garder une seule source de verite pour les libelles, valeurs et explications associees.
- **Impacts & Dependances :** Fichiers touches : `ui/src/app/billing/page.tsx`, `ENGINEERING_LOG.md`. Effet attendu : comprehension plus immediate des postes de cout affiches, sans ajouter de texte visible dans la page.
- **Prochaines etapes :** Si besoin, relire ensuite tout le wording billing avec un angle plus commercial pour affiner encore les formulations visibles et au survol.

### [2026-07-04T23:34:34Z] | Nettoyage de la copie billing et bascule des explications dans les tooltips
- **Contexte :** La page `Facturation` affichait encore trop de texte explicatif visible, notamment dans `Etat de votre facturation`, `Utilisation de la periode` et `Options et tarification`, ce qui alourdissait la lecture et donnait une impression moins premium.
- **Modifications effectuees :**
    - Ajout d'un helper interne de tooltip dans `ui/src/app/billing/page.tsx` pour uniformiser les points d'interrogation sur la page.
    - Suppression des descriptions visibles redondantes dans les cartes de synthese de facturation.
    - Bascule des explications detaillees de `Etat de votre facturation`, `Utilisation de la periode`, `Abonnement mensuel` et `Options et tarification` dans des tooltips au survol.
    - Reecriture plus propre des messages d'aide pour les options supplementaires et les lignes tarifaires.
- **Decisions Techniques :** J'ai centralise le pattern de survol dans un petit composant local pour garantir une aide homogène, limiter la repetition JSX et conserver une UI sobre sans perte d'information.
- **Impacts & Dependances :** Fichiers touches : `ui/src/app/billing/page.tsx`, `ENGINEERING_LOG.md`. Effet attendu : design plus epure, meilleure lisibilite immediate et explications detaillees accessibles uniquement au besoin.
- **Prochaines etapes :** Si besoin, appliquer le meme niveau de finition aux autres pages avec cartes de synthese pour un langage tooltip encore plus uniforme dans tout le produit.

### [2026-07-04T23:32:17Z] | Masquage du renouvellement mensuel sur Facturation
- **Contexte :** Le bloc `Renouvellement mensuel` ne devait plus apparaitre dans l'UI, tout en gardant ce comportement active par defaut sur le parcours de recharge.
- **Modifications effectuees :**
    - Suppression du bloc visible `Renouvellement mensuel` dans `ui/src/app/billing/page.tsx`.
    - Passage du mode de recharge en renouvellement mensuel actif par defaut cote UI.
- **Decisions Techniques :** Le comportement a ete conserve sans exposition visuelle, afin de simplifier l'interface tout en respectant le parcours produit demande.
- **Impacts & Dependances :** Fichiers touches : `ui/src/app/billing/page.tsx`, `ENGINEERING_LOG.md`. Effet attendu : interface plus epuree et renouvellement applique par defaut lors d'un achat.
- **Prochaines etapes :** Si besoin produit, afficher plus tard ce parametre uniquement dans un parcours avance ou dans le portail de facturation.

### [2026-07-04T23:30:53Z] | Deplacement de Options et tarification sous l'historique billing
- **Contexte :** Le bloc `Options et tarification` devait passer sous `Historique des credits` pour eviter une composition en colonnes desequilibree et mieux respecter la lecture verticale de la page.
- **Modifications effectuees :**
    - Passage de la zone basse de `ui/src/app/billing/page.tsx` d'une grille a deux colonnes vers une pile verticale.
    - Deplacement du bloc `Options et tarification` sous `Historique des credits`.
    - Renforcement du modele "explication au survol" avec des tooltips de section et des aides detaillees sur les lignes concernées.
    - Reduction du texte visible pour laisser les explications detaillees dans les tooltips.
- **Decisions Techniques :** J'ai privilegie une lecture verticale plus naturelle sur cette page, avec un contenu dense d'abord dans l'historique puis une section tarifaire plus compacte en second niveau, afin d'ameliorer l'equilibre visuel sans perdre l'information.
- **Impacts & Dependances :** Fichiers touches : `ui/src/app/billing/page.tsx`, `ENGINEERING_LOG.md`. Effet attendu : mise en page plus stable, plus uniforme et details consultables au besoin via survol.
- **Prochaines etapes :** Si besoin, compacter encore davantage les cartes tarifaires en mode liste simple si la page semble encore trop longue avec de vraies donnees.

### [2026-07-04T23:29:21Z] | Reequilibrage visuel des colonnes sur Facturation
- **Contexte :** La nouvelle page `Facturation` restait desequilibree car le bloc `Options et tarification` contenait sensiblement plus de texte que `Historique des credits`, ce qui cassait l'harmonie de la mise en page.
- **Modifications effectuees :**
    - Reduction de la densite textuelle dans `ui/src/app/billing/page.tsx` pour le bloc `Options et tarification`.
    - Suppression des phrases descriptives redondantes quand une aide tooltip existait deja.
    - Compactage des cartes tarifaires secondaires avec moins de padding et une structure plus concise.
- **Decisions Techniques :** J'ai choisi d'alleger la colonne de droite plutot que de surcharger l'historique, afin de conserver une page sobre, plus lisible et mieux equilibree au premier regard.
- **Impacts & Dependances :** Fichiers touches : `ui/src/app/billing/page.tsx`, `ENGINEERING_LOG.md`. Effet attendu : colonnes plus homogenes visuellement et meilleure coherence globale de la page.
- **Prochaines etapes :** Verifier visuellement si un ajustement de largeur de colonnes reste utile avec des donnees reelles plus longues dans l'historique.

### [2026-07-04T23:28:11Z] | Refonte complete de la page Facturation
- **Contexte :** La page `Facturation` etait fonctionnelle mais visuellement trop dense, trop tabulaire et encore marquee par des libelles heterogenes, ce qui la rendait moins claire et moins premium que le reste de l'application.
- **Modifications effectuees :**
    - Recomposition complete de `ui/src/app/billing/page.tsx` autour de quatre blocs clairs : vue d'ensemble, recharge, historique et options/tarification.
    - Ajout d'une hierarchie visuelle plus nette avec cartes resume, progression d'utilisation, mise en avant du cycle de facturation et meilleur positionnement des actions.
    - Refonte de la zone d'achat de credits avec presets plus lisibles, resume de montant plus clair et meilleure separation des actions.
    - Simplification du tableau d'historique et remplacement du vocabulaire trop technique par des libelles plus naturels.
    - Correction de plusieurs formulations et fautes de copie visibles sur la page.
- **Decisions Techniques :** La refonte est restee sur les primitives UI existantes (`PageShell`, `PageHeader`, `Card`, `Table`, `Progress`) pour garantir la coherence visuelle avec les autres pages deja uniformisees et limiter le risque de regression.
- **Impacts & Dependances :** Fichier touche : `ui/src/app/billing/page.tsx`, plus `ENGINEERING_LOG.md`. Effet attendu : page plus lisible, plus moderne, plus uniforme avec le reste de l'application et plus rassurante pour un client final.
- **Prochaines etapes :** Verifier visuellement la page avec de vraies donnees de facturation et poursuivre la meme exigence de finition sur les derniers ecrans encore trop techniques.

### [2026-07-04T15:53:33Z] | Deuxieme passe de simplification de la copie UI
- **Contexte :** Certains ecrans clients affichaient encore du jargon trop operationnel, des formulations internes ou des messages en anglais qui nuisaient a la perception produit.
- **Modifications effectuees :**
    - Simplification du vocabulaire de `ui/src/app/billing/page.tsx` avec remplacement des termes type `grand livre` et `ecritures` par des libelles plus naturels.
    - Reecriture des libelles et descriptions de `ui/src/app/api-keys/page.tsx` pour retirer le jargon interne et recentrer la page sur les integrations.
    - Nettoyage de `ui/src/app/workflow/[workflowId]/components/RecordingsDialog.tsx`, `ui/src/app/workflow/[workflowId]/components/PhoneCallDialog.tsx` et `ui/src/app/telephony-configurations/[configId]/page.tsx` afin de supprimer les messages en anglais et les formulations trop techniques visibles.
    - Simplification du wording dans `ui/src/components/AIModelConfigurationV2Editor.tsx` pour retirer les references internes aux providers et a la gestion serveur.
- **Decisions Techniques :** La passe a cible en priorite les ecrans a forte visibilite client et les messages d'erreur/action susceptibles d'apparaitre en parcours reel, sans modifier les contrats backend ni la logique metier.
- **Impacts & Dependances :** Fichiers touches : `ui/src/app/billing/page.tsx`, `ui/src/app/api-keys/page.tsx`, `ui/src/app/workflow/[workflowId]/components/RecordingsDialog.tsx`, `ui/src/app/workflow/[workflowId]/components/PhoneCallDialog.tsx`, `ui/src/app/telephony-configurations/[configId]/page.tsx`, `ui/src/components/AIModelConfigurationV2Editor.tsx`, `ENGINEERING_LOG.md`. Effet attendu : interface plus premium, plus coherente et moins exposee au jargon interne.
- **Prochaines etapes :** Continuer la francisation et la simplification des ecrans secondaires qui contiennent encore des messages en anglais, notamment certains parcours campagne et workflow.

### [2026-07-04T15:16:57Z] | Nettoyage des messages client exposes sur l'UI
- **Contexte :** Plusieurs ecrans clients affichaient encore des messages trop internes sur le mode de deploiement, des parcours externes et des details d'infrastructure qui degradent la perception produit.
- **Modifications effectuees :**
    - Suppression du bandeau explicatif OSS sur `ui/src/app/billing/page.tsx`.
    - Retrait du renvoi `app.bookivox.com` dans `ui/src/app/api-keys/page.tsx` lorsque la creation supplementaire de cles de service n'est pas proposee.
    - Suppression du bloc d'information technique sur le traitement externe des documents dans `ui/src/app/files/DocumentUpload.tsx`.
- **Decisions Techniques :** Le choix a ete de supprimer ces messages plutot que de les reformuler, afin d'eviter toute fuite de details internes cote client tout en conservant les restrictions fonctionnelles deja appliquees par l'interface.
- **Impacts & Dependances :** Fichiers touches : `ui/src/app/billing/page.tsx`, `ui/src/app/api-keys/page.tsx`, `ui/src/app/files/DocumentUpload.tsx`, `ENGINEERING_LOG.md`. Effet attendu : interface plus sobre, plus premium et sans exposition inutile de logique OSS ou de parcours externes.
- **Prochaines etapes :** Continuer la passe de durcissement UX sur les messages d'erreur et notices visibles pour eliminer les formulations trop techniques ou trop internes dans les autres parcours metiers.

### [2026-07-03T20:25:17Z] | Retrait de l'onglet temps reel dans Modeles
- **Contexte :** La page `Modeles` devait etre simplifiee pour ne plus exposer le parcours `temps reel` dans l'UI principale.
- **Modifications effectuees :**
    - Suppression de l'onglet `Temps reel` dans `ui/src/components/AIModelConfigurationV2Editor.tsx`.
    - Passage du selecteur principal a deux onglets visibles : `Bookivox` et `BYOK`.
    - Conservation de la logique backend et des structures de configuration existantes pour ne pas casser les payloads ni le chargement.
- **Decisions Techniques :** Le retrait a ete limite a la couche presentation de l'editeur principal afin d'eliminer l'option de l'interface sans modifier le contrat API ni la compatibilite avec les configurations deja stockees.
- **Impacts & Dependances :** Fichiers touches : `ui/src/components/AIModelConfigurationV2Editor.tsx`, `ENGINEERING_LOG.md`. Effet attendu : la page `Modeles` n'affiche plus l'option `temps reel` tout en gardant le backend intact.
- **Prochaines etapes :** Verifier s'il faut aussi masquer les references `temps reel` dans d'autres parcours lies aux modeles ou aux overrides workflow.

### [2026-07-03T19:11:24Z] | Conversion de `pipecat` en dossier versionne
- **Contexte :** Le depot devait etre pousse vers un nouveau remote GitHub avec tout le code embarque, alors que `pipecat` etait encore reference comme sous-module Git.
- **Modifications effectuees :**
    - Creation d'une sauvegarde complete du depot dans `../_repo_backups` avant toute manipulation Git.
    - Suppression de la reference sous-module `pipecat` (`.gitmodules` + gitlink) pour preparer une integration en dossier normal.
    - Restauration du contenu exact de `pipecat` depuis la copie locale de sauvegarde, puis re-ajout dans l'index Git comme fichiers standards.
- **Decisions Techniques :** La conversion a ete faite avec sauvegarde prealable et restauration depuis la copie locale exacte plutot qu'un reclonage reseau, afin d'eviter toute derive par rapport au contenu reel du sous-module present sur la machine.
- **Impacts & Dependances :** Fichiers touches : `.gitmodules`, l'arborescence `pipecat/`, et l'index Git racine. Effet attendu : le prochain commit embarque `pipecat` directement dans le depot principal et supprime la dependance au sous-module externe.
- **Prochaines etapes :** Finaliser le commit Git global, pousser sur `origin/main`, puis verifier l'etat final du depot distant et nettoyer uniquement les artefacts temporaires crees pour la sauvegarde.

### [2026-07-03T17:42:00Z] | Regularisation des formulaires BYOK et Speech to Speech
- **Contexte :** Les formulaires de configuration `BYOK` et `Speech to Speech` restaient visuellement irreguliers avec des grilles asymetriques, des zones API keys peu homogenees et des actions mal rythmees.
- **Modifications effectuees :**
    - Refonte du layout de `ui/src/components/ServiceConfigurationForm.tsx` avec un bloc fournisseur distinct, une grille responsive reguliere pour les champs et des sections API keys mieux structurees.
    - Harmonisation des libelles visibles, des placeholders, des tabs et du bouton final aligne a droite.
    - Conservation stricte de la logique de sauvegarde et des payloads backend existants.
- **Decisions Techniques :** Le composant `ServiceConfigurationForm` est partage par `BYOK` et `Speech to Speech`, donc la correction a ete centralisee ici pour reduire les divergences visuelles sans dupliquer de logique.
- **Impacts & Dependances :** Fichier touche : `ui/src/components/ServiceConfigurationForm.tsx`. Effet attendu : formulaires plus stables, plus symetriques et plus lisibles sur les parcours `BYOK` et `Speech to Speech`.
- **Prochaines etapes :** Verifier visuellement les cas reels de fournisseurs avec beaucoup de champs et ajuster si certains schemas generent encore des longueurs atypiques.

### [2026-07-03T17:28:00Z] | Suppression du parcours v1 sur model-configurations
- **Contexte :** La page `model-configurations` exposait encore un parcours `v1`, alors que la demande produit est de n'afficher que la configuration actuelle `v2`.
- **Modifications effectuees :**
    - Suppression de l'edition legacy `v1` dans `ui/src/components/ModelConfigurationV2.tsx`.
    - Mise en place d'une migration automatique vers `v2` quand une organisation est encore en `legacy_user_v1`.
    - Conservation des endpoints backend existants de lecture, sauvegarde et migration.
- **Decisions Techniques :** La migration automatique permet d'eliminer l'UI legacy sans changer le contrat backend. En cas d'echec, la page reste dans un etat de relance explicite au lieu de re-afficher le vieux formulaire.
- **Impacts & Dependances :** Fichier touche : `ui/src/components/ModelConfigurationV2.tsx`. Effet attendu : la page n'affiche plus que l'experience `v2` et force la bascule des anciennes organisations vers le nouveau parcours.
- **Prochaines etapes :** Verifier le rendu en environnement local avec une organisation legacy et confirmer que la transition vers `Bookivox / BYOK` est immediate.

### [2026-07-03T16:52:45Z] | Refonte UI modales et symetrie formulaires
- **Contexte :** Plusieurs ecrans UI restaient trop proches de la base d'origine, avec des textes sous champs trop verbeux, des actions parfois alignees a gauche, des modales qui depassaient l'ecran et des asymetries de largeur entre inputs, selects et blocs d'action.
- **Modifications effectuees :**
    - Uniformisation du comportement global des modales via `dialog`, `alert-dialog` et `sheet` avec `max-height`, scroll interne et footer aligne a droite.
    - Refactor de formulaires/boites de dialogue critiques pour remplacer les textes d'aide sous champs par des tooltips `?` dans les configurations telephonie, campagnes, preferences, telemetry, MCP et enregistrements.
    - Reequilibrage des layouts sur plusieurs pages et composants (`settings`, `reports`, `LanguageSelector`, `VoiceSelectorModal`, dialogues d'enregistrements, media preview, workflow tester).
    - Repositionnement des actions primaires a droite et reduction des largeurs fixes cassant la symetrie.
- **Decisions Techniques :** Le choix a ete de corriger d'abord les primitives globales (`Dialog`, `AlertDialog`, `Sheet`) pour traiter le probleme des modales a la source, puis de cibler les gros formulaires et modales les plus visibles. Cette approche reduit la dette UI, limite les regressions et generalise le comportement sans multiplier les correctifs locaux.
- **Impacts & Dependances :** Fichiers touches principaux : `ui/src/components/ui/dialog.tsx`, `ui/src/components/ui/alert-dialog.tsx`, `ui/src/components/ui/sheet.tsx`, `ui/src/components/telephony/*`, `ui/src/components/*Section.tsx`, `ui/src/components/MCPSection.tsx`, `ui/src/components/VoiceSelectorModal.tsx`, `ui/src/app/settings/page.tsx`, `ui/src/app/reports/page.tsx`, `ui/src/app/recordings/RecordingsUploadDialog.tsx`, `ui/src/app/workflow/[workflowId]/components/RecordingsDialog.tsx`. Effet attendu : modales plus robustes sur petits ecrans, formulaires plus compacts et meilleure coherence visuelle transversale.
- **Prochaines etapes :** Continuer la passe page par page sur les ecrans metiers encore denses (`workflow settings`, `campaign details`, `service configuration`, `usage`) pour remplacer les derniers helper texts residuels et pousser davantage l'uniformite visuelle.
