# Solution du niveau 2
### Afin de trouver le flag du niveau 2, voici comment j'ai procédé:

- Comme d'habitude, on se rend au répertoire `/home/level`  et cette fois, on entre dans le dossier <b style="color:#3794aa">02</b>.
- En utilisant la commande <i style = 'color:#E6D737'>ls</i>, on peut afficher le contenu du dossier: <pre><b style="color:#3794FF">documents  photos</b></pre>
- Le dossier <b style="color:#3794aa">documents</b> contient un fichier ***letter.txt*** dont le contenu est sans importance, et le dossier <b style="color:#3794aa">photos</b> contient un fichier ***thumbnail*** qui lui aussi n'est d'aucune utilité.
- En revenant dans le dossier  `/home/level/02`, on utilise cette fois la commande <i style = 'color:#E6D737'>ls -a</i>. Voici ce qu'elle affiche: <pre><b style="color:#3794FF">.  ..  .porb  documents  photos</b></pre> <b style="color:#3794aa">.porb</b> est dossier caché qui ne peut être afficher que par la commande précédente.
- Lorsqu'on accède à ce dossier et qu'on regarde son contenu avec <i style = 'color:#E6D737'>ls</i>, rien ne s'affiche. Mais avec <i style = 'color:#E6D737'>ls -a</i>, on peut voir un fichier caché ***.solution***. En utilisant la commande  <i style = 'color:#E6D737'>cat</i>, on peut voir qu'il contient le flag du niveau 2.
---