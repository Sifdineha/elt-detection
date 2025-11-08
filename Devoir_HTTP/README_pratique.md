Devoir – Protocole HTTP (partie pratique)

1) Objectif du travail
Ce travail pratique a pour but de comprendre le fonctionnement du protocole HTTP et HTTPS à travers des exemples concrets :
Envoyer une requête HTTP brute avec netcat.
Analyser la structure d’une réponse (status, headers, body) 
Observer les mêmes échanges via un navigateur web (Firefox DevTools).

2) Requête HTTP brute (port 80)

J’ai envoyé une requête manuelle à example.com via le port 80 avec :

printf 'GET / HTTP/1.1\r\nHost: example.com\r\nConnection: close\r\n\r\n' | nc example.com 80

Le serveur a répondu :

HTTP/1.1 200 OK
Content-Type: text/html
ETag: "bc2473a18e003bdb249eba5ce893033f:1760028122.592274"
Last-Modified: Thu, 09 Oct 2025 16:42:02 GMT
Cache-Control: max-age=86000
Date: Sat, 01 Nov 2025 12:14:20 GMT
Content-Length: 513
Connection: close
X-N: S

3) Analyse HTTPS avec Google (port 443)

Ensuite, j’ai observé le protocole HTTPS avec Google :

J'ai envoyé des requêtes avec curl et suivi des redirections.

Observation des headers et des statuts (302, 303, 200).

Enregistrement du corps HTML et des en-têtes complets.

Fichiers produits :

google_headers.txt

google_body.html

google_final_headers.txt

google_final_body.html

Ces fichiers montrent comment un serveur renvoie des redirections avant la réponse finale 200 OK.

5) Observation avec Firefox DevTools

Pour visualiser le trafic HTTP dans mon navigateur :

J’ai ouvert l’onglet Réseau (Network) dans Firefox.

J’ai effectué une recherche : https://www.google.com/search?q=avion.

J’ai sauvegardé les résultats et pris plusieurs captures d’écran.

Captures jointes :

captured'écran 1.png

Capture d’écran 2.png

Capture d’écran 3.png

Capture d’écran 4.png

Capture d’écran 5.png

Capture d’écran 6.png

www.google.com_gen_204_Archive.har

6) Conclusion

Ce travail m’a permis de comprendre la différence entre HTTP et HTTPS. Ca m'a aussi permis d'apprendre à identifier les principales parties d’une requête et d’une réponse. Cela m'a aussi permis de voir comment un navigateur gère automatiquement les redirections, cookies et ressources. Et j'ai aussi appris à utiliser les outils réseau tel que netcat, curl, et Firefox DevTool.
