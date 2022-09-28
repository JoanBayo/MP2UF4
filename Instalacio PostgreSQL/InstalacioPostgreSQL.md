# PostgreSQL

## 1. Instal·lacio
Per a instalar el PostgreSQL, obrirem un terminal i executarem la següent comanda:
~~~
sudo apt-get install postgresql-14
~~~
Un cop executada la comanda, podem veure que comença la instal·lació.

![Selecció_001](https://user-images.githubusercontent.com/91245889/189872334-570ef3f7-40bf-4cb4-a168-202a844056eb.png)

Hi ha una comanda on podem veure si el servei de PostgreSQL es troba actiu:
~~~
service postgresql status
~~~
En la següent imatge podem veure com el servei es troba actiu.

![Selecció_002](https://user-images.githubusercontent.com/91245889/189872417-bf6f11c3-c925-4035-9aa2-d5b0d8201d3f.png)

Finalment, per comprovar que tot s'ha instal·lat correctament, accedirem a PostgreSQL amb l'usuari postgres.
~~~
sudo -u postgres psql
~~~
![Selecció_003](https://user-images.githubusercontent.com/91245889/189872495-ded020d2-1e5d-4826-9675-17f6aed644b8.png)

Un cop arribats fins aqui, ja ens trobem dintre del Sistema Gestor de Bases de Dades PostgreSQL i podem realitzar sentencies SQL.

## 2. Creació de base de dades

Primer que tot, crearem una base de dades amb el nom de "UF4riba". Molt important posar *;* al final de cada sentència per a que s'executi.
~~~
CREATE DATABASE UF4riba;
~~~
Aquest hauria de ser el resultat i ja tindriem la base de dades creada.

![Selecció_008](https://user-images.githubusercontent.com/91245889/189877297-bead8792-cec4-4f8a-ad51-05f039a46163.png)

Podem comprovar que s'ha creat correctament, amb la comanda que ens mostra totes les bases de dades que existeixen:
~~~
\l
~~~
Veiem que es troba en ultim lloc.

![Selecció_009](https://user-images.githubusercontent.com/91245889/189877420-f9bc2ff3-ac92-476f-9c55-0945ba9d2311.png)

Ara crearem un usuari on despres li donarem tots els privilegis de la taula que hem creat abans (UF4riba). Posarem com a nom d'usuari *riba* i com a contrasenya *1234*.

~~~
CREATE USER riba WITH PASSWORD '1234';
~~~

![Selecció_005](https://user-images.githubusercontent.com/91245889/189877493-c3e1bbc7-2ede-4a1f-8343-e7e1b8ad41ef.png)

Finalment donariem permisos a l'usuari creat per a la Base de Dades.
~~~
GRANT ALL PRIVILEGES ON DATABSE UF4riba TO riba;
~~~

![Selecció_007](https://user-images.githubusercontent.com/91245889/189877464-4f61d308-f102-40a2-81f8-ee8829b882bd.png)

Ja hauriem creat una Base de Dades amb un usuari amb tots els permisos necessaris per a explotar la taula.
