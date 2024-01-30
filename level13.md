# Solution du niveau 13

### Afin de trouver le flag du niveau 13, voici comment j'ai procédé

- On commence par accéder au répertoire `/home/level/matrixman`, puis on entre dans le dossier <b style="color:#3794aa">13_tryouts</b>.

- Dans ce dossier, il y a un code en langage C appelé  <i style = 'color:#15fbaf'>tryouts.c</i> et sa version compilé <i><b style = 'color:#f05ddf'>tryouts</b></i>.  Il y a bien évidemment un fichier ***solution.txt*** dont nous n'avons pas accès. On ne peut malheureusement pas regarder le code source du programme, mais lorsqu'on le lance, on comprend tout de suite en quoi il consiste.

- <i style = 'color:#15fbaf'>tryouts.c</i> nous de demande de deviner un nombre aléatoire généré à l'aide de `/dev/urandom`. Cependant, on ne peut pas acceder à `/dev/urandom`, ce qui fait que deviner les nombres aléatoires qu'il génère est presque impossible. 

#### *Afin de trouver le flag, j'ai décidé d'utiliser une autre approche un peu plus difficile.*

- Suite à plusieurs recherches et analyses approfondies, j'ai pu découvrir plusieurs elements exploitable dans ce niveau :

    1. D'abord, il y a ce qu'on appelle un ***descripteur de fichier***. C'est un identifiant numérique pour faire référence à un fichier ouvert, généralement un entier non négatif où les premiers descripteurs (0, 1, 2) sont souvent réservés pour les entrées/sorties standard (stdin, stdout, stderr). Lorsqu'un programme ouvre un fichier, le système d'exploitation lui attribue un descripteur de fichier, qui peut ensuite être utilisé pour effectuer des opérations de lecture, écriture et autres opérations sur ce fichier. Dans notre cas,  <i><b style = 'color:#f05ddf'>tryouts</b></i> va ouvrir ***solution.txt*** et un descripteur de fichier lui sera attribué. 

    2. Cependant, le descripteur du fichier ***solution.txt*** n'est fermé qu'à la toute fin du programme, même après avoir utilisé /dev/urandom, ce qui semble être anormal. C'est là la faille que l'on va exploiter.

    3. Grâce à mes recherches, j'ai trouver ce code en langages C que l'on peut exploiter: <pre>
    #include <stdio.h> 
    #include <unistd.h> 
    #include <string.h> 
    int main(int argc, char *argv[]) {
    FILE *fp = fopen(argv[1], "w");
    char buf[16];
    memset(buf, 0, sizeof buf);
    lseek(3, 0, SEEK_SET);
    read(3, buf, sizeof buf);
    fprintf(fp, "%s", buf);
    return 0;
    } 
    </pre>
    Ce code va lire des caractères à partir du descripteur de fichier 3 *(puisque dans notre cas les descripteurs 0 à 2 sont probablement déjà utilisés par <i style = 'color:#15fbaf'>tryouts.c</i>)* et les écrit dans un fichier spécifié en paramètre. On utilisera donc ce code pour écrire le contenu de ***solution.txt*** dans un autre fichier.
    
    4. Maintenant que nous avons tous ce dont on  a besoin, il ne reste plus qu'à les utiliser.

- Pour commencer, on va compiler le code précédent pour créer un executable appelé <i><b style = 'color:#f05ddf'>cat</b></i>.

- Puis, on va exécuter ce programme en spécifiant le fichier de sortie où il va écrire le contenu de ***solution.txt***.

- La raison pour laquelle on a nommé le programme <i><b style = 'color:#f05ddf'>cat</b></i> c'est parce qu'on veut le système utilise notre cat plutôt que la commande <i style = 'color:#E6D737'>cat</i> par défaut qui permet d'afficher le contenu d'un fichier. Pour ce faire on va utiliser la commande suivante qui va modifier les variables d’environnement:
> export PATH=$HOME:$PATH

- On va ensuite executer <i><b style = 'color:#f05ddf'>tryouts</b></i>. Ce programme utilise forcément <i style = 'color:#E6D737'>cat</i> pour pouvoir afficher le contenu de ***solutions.txt***. L'idée ici est que le programme utilisera notre <i><b style = 'color:#f05ddf'>cat</b></i> (au lieu de celui système) en raison de l'ordre modifié dans le PATH, et ainsi le contenu de ***solution.txt*** sera écrit dans le fichier spécifié lors de l'exécution de notre <i><b style = 'color:#f05ddf'>cat</b></i>.

- Pour finir, on restaure les variables d'environnements par défaut avec la commande suivante:
>export PATH=$PATH

- Il ne reste plus qu'à consulter le fichier où on a mis le contenu de ***solution.txt*** pour récupérer le flag du niveau 13
---
