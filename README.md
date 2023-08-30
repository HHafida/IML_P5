# IML_P5
## Développemment d'un système de suggestion de tags pour le site stackoverflow

Stack Overflow est un site célèbre de questions-réponses liées au développement informatique.
Pour poser une question sur ce site, il faut entrer plusieurs tags afin de retrouver facilement la question par la suite. Pour les utilisateurs expérimentés, cela ne pose pas de problème, mais pour les nouveaux utilisateurs, il serait judicieux de suggérer quelques tags relatifs à la question posée.
Amateur de Stack Overflow, qui vous a souvent sauvé la mise, vous décidez d'aider la communauté en retour. Pour cela, vous développez un système de suggestion de tags pour le site. Celui-ci prendra la forme d’un algorithme de machine learning qui assignera automatiquement plusieurs tags pertinents à une question.


**Données disponible**:
https://data.stackexchange.com/stackoverflow/query/new:

**Commande**:
SELECT TOP 500000 Title, Body, Tags, Id, Score, ViewCount, FavoriteCount, AnswerCount

FROM Posts

WHERE PostTypeId = 1 AND ViewCount > 10 AND FavoriteCount > 10

AND Score > 5 AND AnswerCount > 0 AND LEN(Tags) - LEN(REPLACE(Tags, '<','')) >= 5
