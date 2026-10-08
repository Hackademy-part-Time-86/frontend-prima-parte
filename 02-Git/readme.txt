Git è un distrubited version control system

version control system cioè un sistema utile a tenere traccia di cambiamenti apportati al progetto
distrubited ci permette di lavore in team

Chi ha windows
git bash

Per chi ha il mac è necessario eseguire sul terminale:
xcode-select --install


# Configurare git
git config --global user.name "Eric Cartman"
git config --global user.email "ericcartman@gmail.com"


# Introduzione
- Repository è una struttura dati (un contenitore di dati). Una Repository è formata da uno o più branch. 
- un branch è una linea di sviluppo nel tempo che tiene traccia di come un progetto si evolve nel tempo (history del progetto).
Un branch è formato da commit
- un commit è una istantanea del progetto


# Repository
All'atto pratico, una Repository è una directory nascosta .git all'interno della directory del progetto

Per creare una nuova Repository è necessario aprire il terminale all'interno della directory del progetto ed eseguire (one time):
git init


Al momento della creazione della Repository viene contemporanemente creato un branch che di default si chiama master (da rinominare in main)

untracked




# Staging area
Una sorta di "anteprima di stampa" (cioè una anteprima del commit)
Tutti i file presenti nella Staging area andranno a formare il prossimo commit

Per inserire i file dalla working directory (la cartella del progetto) dentro la staging area:
    git add nomeDelFile
ad esempio:
    git add index.html

git add .

Per visualizzare lo stato della staging area:
git status



# Commit
A partire dai file presenti nella staging area posso creare un nuovo commit
Un commit è una istantanea del progetto (cioè una fotografia)

git commit -m "qui un messaggio descritto del commit"

Per visualizzare i commit
git log
git log --oneline


I passi da eseguire saranno:
1) git init (una sola volta)
2) git add .
3) git commit -m "qui un messaggio descritto del commit"
Ripetere gli step 2 e 3 quanto basta per creare nuovi commit






Servizio di hosting per Repository git tra questi:
- GitHub
- GitLab
- ...


# Configurazione GitHub
E' necessario collegare il profilo GitHub con l'utente del sistema operativo.
Per far ciò è necessario creare una coppia di chiavi pubblica e privata eseguendo il comando all'interno della directory home dell'utente:
    ssh-keygen

Per rinominare il branch da master a main è necessario eseguire:
git branch -M main


Il comando git remote permette di collegare la Repository locale con la sua corrispondente Repository remota all'URL 
Il termine origin è un alias per l'URL specificato
git remote add origin git@github.com:kuttino/Instagram.git

Il comando git push permette di effettuare l'upload dalla repo locale alla repo remota del contenuto del branch specificato
git push URLRepoRemota nomeDelBranch
ad esempio
git push origin main


# Procedura repo locale e remota
1) git init (una volta sola)
2) git add .
3) git commit -m ""
4) git remote add ... (una sola volta)
5) git push origin main
Ripetere gli step 2, 3, 5 quanto basta



Il comando git clone (one time) permette di copiare l'intero progetto e l'intera repository remota a formare una repo locale
git clone URLRepoRemota
ad esempio
git clone git@github.com:kuttino/Instagram.git



Il comando git pull permette di effettuare il download del contenuto del branch specificato della repo remota verso la repo locale
git pull origin main


Potrebbero nascere dei conflitti se due utenti modificano le stesse righe negli stessi file in particolare quando non avete effettuato il git pull scaricando i nuovi aggiornamenti dalla repo remota
La risoluzione di un conflitto terminano con un commit!