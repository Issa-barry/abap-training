## abap-training

# VARIABLES 
		

data: nom type string value 'barry',
      age type i value 18,
      phone(10) type n value 0758855039,
      sexe(8) type c  value 'femme',
      periode type d,
      temps type t,

      
      periode = sy-datum.
      temps = sy-uzeit.
      
write: 'Nom:',nom,
        /'Age:',age,
        /'Phone:',phone,
        /'Sexe:',sexe,
        /'La date:',periode,
        /'Temps:',temps.
        
        
#  STRUCTURES DE  DONNEES
DATA: BEGIN OF adresse,
          street(255) type c,
          city(100) type c,
          cp(5) type n,
      END OF adresse.
      
    move '22 Rue de strasbourg' to adresse-street.
    move 'Angers' to adresse-city.
    move 49000 to adresse-cp.
    
    
    
write: 'Street:',adresse-street,
       /'Ville:',adresse-city,
       
       
       
        
 					#	CONDITIONS
 
 --Version simple---
 data: 
    a type i,
    b type i,
    resultat type p LENGTH 15 DECIMALS 1,
    operateur type c.
   
            
    a = 2.
    b = 3.
    operateur = '/'.
    
case operateur.
    when '+'.
        resultat = a + b.
    when '-'.
        resultat = a - b.
    when '*'.
        resultat = a * b.
    when '/'.
        resultat = a / b.
        
endcase.
write: 'Resultat =', Resultat.
 
# Version complexe---
 data: 
    a type i,
    b type i,
    resultat type p LENGTH 15 DECIMALS 1,
    operateur type c.
   
            
    a = 5.
    b = 4.
    operateur = 'L'.
    
    if ( operateur = '+' or operateur = '-' or operateur = '*' or operateur = '/' ).
    
             case operateur.
                when '+'.
                    resultat = a + b.
                    
                when '-'.
                    if ( a > b ).
                        resultat = a - b.
                    else.
                        resultat = b - a.
                    
                    endif.
                    
                when '*'.
                    resultat = a * b.
                    
                when '/'.
                    if ( b > 0 ).
                        resultat = a / b.
                    else.
                        write 'Impossible de diviser a/b !!'.
                    endif.
        endcase.
        
        write: /'Resultat =', Resultat.
 
    else.
        write: 'Operateur',operateur,',est invalide !'.
    endif.
 


       
 					#	BOUCLES

 
 Exemple 1:
 	data: i type i.

	i = 0.

	WHILE i <> 5.
	    write: /'Ligne:',i.
	    i = i + 1.
	endwhile.
	
Exemple 2:
	data i type I value 0.

	do 5 times.
	    write: /'Ligne',i.
	    
	    i = i + 1.
	enddo.
 
 

 						# TABLE INTERNE/TABLEAUX

Exemple 1:
	 types t_pr(20) type c.

	data list_p type standard table of t_pr.
	
	
Exemple 2:
	TYPES: begin of ty_personne,
		    nom      TYPE c length 10,
		    prenom  TYPE c length 10,
		    age       TYPE i,
		    end of ty_personne.

	DATA it_personnes TYPE STANDARD TABLE OF ty_personne.
	
 
 
 
 
 
