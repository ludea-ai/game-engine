# Ludea — Moteur de jeu

*[English version](README.md)*

Un **modèle de dépôt** GitHub pour créer de petits jeux 2D vus de dessus (Phaser 3, 100 %
statique, sans compilation). Le moteur est générique : on ne programme pas un jeu, on le
**décrit** dans un fichier de configuration (`game.config.js`) et des images — ou, plus simple,
on lance **`/new-game`** et on répond à quelques questions.

Le modèle contient déjà un **petit jeu de départ** qui fonctionne : une mini-nurserie spatiale
où un robot s'occupe de trois créatures lumineuses (trois besoins, un gros plan « on fait
briller », une capsule de repos, des surprises qui apparaissent en jouant), en anglais et en
français. C'est la graine que `/new-game` transforme en votre jeu.

Envie de voir tout ce que le moteur sait faire ? La vitrine **Nebula Nursery** active tous les
systèmes : montures et sauts, boutique et décorations, livraisons poursuivies par des drones,
course en pseudo-3D…

**[Jouer à la vitrine](https://ludea.ai/nebula/)** · **[ludea.ai — les jeux créés avec le moteur](https://ludea.ai/fr/)**

---

## Créer un nouveau jeu

Chaque jeu vit dans **son propre dépôt** : le moteur reste propre et vous pouvez créer autant
de jeux que vous voulez.

1. **« Use this template » → « Create a new repository ».** Sur la page du dépôt, cliquez sur le
   bouton vert **« Use this template »**, donnez un nom à votre jeu (par ex. `mon-jeu-spatial`)
   et choisissez **Public** (GitHub Pages publie gratuitement les dépôts publics). Vous obtenez
   un dépôt indépendant avec tout le moteur et un jeu qui marche déjà.
2. **Activez GitHub Pages :** dans votre dépôt, **Settings → Pages → Source → « GitHub
   Actions »**. C'est la seule chose que l'agent ne peut pas faire à votre place. Votre jeu sera
   en ligne à `https://<vous>.github.io/<dépôt>/`, et chaque envoi sur `main` le remet à jour.
3. **Ouvrez le dépôt dans Claude Code, sur la branche `main`** (voir l'avertissement plus bas).
4. **Tapez `/new-game`.** L'agent vous pose quelques questions — **thème, âge des joueurs, style
   graphique, langue, ce qu'on fait dans le jeu** — puis écrit la fiche du jeu, dessine, teste et
   met en ligne une première version **volontairement petite**.

C'est tout : vous avez votre propre jeu. Ensuite, on le fait grandir en jouant et en donnant
son avis.

> **Travaillez sur `main`.** Dans Claude Code (web), vérifiez que la session travaille bien sur
> `main` : sinon le jeu part sur une autre branche que GitHub Pages ne publie pas.

> **Commencez petit.** Un lieu, une créature, un ou deux besoins, deux actions, peut-être un
> petit objectif. Le jeu grandit au fil des retours : c'est toute la méthode.

---

## Le faire grandir

On joue sur son téléphone, puis on dit ce qu'on veut, avec ses mots : *« ajoute une créature
rose »*, *« je voudrais pouvoir les monter »*, *« ajoute une boutique »*. L'agent choisit la
bonne recette (skill), dessine, teste sur un grand et un petit écran, et met en ligne.

Pour les **retours des joueurs, même des enfants**, dites *« ma fille va faire des retours »* :
le mode **feedback-session** les écoute sans aucune question technique et fait le travail en
silence.

---

## Partager avec Ludea, et rejoindre le catalogue

Votre jeu et le moteur s'améliorent l'un l'autre :

- **Automatiquement :** quand votre jeu rencontre un bug du moteur ou de ses outils, ou a besoin
  d'une nouvelle fonction du moteur (ajoutée de façon générique et activable), le skill
  **report-upstream** l'envoie à Ludea sous forme de signalement sur
  [ludea-ai/game-engine](https://github.com/ludea-ai/game-engine/issues), avec la modification
  exacte jointe. Ludea l'étudie, l'ajoute au moteur, et tous les jeux en profitent à la mise à
  jour suivante.
- **`/ludea-feedback`** : vos propres idées pour le moteur (« ce serait bien si le moteur
  pouvait… »).
- **`/ludea-publish`** : demander que votre jeu apparaisse sur **[ludea.ai](https://ludea.ai/fr/)**.
  L'agent vérifie que le jeu est prêt (âge, description, français + anglais, icône, aucune
  erreur) et sans danger pour les enfants (ni pistage, ni publicité, ni lien extérieur, ni
  collecte de données), puis envoie la demande. Ludea relit la version exacte envoyée — la
  sécurité des enfants d'abord — et, une fois acceptée, met en ligne une copie relue sur
  `https://ludea.ai/<votre-jeu>/`, **avec votre nom** sur sa fiche. Votre dépôt reste le vôtre.

Si votre session Claude Code ne peut pas écrire sur les dépôts Ludea, ces skills vous donnent
un lien déjà rempli : un clic sur **Submit** et c'est envoyé.

---

Pour les détails techniques (structure de `game.config.js`, test local, déploiement, liste des
skills), voir la [version anglaise](README.md) et **[ENGINE.md](ENGINE.md)**.
