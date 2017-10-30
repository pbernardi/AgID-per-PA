Istruzioni di installazione del CRUSCOTTO di GESTIONE Misure SICUREZZA

Istruzioni per l’ACQUISIZIONE MATERIALE

A – Scaricare sul PC XAMPP (Prodotto libero) suggeriamo il link: https://www.apachefriends.org/download.html
Nella versione più adatta al PC in dotazione, selezionate la versione con PHP 7.x.x.<br>
NB. La versione a 32 bit funziona anche su macchine dotate di SO a 64 bit.

B – Scaricare da GitHub il ProgettoAgid_3 <b>solo</b> tramite il pulsante <b>“Clone or download”</b> situato in alto a destra<br>
<b>NB. NON SCARICARE i file singolarmente in quanto questo determinerà il malfunzionamento dell'applicativo</b>

Istruzioni per l’INSTALLAZIONE

1. Installare Xampp ed attivare Mysql e Apache.

2. Modificare il path di sistema, per farlo digitare da finestra prompt di DOS il comando:

	   setx path "%path%;c:\xampp\php\"

   Se corretto comparirà la risposta:

	   OPERAZIONE RIUSCITA: valore specificato salvato

3. Creare una cartella chiamata "sicurezza" sul disco C. (C:\sicurezza)

4. Copiare in C:\sicurezza l'intera cartella del progetto “ProgettoAgid_3”

5. Aprire una finestra di prompt DOS con path della cartella in cui si trova il progetto (“C:\sicurezza\ProgettoAgid_3”) e digitare i seguenti comandi:

	   php artisan config:cache (Risposta – Configuration chache cleared!
	 			                Configuration successfully!)
           php artisan key:generate (Risposta- Application key ..)

6. Dalla cartella C:\sicurezza\progettoagid_3 selezionare il file

	   .env

Aprirlo con editor di testo per poterlo “EVENTUALMENTE” modificare. Se si sono seguite le precedenti istruzioni, i parametri indicati non necessitano di modifica.

	-DB_CONNECTION: è il tipo di DBMS che si utilizza (mysql)
	-DB_HOST: è l'indirizzo IP del database server (127.0.0.1)
	-DB_PORT: è la porta del server su cui è creata la connessione (cambiarla SOLO se è stata quella standard, 3306)
	-DB_DATABASE: è il nome del DB su cui si vogliono registrare i dati (di default è progettoagid_3)
	-DB_USERNAME: è l'username con cui si accede alla connessione del server su quel database (di default è root)
	-DB_PASSWORD: è la password con cui si accede alla connessione del server su quel database (di default non c'è)

7. Creare sul DB un nuovo database denominato "progettoagid_3", per fare questo aprire tramite un qualsiasi browser il link sotto riportato:

	   http://localhost/phpmyadmin/
	
8. Riaprire la finestra prompt del DOS e digitare il comando:

	   php artisan migrate

Questo genererà la struttura del database. Se a buon fine comparirà la sequenza:
				
	   Migration table created successfully.
  	   Migrating: 2014_10_12_000000_create_users_table
  	   Migrated: 2014_10_12_000000_create_users_table
  	   Migrating: 2017_09_08_070915_create_cruds_table
  	   Migrated: 2017_09_08_070915_create_cruds_table
	   Migrating: 2017_09_17_215219_create_files_table
	   Migrated: 2017_09_17_215219_create_files_table
 	   Migrating: 2017_10_06_112053_create_links_table
 	   Migrated: 2017_10_06_112053_create_links_table

9. Copiare i dati della cartella “DUMPDATABASE.zip” in una directory di appoggio, poi importarli nel database, ritornare al browser aperto sulla gestione del DB MySQL e selezionare “IMPORTA”. Dopo aver seleziona “Sfoglia”, si dovranno selezionare (una alla volta) TUTTI i file presenti nella directory di appoggio prima indicata; dopo averne selezionato uno dei file e’ necessario completare l’importazione di quel singolo file premendo il pulsante “Esegui” in fondo alla finestra.
Questa operazione va ripetuta per tutti i file presenti nella Directory di appoggio.

10. Attivare il Server Web del SW di appoggio LARAVEL digitando nella finestra prompt del DOS il seguente comando:

		php artisan serve

se il comando va a buon fine comparirà

        Laravel development server started: <http://127.0.0.1:8000>

LASCIARE APERTA QUESTA FINESTRA DOS

11. Aprire un Browser al link:

	    http://localhost:8000

e si verrà condotti alla pagina di login

12. Accedere con il nome utente "sicurezza" e password "sicurezza123" e verificare il riconoscimento e l’apertura del programma.

A questo punto la procedura di caricamento dell'applicazione e’ terminata.



Treviso 28.10.2017


