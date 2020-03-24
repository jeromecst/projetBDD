## ETAPE 1-2

ATELIER(Num_AT, Niveau, Min, Max)

HORAIRE(Jour, Créneau)

ACTIVITE(id_Act, Nom_Act, Pratique)

DISC.ART.(Num.DA, Nom_DA)

HABITANT(N_SS, Nom_Hab, Prén_Hab, Genre, Date_Nat)

BÂTIMENT(Id_Bât, Nom_Bât, Num_Rue, Rue, CP )

LOCAL(Id_Bât, Type)

IMMEUBLE(Id_Bât, Année)

APPART(Id_Bât, Num_AP, Pièces)

SALLE(Id_Bât, Etage, Num_S)

R_THÈME(Num_AT,Id_Act)

R_ANIME(Num_AT, N_SS)

R_PARTICIPE(Num_AT, N_SS)

R_PARRAINE(N_SS1, N_SS2)

R_DISCIPLINE(Id_Act, NUM_DA)

R_HABITE(N_SS, Id_Bât, NUM_AP)

R_CAPACITÉ(Id_Bât,Étage, Num_S, Num_DA, lieu_possible)

R_DANS_LOCAL(Id_Bât, Etage, Num_S)

R_DANS_2(Id_Bât, Num_AP)

R_A_LIEU(Num_AT, Étage, Num_S, Jour, Créneau)

---

R_THÈME[Num_AT] $\subseteq$ ATELIER[Num_AT]
                
R_THÈME[Id_Act] $\subseteq$ ACTIVITÉ[Id_Act]
                
R_ANIME[Num_At] $\subseteq$ ATELIER[Num_At]
                
R_ANIME[N_SS] $\subseteq$ HABITANT[N_SS]
                
R_PARTICIPE[Num_At] $\subseteq$ ATELIER[Num_At]

R_PARTICIPE[N_SS] $\subseteq$ HABITANT[N_SS]

R_PARAINE[N_SS1, N_SS2] $\subseteq$ HABITANT[N_SS]

R_DISCIPLINE[Id_Act] $\subseteq$ ACTIVITÉ[Id_Act]

R_DISCIPLINE[NumDa]$\subseteq$ DISC.ART.[NumDA]

R_HABITE[N_SS] $\subseteq$ HABITANT[N_SS]

R_HABITE[Id_Bat] $\subseteq$ BATIMENT[Id_Bat]

R_HABITE[Num_Ap] $\subseteq$ APPARTEMENT[Num_Ap]

R_LIEU_POSSIBLE[Id_Bat] $\subseteq$ BATIMENT[Id_Bat]

R_LIEU_POSSIBLE[Etage] $\subseteq$ SALLE[Etage]

R_LIEU_POSSIBLE[Num_S] $\subseteq$ SALLE[Num_S]

R_LIEU_POSSIBLE[NumDA] $\subseteq$ DISC.ART.[NumDA]

R_DANS_LOCAL[Id_Bat] $\subseteq$ BATIMENT[Id_Bat]

R_DANS_LOCAL[Etage] $\subseteq$ SALLE[Etage]

R_DANS_LOCAL[Num_S] $\subseteq$ SALLE[Num_S]

R_DANS_2[Id_Bat] $\subseteq$ BATIMENT[Id_Bat]

R_DANS_2[Num_Ap] $\subseteq$ APPART[Num_Ap]

R_A_LIEU[Num_At] $\subseteq$ ATELIER[Num_At]

R_A_LIEU[Etage] $\subseteq$ SALLE[Etage]

R_A_LIEU[Num_S] $\subseteq$ SALLE[Num_S]

R_A_LIEU[Jour] $\subseteq$ HORAIRE[Jour]

R_A_LIEU[Creneau] $\subseteq$ HORAIRE[Creneau]

---

ATELIER[Num_AT] $\subseteq$ R_THEME[Num_AT]

ATELIER[Num_AT] $\subseteq$ R_ANIME[Num_AT]

ATELIER[Num_AT] $\subseteq$ R_A_LIEU[Num_AT]

ACTIVITE[Id_Act] $\subseteq$ DISCIPLINE[Id_Act]

HABITANT[N_SS] $\subseteq$ R_HABITE[N_SS]

SALLE[Etage, Num_S] $\subseteq$ R_DANS_LOCAL[Etage, Num_S]

APPART[Num_Ap] $\subseteq$ R_DANS_2[Num_Ap]

LOCAL[Id_Bat] $\subseteq$ BATIMENT[Id_Bat]

APPART[Id_Bat] $\subseteq$ BATIMENT[Id_Bat]


## ETAPE 3

ATELIER(**NumAT**, Id_Act *NOT NULL*, Jour *NOT NULL*,Crénau *NOT NULL*, Etage *NOT NULL*, Num_S *NOT NULL*, Id_Bat_Local *NOT NULL*,  N_SS_Anime *NOT NULL* , Niveau, Min, Max)

ACTIVITE(**Id_Act**, Num_DA *NOT NULL*, Nom_Act, Pratique)

HABITANT(**N_SS**, Id_Bât_Immeuble *NOT NULL*, Num_AP *NOT NULL*, Prén_Hab, Nom_Hab, Genre, Date_Nat)

SALLE(**Etage**, **Num_S**, **Id_Bât_Local**)

APPART(**Num_AP**, **Pièces**, **Id_Bat_Immeuble**)

LOCAL(**Id_BatLocal**, Nom_Bat, Num_Rue, Rue, CP, Type)

IMMEUBLE(**IdBâtImmeuble**, NomBat, NumRue, Rue, CP, Année)

HORAIRE(**Jour**, **Créneau**)

DISC.ART.(**NumDA**, NomDA)

R_PARTICIPE(**NSS**, NumAT *NOT NULL*)

R_PARRAINE(**NSSParrain**, NSSFilleul *NOT NULL*)

R_LIEU_POSSIBLE(**Capacité**, NumDA *NOT NULL*, Etage *NOT NULL*, NumS *NOT NULL*, IdBâtLocal *NOT NULL*)

---

ATELIER[IdAct] $\subseteq$ ACTIVITE[IdAct]

ATELIER[Jour] $\subseteq$ HORAIRE[Jour]

ATELIER[Creneau] $\subseteq$ HORAIRE[Creneau]

ATELIER[Etage] $\subseteq$ SALLE[Etage]

ATELIER[NumS] $\subseteq$ SALLE[NumS]

ATELIER[IdBatLocal] $\subseteq$ SALLE[IdBatLocal]

ATELIER[NSS_Anime] $\subseteq$ HABITANT[NSS]

ACTIVITE[Num_DA] $\subseteq$ DISC.ART.[Num_DA]

HABITANT[IdBâtImmeuble] $\subseteq$ BATIMENT[IdBâtImmeuble]

HABITANT[NumAP] $\subseteq$ APPART[NumAP]

SALLE[IdBâtLocal] $\subseteq$ LOCAL[IdBâtLocal]

APPART[IdBâtImmeuble] $\subseteq$ IMMEUBLE[IdBâtImmeuble]

R_PARTICIPE[NSS]  $\subseteq$ HABITANT[NSS]

R_PARTICIPE[NumAT] $\subseteq$ ATELIER[NumAT]

R_PARRAINE[NSSFilleul] $\subseteq$ HABITANT[NSS]

R_PARRAINE[NSSParrain] $\subseteq$ HABITANT[NSS]

R_LIEU_POSSIBLE[NumDA] $\subseteq$ DISC.ART.[NumDA]

R_LIEU_POSSIBLE[Etage] $\subseteq$ SALLE[Etage]

R_LIEU_POSSIBLE[NumS] $\subseteq$ SALLE[NumS]

R_LIEU_POSSIBLE[IdBatLocal] $\subseteq$ LOCAL[IdBatLocal]

