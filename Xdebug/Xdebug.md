## Debug
En faisant du code , il est rare voire impossible que celui-ci marche du premier coup. 
Il existe des outils aidant le développeur à analyser les bogues du code. Nous allons faire une brève introduction de Xdebug.
## Pour commencer
Nous allons vérifier si xdebug est installé.
### Exercice 
Vérifier à partir de la homepage de wampserveur que vous avez l'extension xdebug activée.
executer le script  :

    <?php
       echo phpinfo();
    ?>
Trouver xdebug_remote_enable, quel est sa valeur.
Cette valeur doit être a on.
## Configuration de xdebug
Pour configurer xdebug, rajouter au fichier php.ini

    xdebug.remote_enable=1
    xdebug.remote_handler=dbgp
    xdebug.remote_host=127.0.0.1
    xdebug.remote_port=9000
    xdebug.remote_log="/var/log/xdebug/xdebug.log"
    
## Configuration de sublime
Installation ddu package xdebug-client
En ouvrant le dossier projet crée le contenu ressemble à : 

    {
        "folders":
        [
           {
              "follow_symlinks": true,
              "path": "."
          }
        ]
    }
    On peut rajouter une url pour xdebug
    
      {
        "folders":
       [
           {
                "follow_symlinks": true,
                "path": "."
           }
        ],
        "settings": {
            "xdebug": {
                 "url": "http://my.local.website/",
            }
        }
    }
    
    
    
## lancez xdebug
Sur sublime, cliquez sur tools xdebug -> Start debugging
   
 ## breakpoints
 Ecrire un bout de script avec trois variables. Utiliser xdebudg pur voir leur evolution.
