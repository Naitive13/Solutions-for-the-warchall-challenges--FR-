# Solution du niveau 11

### Afin de trouver le flag du niveau 11, voici comment j'ai procédé

- On commence par accéder au répertoire `/home/level/`, puis on entre dans le dossier <b style="color:#3794aa">11_choose_your_path2</b>.

- Dans ce dossier, il y a un code en langage C appelé  <i style = 'color:#15fbaf'>charp2.c</i> et sa version compilé <i><b style = 'color:#f05ddf'>charp2</b></i>.  Il y a bien évidemment un fichier ***solution.txt*** dont nous n'avons pas accès. Lorsqu'on regarde le code source du fichier <i style = 'color:#15fbaf'>charp2.c</i>, on comprend que ce programme consiste à compter le nombre de caractère par ligne dans un fichier. Il prend en paramètre le fichier en question. Il y a cependant certaines conditions qu'il faut respecter. Par exemple, si le nom du ficher est trop long, le programme renvoie une erreur.

- Pour obtenir le flag, il faut donc exploiter ce programme. Ici, je propose d'exploiter la commande `--files0-from=`. Par défaut (<i style = 'color:#ff7000'>--files0-from=le_fichier_cible</i>) , elle est utilisée pour spécifier un ficher contenant une liste de chemins de fichiers séparés par des caractères *NULL*. Dans notre cas, on va la passer en paramètre lorsqu’on va executer le programme comme ceci:
>./charp2 "--files0-from=solution.txt"

- Ici, le fichier cible est ***solution.txt***. Lorsqu'on execute cette commande, `--files0-from=` va lire et renvoyer le contenu de ***solution.txt***, ce qui fait que l'argument mis en paramètre pour <i><b style = 'color:#f05ddf'>./charp2</b></i> va changer.
>./charp2 "nouveau contenu généré par la commande précédente"

- Ce nouvel argument correspond au contenu du fichier ***solution.txt***. Le programme va renvoyer un message d'erreur quand il sera executer parce que le nom du fichier est trop. Et dans ce message, on peut voir le nom du fichier qui a été mis en paramètre, autrement dit le contenu de ***solution.txt*** avec le flag du niveau 11.

---