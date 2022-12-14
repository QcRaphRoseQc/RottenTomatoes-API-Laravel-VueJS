# Rotten Tomatoes


# Images

<p align="center">
<img src="./img/HomePage.png"
     alt="HomePage"
     style="margin-right: 10px;" />
</p>

<p align="center">
<img src="./img/Recherche.png"
     alt="Recherche"
     style="margin-right: 10px;" />
</p>

<p align="center">
<img src="./img/Film.png"
     alt="Film"
     style="margin-right: 10px;" />
</p>

<p align="center">
<img src="./img/Profil.png"
     alt="Profil"
     style="margin-right: 10px;" />
</p>

<p align="center">
<img src="./img/AdminMenu.png"
     alt="AdminMenu"
     style="margin-right: 10px;" />
</p>

<p align="center">
<img src="./img/Login.png"
     alt="Login"
     style="margin-right: 10px;" />
</p>

<p align="center">
<img src="./img/Register.png"
     alt="Register"
     style="margin-right: 10px;" />
</p>

Lien Front End  = https://rotten-frontend.herokuapp.com <br>
Lien Back End(API) = https://vuetp3.herokuapp.com/

Login Admin = admin/admin1234

<h1>Code Source </h1>

FrontEnd : 

1) npm -i 

2) npm run serve

BackEnd : 

Modifier le .env pour vos info de BD dans le folder backend<br>
Ensuite entrer les commandes suivantes:

1) composer update --no-scripts

2) php artisan migrate ( la premiere fois ) 

3) php artisan db:seed ( la premiere fois ) 

4) php artisan serve

-----------------------------------------------------------------

Pour se créer un user avec l'api 

dans postman: 

1) Headers = Accept application/json

2) Body = raw Json

users/register POST:

    {
        "login" : "admin",
        "password" : "admin2002",
        "email" : "admin@gmail.com",
        "last_name" : "admin",
        "first_name" : "admin",
        "role_id" : "1"
    }

role_id 1 = admin 
role_id 2 = user


Voici les Routes du backend

|ROUTE | ACTION | DESCRIPTION |
|------|--------|-------------|
| films                    | GET        | Consultation des films (sans critiques et sans acteurs)   |
| films/actors/{id}        | GET        | Consultation de tous les acteurs d’un certain film        |
| films/critics/{id}       | GET        | Consultation d’un certain film avec ces critiques         |
| films/search             | GET        | Recherche de films                                        |
| films                    | POST       | Ajout d’un film (seulement si admin)                      |
| films/{id}               | DELETE     | Suppression d’un film (seulement si admin)                |
| users/register           | POST       | Ajout d’un nouveau user                                   |
| users/login              | POST       | Connexion d’un user                                       |
| users/{id}               | GET        | Consultation des informations d’un certain user           |
| users/logout             | POST       | Déconnexion d’un user                                     |
| users                    | PUT        | Modification d’un user existant                           |
| users/password           | PUT        | Modification du Mot de Passe                              |
| critics                  | POST       | Ajout d’une critique (seulement si membre connecté)       |

Exemple de requête json avec Postman:

films POST:
        
    {            
        "title": "Raph Contre Attack",
        "release_year": "2006",
        "length": 48,
        "description": "A Astounding Epistle of a Database Administrator And a Explorer who must Find a Car in Ancient China",
        "rating": "G",
        "language_id": 1,
        "special_features": "Trailers,Deleted Scenes",
        "image": "null"
    }

users/register POST:

    {
        "login" : "admin",
        "password" : "admin2002",
        "email" : "admin@gmail.com",
        "last_name" : "admin",
        "first_name" : "admin",
        "role_id" : "1"
    }

users/login POST:

    {
        "login" : "admin",
        "password":"admin2002"   
    }

films/search GET:

    {
    "keywords":"A",
    "max_length" : "150",
    "rating" : "G"
    }


