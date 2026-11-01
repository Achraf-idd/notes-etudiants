# Exigences de sécurité de l'application des notes

| # | Exigence : « Le système doit… » | Vérification | Étape du SDLC | Test |
|---|---|---|---|---|
| 1 | Le système doit résister aux injections SQL dans la recherche d'un étudiant. | Requête piégée, la réponse est vide | Tests | S1 |
| 2 | Le système doit refuser toute modification de note sans identification (401). | Requête sans jeton, code 401 | Conception | S2 |
| 3 | Le système doit refuser la modification d'une note à un étudiant (403). | Requête avec jeton étudiant, code 403 | Conception | S3 |
| 4 | Le système doit refuser à un enseignant la modification des notes d'un autre module (403). | Requête avec jeton d'un autre module, code 403 | Conception | S4 |
| 5 | Le système doit n'accepter qu'une note numérique entre 0 et 20 (400). | Notes 25 et "20 WHERE 1=1", code 400 | Développement | S5 |
| 6 | Le système doit afficher une erreur sans détail technique (500). | Base inaccessible, aucun détail technique dans la réponse | Développement | S7 |