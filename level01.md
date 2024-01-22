# Solution du niveau 1
### Afin de trouver le flag du niveau 1, voici comment j'ai procédé:

- Je suis d'abord revenu au répertoire `/home/level` et j'ai affiché son contenu: <pre><b style="color:#3794FF">00_welcome      02  04_kwisatz  07_tropical_fruits  10_choose_your_path   12_pytong   15_live_rfi  level01    special
01_choice_tree  03  05_privacy  08_sshz             11_choose_your_path2  14_live_fi  20_live_rce  matrixman</b></pre>

- Comme on a déjà exploré le dossier <b style="color:#3794aa">00_welcome</b>, on va maintenant explorer le dossier <b style="color:#3794aa">01_choice_tree</b>. Avec la commande <i style = 'color:#E6D737'>ls</i>, voici ce qu'on peut voir:<pre>README.md  <b style="color:#3794FF">blue  green  red</b></pre>

- Comme le fichier ***README.md*** ne contenait rien d'intéressant, j'ai commencé par explorer le dossier  <b style="color:#3794aa">red</b>. Mais ce dossier ne contenait qu'un seul fichier texte qui avait comme message <b style ="color:#FF4838; font-family:'Comic Sans Ms'">DEAD</b>. Je suis donc passé au dossier <b style="color:#3794aa">green</b>. Ce dossier aussi ne contenait qu'un seul fichier texte avec le message <i style="color:#6CC466; font-family:'Comic Sans Ms'">there is no green pill</i>. Il ne reste plus que le dossier  <b style="color:#3794aa">blue</b>. 

- Ce dossier contenait un autre dossier qui contenait les dossiers suivant:<pre><b style="color:#3794FF">black  grey  white</b></pre>

- En allant dans le dossier <b style="color:#3794aa">white</b>, j'ai trouvé un fichier ***README.exe***  dont j'ai pu lire le contenu avec la commande  <i style = 'color:#E6D737'>cat</i>: <pre>BROTHER, TRUST ME
THE WHITEHAT HAS NO SECRETS
DEEP IN YOUR HEART YOU SHOULD BECOME A GRAYHAT
ALWAYS KEEP A JOKER.</pre> Ce message nous incite alors à regarder le dossier <b style="color:#3794aa">grey</b>. 

- Finalement, on peut voir dans ce dossier un autre dossier qui lui aussi contient un dossier avec un fichier ***SOLUTION.txt***, et on peut lire le contenu avec la commande  <i style = 'color:#E6D737'>cat</i>.
---