# Yannis #
> ## What I read ##
    * http://developers.facebook.com/docs/reference/plugins/like/
    * https://developers.facebook.com/docs/opengraphprotocol/#types
    * http://www.quora.com/What-is-the-difference-between-the-Facebook-Like-button-and-their-Recommend-button
    * http://reyt.net/5-raisons-de-retirer-le-bouton-like-facebook-de-votre-site/787

> ## What I think ##
    * il y a une différence pour retrouver les "like" avec la timeline de facebook (a vérifier)

> ## What I learned ##
    * Si on aime un site comme KRDS on ne voit ni sur mon mur directement, ni dans l'accueil, on le voit dans les activités récentes et quand elle ne l'est plus, on la retrouve dans le profil, infos et activités et intérêt.
    * Il y a moyen d'intégré le bouton j'aime en html5 et XFBML (nécessite le SDK Javascript à intégrer juste après la balise body) ou avec iFrame.
    * Pour savoir qui a aimer il faut utiliser XFBML (à vérifier plus profondement)
    * Si on veut que l'utilisateur puisse ajouter un commentaire
      * avec XFBML -> ça se fait toujours
      * avec iFrame -> il faut utiliser la frame standard (à revérifier) avec une largeur de 400px (min).
    * Si il y a un commentaire, l'histoire publié a plus d'importance (cfr dessin)
    * Les "like" se font sur une url donc il faudrait que l'on ait une page pour chaque objet et le "like" portera sur cette page.
    * Il y a moyen de mettre des "tags" pour préciser de quel type est la page (cfr 2ème lien)
    * Mettre 2 même liens sur la même page ne fait pas planter.
> ### Différence entre like et recommend ###
    * Les gens sont plus familiarisé avec like et ils sont moins réticent à cliquer sur j'aime que sur recommander
    * Action plus forte, fonctionne avec le négatif (on ne va pas aimer un article sur la guerre même s'il est intéressant, on va le recommander)
    * prend plus de place dans le flux d'info


### pourquoi html5? ###
  * avec iFrame j'ai pas trouvé comment laisser les guillemets pour qu'il ne se transforme pas en &quot; celà provoquait des problèmes dans les paramètres css du bouton like.

  * vec iFrame:
```
 "http//www.facebook.com/plugins/like.php?href=http%3A%2F%2{{url}}&amp;ParanYoItem={{objecttoshare.key}}&amp;send=false"
```
on a la key après un '&' et le like ne prenait pas en compte les paramètres.

  * avec html5:
```
"http://localhost:8080/readobject?ParanYoItem=ahBkZXZ-eWRvLXRlc3QtaXBschELEgtQYXJhbllvSXRlbRgcDA
```
on a la key après un '?' et dans ce cas là le like la prend en compte.

Ensuite il y avait le choix entre html5 et XFBML j'ai pas trouvé un avantage particulier à utiliser XFBML et en plus il faut rajouter une ligne dans la balise html.
J'ai donc opté pour HTML5.
