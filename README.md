# BotTwitter
Un bot multi-compte Twitter simple d'utilisation pour participer aux concours (et les gagner).


### Les fonctionnalités du bot :

* Multicompte
* Bypass les protections de Pickaw (Twrench)
* Tag des comptes quand un concours le demande
* Retweet, like et follow les concours
* Unfollow automatique
* Possibilité de blacklist des comptes
* Si le concours le demande le bot peut follow plusieurs personnes
* Le bot peut répondre à un concours avec des hashtags


### Dépendance du script :

Vous devez installer ces libraries python3 pour que le script fonctionne :
```
Tweepy
PyYaml
feedparser
```
### Installation :

* Dans un premier temps pour utiliser le script vous allez avoir besoin d'un compte développeur Twitter et de récupérer vos accès à l'API.
 Vous pouvez demander cet accès sur le site développeur de Twitter : [Twitter Developer](https://developer.twitter.com/)  
 Si vous avez besoin d'un tutoriel : [Tutoriel compte développeur](https://www.extly.com/docs/autotweetng_joocial/tutorials/how-to-auto-post-from-joomla-to-twitter/apply-for-a-twitter-developer-account/#apply-for-a-developer-account)

* Vous devez ensuite installer une version 3.x de Python : [Python 3.x](https://www.python.org/downloads/)

* Pour finir vous devez installer les libraries Tweepy, PyYaml et feedparser:
     ```
     python3 -m pip install tweepy PyYaml feedparser
     ou
     py -m pip install tweepy PyYaml feedparser
     ```
Ces commandes sont à rentrer dans votre console (cmd pour Windows)
 Si pip n'est pas reconnu vous devez l'installer.


### Configuration :

Tous les paramètres de configurations sont dans le fichier **configuration.yml**.  
Copiez le fichier **configuration.yml.dist** pour créer le fichier **configuration.yml**.

Une fois que vous avez téléchargé le projet, pour pouvoir lancer le script vous devez ajouter dans le fichier configuration.yml les clés de l'[API Twitter](https://developer.twitter.com/).

```
accounts:
  # Accounts name
  - "Nom du compte":
      # API key
      - "Example"
      # API key secret
      - "Example"
      # Access token
      - "Example"
      # Access token secret
      - "Example"
```
Vous pouvez rajouter autant de comptes que vous voulez. Evitez les comptes commençants par un chiffre.
```
accounts:
  # Accounts name
  - "Nom du compte":
      # API key
      - "Example"
      # API key secret
      - "Example"
      # Access token
      - "Example"
      # Access token secret
      - "Example"
  - "Nom du compte 2":
      # API key
      - "Example"
      # API key secret
      - "Example"
      # Access token
      - "Example"
      # Access token secret
      - "Example"
```
Pour faire fonctionner correctement la fonction de bypass antibot, vous devez renseigner des flux rss.  
Une liste de flux que vous pouvez ajouter est disponible ici : [Flux rss](http://atlasflux.saynete.net/index.htm)
```
# RSS
flux_rss:
    - https://partner-feeds.20min.ch/rss/20minutes
    - https://www.24matins.fr/feed
```

Il est possible désactiver la fonction de bypass antibot, la fonction like des concours, la fonction commenter avec un hashtag.
```
# Use the antibot bypass feature (True/False)
bypass_antibot : True

# Like all giveaway (True/False)
like_giveaway : False

# Comment with hashtag (True/False)
comment_with_hashtag : True
```

Vous pouvez ajouter des mot à rechercher pour trouver des concours
```
# Words to search for giveaway
words_to_search:
  - "#concours"
  - "#JeuConcours"
  - "concours pour gagner"
  - "Gagnez rt + follow"
  - "RT & follow"
```

Vous pouvez définir des comptes à tag quand un concours le demande (par défaut vos bots peuvent se tag entre eux)
```
# Accounts we want to invite
accounts_to_tag:
  - "@j4rj4r_binks"
```

En copiant des tweets, vous pouvez récupéré des tweets "sensibles". Il y a donc la possibilité de filtrer des mots à ne pas copier.
```
# Words that should not be copied with the antibot
words_to_blacklist_antibot:
  - "pd"
  - "tapette"
  - "enculé"
  - "pédale"
  - "isis"
```

### Lancement du bot :
```
python3 main.py
ou
py main.py
```

### Install the service

```
sudo cp ~/BotTwitter/bot-twitter.service /etc/systemd/system/bot-twitter.service
sudo systemctl enable bot-twitter.service
sudo systemctl start bot-twitter.service
```



Vous avez une question ? Des idées d'ameliorations ? vous pouvez venir sur notre serveur discord  : [MoneyMakers](https://discord.gg/gjNbrgwRxT)
On recherche des devs pour continuer à améliorer ce bot et à commencer de nouveaux projets !
