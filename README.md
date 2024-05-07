Définition des feux de circulation
feu(vert).
feu(rouge).

% Règles pour changer la couleur des feux
changer_feu(vert, rouge).
changer_feu(rouge, vert).

% Règle pour afficher l'état actuel des feux
afficher_feu(Etat) :-
     feu(Etat),
     write('Le feu est actuellement '), write(Etat), nl.

% Règle pour changer la couleur des feux
changer_feux :-
     retract(feu(Etat)),
     changer_feu(Etat, NouvelEtat),
     asserta(feu(NouvelEtat)),
     afficher_feu(NouvelEtat).

% Exemple d'utilisation
afficher_feu(vert).
changer_feux.
