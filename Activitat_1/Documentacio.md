
# ACTIVITAT 1

## Fase 0
Per a poder fer aquesta activitat s'ha de tenir instalat el PostgreSQL i el Python


## Fase 1

* ### Entrar al gestor Postgre
Per a entrar al gestor Postgre ho fem al la comanda:
~~~
sudo -u postgres psql
~~~
<p align=center>
<img src=https://user-images.githubusercontent.com/91245889/192812494-a61889c6-4bd4-4c1c-abdf-3f476dcbb603.png>
</p>

Ja estariem dintre
* ### Crear una base de dades anomenada uf4jrf
Crearem la BD amb el nom indicat:
~~~
CREATE DATABASE nomBaseDeDades;
~~~
![1](https://user-images.githubusercontent.com/91245889/192812944-e4e0c25f-fc26-4885-af98-7f366bbc6b8f.png)

La base de dades ja esta creada, aprofitem també per a donar privilegis sobre la BD:
~~~
GRANT ALL PRIVILEGES ON DATABASE nomBaseDeDades TO nomUsuari;
~~~
![2](https://user-images.githubusercontent.com/91245889/192813968-8740c9fb-df06-4f7a-bfaa-36557203ca00.png)

Permisos donats correctament i finalment, entrem dintre de la BD:
~~~
\c nomBD
~~~
![3](https://user-images.githubusercontent.com/91245889/192814367-a479681a-a718-41cd-8293-0cc41cd7bd8c.png)

Ja hem entrat dintre

* ### Crear una taula anomenada estatsjrf amb els camps ID, nom i superficie

Per a crear taules ho farem indicant el nom de la taula amb els camps que contindra la taula i el tipus de dades

~~~
CREATE TABLE nomtaula (camp tipusCamp, camp2 tipusCamp2,...);
~~~
Creem la taula Estats:

![4](https://user-images.githubusercontent.com/91245889/192815548-e49bf4d1-5aca-43a3-90bd-9048e6ccae9a.png)

* ### Crear una taula anomenada ciutatsjrf amb els camps ID, nom, habitants i estat
Creem la taula Ciutats amb la comanda anterior:

![9](https://user-images.githubusercontent.com/91245889/192816134-49972eba-4293-4b11-9b59-cfb35d78d9ac.png)

Podem comprovar que s'han creat les dues taules llistant totes les taules que figuren a la BD:
~~~
\dt
~~~
![14](https://user-images.githubusercontent.com/91245889/192817197-be3b8856-27a7-42f9-a02a-295de256adb6.png)


* ### Afegir a la taula estatsjrf els estats de EEUU
~~~
INSERT INTO nomTaula (camp1,camp2,camp4) VALUES ('valorCamp1','valorCamp2','valorCamp4'),('valorCamp1','valorCamp2','valorCamp4')
~~~
![6](https://user-images.githubusercontent.com/91245889/192818884-76e6dbca-4e87-4b28-9263-fdf94859935e.png)
![7](https://user-images.githubusercontent.com/91245889/192818910-f1586d2c-1242-43ca-884a-51c3c67fcb8b.png)

Veiem que s'han indroduït els 50 estats. També ho podem fer amb un SELECT:
~~~
SELECT * FROM nomTaula;
~~~

![8](https://user-images.githubusercontent.com/91245889/192819177-5a8caf3f-3e7a-4b5b-8287-ee77823fddd1.png)

Veiem que figuren a la BD.

* ### Afegir a la taula ciutatsjrf les 30 ciutats mes poblades de EEUU
Seguint els passos de l'apartat anterior, introduim les 30 ciutats:

![11](https://user-images.githubusercontent.com/91245889/192824780-f4029fe9-dcce-4a20-8b75-ffc4c7c89545.png)
![10](https://user-images.githubusercontent.com/91245889/192824832-c4a98ca4-e12f-4b4e-97f8-2e3b8750a040.png)

Veiem que s'han indroduit correctament i ho comprovem amb un SELECT:

![13](https://user-images.githubusercontent.com/91245889/192825138-d3eb794f-4b20-47cc-bc76-34e753bc8589.png)

![12](https://user-images.githubusercontent.com/91245889/192825033-05dfbfe3-242a-4cfe-bcb7-c5c5398339e1.png)


* ### Connecteu amb la BD de Python i feu les següents consultes:
Per a fer les consultes, hem de donar permisos a les taules:
~~~
GRANT ALL PRIVILEGES ON TABLE nomTaula TO nomUsuari;
~~~
![20](https://user-images.githubusercontent.com/91245889/192825951-c74c9fd4-0373-4f1e-8a3a-718d1f29b947.png)

Un cop fet això ja podrem fer consultes. Per a fer consultes he creat un mètode que sol cal passar-li la sentencia SQL:

![15](https://user-images.githubusercontent.com/91245889/192826424-c50b9407-0c2d-4daf-afb3-6b5a50529205.png)


  * Estats amb una superficie superior a 200.000K m2

Sentencia SQL:

![17](https://user-images.githubusercontent.com/91245889/192826533-03414e30-f889-423d-abb0-5139ea1fa21d.png)

Resultat:

![16](https://user-images.githubusercontent.com/91245889/192826944-eacf57d8-bbd7-492f-a060-16bde0aed5b9.png)

  * Estats amb una superfície menor que 100.000Km2 i major a 20.000 Km2
Sentencia SQL:



Resultat:




  * Ciutats amb més de 1.000.000 habitants
Sentencia SQL:


Resultat:
  * Ciutats amb menys de 1.000.000 habitants i mes de 650.000 habitants.












