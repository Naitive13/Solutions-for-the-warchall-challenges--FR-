# Solution du niveau 12

### Afin de trouver le flag du niveau 12, voici comment j'ai procédé

- On commence par accéder au répertoire `/home/level/`, puis on entre dans le dossier <b style="color:#3794aa">12_pytong</b>.

- Dans ce dossier, il y a un fichier ***pytong.py*** et un autre fichier `pytong` qui est une version compilée du fichier précédent. En regardant le code dans le premier fichier, on peut voir comment il fonctionne mais aussi ce qu'il faut faire pour obtenir le flag.

- En résumer, il faut que le programme retourne  <b style="color:#00ff00">true</b> lorsqu'on le lance. 

<ul> <li> Il y a 2 manières possible pour arriver à ce résultat :

<ol> <li>Si on ouvre un fichier une première fois, puis lorsqu'on essaye de l'ouvrir une deuxième fois le fichier a dispparu, le programme retourne <b style="color:#00ff00">true</b>.</li>
<li> Si on ouvre un fichier une première fois, puis lorsqu'onl'ouvre une deuxième fois le contenu change, le programme retourne <b style="color:#00ff00">true</b>.</li></li></ol></ul>

- Ici on utilisera la deuxième méthode. Pour ce faire. on va créer un script dans notre dossier courant qui va changer régulièrement le contenu d'un fichier. Voici à quoi il pourrait ressembler: <pre>#!/bin/bash
while true
 do echo $(date)>>test.txt
done
</pre> Ici, on va régulièrement rajouter une ligne  dans un fichier ***test.txt*** *(le contenu de la ligne n'est pas important, ici j'ai juste choissi la date)*

- Ensuite, on va lancer ce script en utilisant la commande <i style = 'color:#E6D737'>nohup</i> car si on l'execute juste comme ça, on devra attendre qu'il se termine avant de pouvoir faire autre chose *(il ne se terminera jamais puisque c'est une boucle infini)*. <i style = 'color:#E6D737'>nohup</i> nous permettra de lancer le programme ***pytong*** tout en permentant à notre script de s'executer en arrière-plan.

- Lorsqu'on saisie la ligne suivante: `/home/level/12_pytong/pytong "./test.txt"`, le programme se lance . Si on a bien suivi les instructions précédentes, on aura le message suivant avec le flag:<pre>opening ./test.txt
closed
You are a winner
<?php
return 'KnowYourFilesChiller';
?>
</pre>
