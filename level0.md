# Solution du niveau 0

### Afin de trouver le premier flag (flag du niveau 0), voici comment j'ai procédé

- Une fois que j'ai réussi à me connecter, j'ai utilisé la commande <i style = 'color:#E6D737'>ls</i> pour voir le contenu du répertoire courant. Voici ce qui est affiché: <pre>WELCOME.md <b style="color:#3794FF"> level</b>  www  www_access.log  www_error.log</pre>
- J'ai alors commencé par lire le fichier ***WELCOME.md*** à l'aide de la commande <i style = 'color:#E6D737'>cat</i> et voici son contenu: <pre>
Welcome, challenger to warchall.net.
We hope to be able to present some more realistic challenges in a safe (or not so safe environment) and hope you will like the project!
You will find the solution to each level in
/home/level
or
/home/user/yournick/level
=========================
== COOL ASCII ART HERE ==
=========================
tehron,noother,bsdhell,livinskull,kwisatz,gizmore,jjk,paipai
(warchall.net ) </pre>
- Je suis ensuite allé dans le répertiore `/home/level` grâce à la commande <i style = 'color:#E6D737'>cd</i>  et voici ce que j'ai trouvé: <pre><b style="color:#3794FF">00_welcome      02  04_kwisatz  07_tropical_fruits  10_choose_your_path   12_pytong   15_live_rfi  level01    special
01_choice_tree  03  05_privacy  08_sshz             11_choose_your_path2  14_live_fi  20_live_rce  matrixman</b></pre>

- En accedant au dossier <b style="color:#3794FF">00_welcome</b>, j'y ai trouvé un fichier ***README.md***. En lisant son contenu, on retrouve le flag du niveau 0
---