# Solution du niveau 4

### Afin de trouver le flag du niveau 4, voici comment j'ai procédé:

- Dans le répertoire `/home/level` , on accède au dossier <b style="color:#3794aa">04_kwisatz</b> . Il contient un fichier **_README.nfo_** dont on peut afficher le contenu avec <i style = 'color:#E6D737'>cat</i>: <pre>
Look in your ~
</pre> Ce message nous demande de regarder dans notre répertoire personnel. On peut directement y accéder en tapant simplement la commande <i style = 'color:#E6D737'>cd</i>.

- Grâce à <i style = 'color:#E6D737'>ls -a</i>, on peut voir le contenu de notre dossier :<pre><b style="color:#3794FF">.</b> .bash_history .bashrc <b style="color:#3794FF">.local </b> WELCOME.md <b style="color:#3794FF">www</b> www_error.log
<b style="color:#3794FF">..</b> .bash_logout <b style="color:#3794FF">.cache</b> .profile <b style="color:#3794FF">level</b> www_access.log
</pre>

- Le dossier qui nous intéresse est <b style="color:#3794aa">level</b> . Il contient aussi un dossier <b style="color:#3794aa">04_kwisatz</b> , mais son contenu est différent. Ici, on a 2 fichiers **_README.txt_** et **_README2.md_**. Dans le premier, on a le message suivant:<pre>Dear Future Hacker,
I wrote you an important message in README2.md
Please act accordingly.
The WarChall Staff 2023!
</pre>

- Lorsqu'on essaie de lire le second fichier, un message s'affiche indiquant que nous ne sommes pas autorisés à lire ce fichier. Il faut donc modifier les permissions du fichier **_README2.md_**. Pour cela, on execute la commande <i style = 'color:#E6D737'>chmod 755 README2.md</i>.

- On peut maintenant afficher le contenu de **_README2.md_**, dans lequel se trouve le flag du niveau 4
#