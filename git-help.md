# git HELPFILE
Dieser Helfer für den "git workflow" ist während der ersten Gruppenarbeit an der WBS Coding School entstanden.
(WDG#012 - Hackathon1 - Gruppe3)
"Warten sie nicht! Bestellen sie noch heute ihren WishApple!"
## Der "git workflow" im Team (work in progress)
Als Ausgangspunkt für dieses Helpfile dient die Annahme das es drei Zustände in der Zusammenarbeit via GitHub gibt:
 1. [START](#1-start)
	- Anwendungsfall: **ein neues Projekt entsteht**
	 - es gibt kein Repository auf GitHub
	 - es kann Code existieren, der liegt aber nur lokal vor
 2. [COLLAB](#2-collab)
	 - Anwendungsfall: **man sucht sich Mitstreiter fürs Team**
	 - das Repository existiert auf GitHub
	 - man lädt die Teammitglieder via Repository ein, dieser erhalten Infos für die Mitarbeit
	 - jedes Teammitglied erstellt eine eigene branch
 3.  [CHANGE](#3-change)
	 - Anwendungsfall: **man soll nochmals mitarbeiten oder weiterarbeiten**
	 - das Repository existiert auf GitHub
	 - man hat bereits mitgearbeitet, dadurch kann Code lokal existieren, muss aber nicht
	 - die vorherige branch kann noch existieren, muss aber nicht


## 1. START

***online***	im Browser auf GitHub das Repository erstellen und die github-url `git-url` des erstellten Repository in die Zwischenablage kopieren (ssh)

***lokal***		lokalen Arbeitsordner erstellen und in vscode öffnen

***lokal***		in vscode, im Terminal (Git-Bash oder term) im lokalen Arbeitsordner einen initialen Befehl ausführen 

		git init
	
		// wenn man lokal dem github-standard folgt wird die branch "main" erstellt
***lokal***		Inhalte erstellen und dem lokalen git-index hinzufügen mit 
	
		git add *option*
		
		// *option* "." für alles oder selektiv mit einzelnen Dateienamen
***lokal***		die im git-index vorhandenen Inhalte werden mit dem folgenden Befehl  in ihrem zustand als _fertig_ bestätigt und somit in die staging-area verschoben

		git commit -m 'initial commit'

		// dies nennt man staging
***lokal***		das GitHub repository als remote Referenz hinzufügen mit 

		git remote add git-url
		
		// die remote Referenzen kann man mit 'git remote -v' anzeigen
***lokal***		die lokalen Inhalte, die in der staging area sind, in das remote repository schieben mit 

		git push origin main
***online***	im Browser sollten nun die Inhalte im GitHub Repository unter `git-url` erscheinen

Nun die Collaborators zur Zusammenarbeit auf GitHub einladen und dabei Rechte vergeben.

Aufgabe **Start** abgeschlossen






## 2. COLLAB

***lokal***		Arbeitsordner erstellen und in vscode öffnen

***lokal***		in vscode, im Terminal das remote repository klonen mit

		git clone git-url
		
		// main Inhalte aus dem repository sind nun lokal vorhanden
***lokal***		um an seiner Aufgabe zu arbeiten erstellt man eine *branch* mit einem aussagekräftigen Branchnamen

		git checkout -b *branch*
		
		// der Branchname sollte erkennen lassen was gearbeitet wird
***lokal***		nach durchgeführten Änderungen stellt man diese in die staging-area mit 	
		
		git add *option*
		
		// *option* "." für alles oder selektiv mit einzelnen Dateienamen
***lokal***		mit dem folgenden Befehl kann man überprüfen ob die geänderten Dateien im git-index aufgenommen wurden

		git status
***lokal***		die im git-index vorhandenen Inhalte werden mit dem folgenden Befehl als _fertig_ bestätigt und somit in die staging-area verschoben

		git commit -m 'was wurde gemacht'
		
		// mehr infos zu commit messages -> https://www.conventionalcommits.org/de/
***lokal***		um mögliche Änderungen, während man gearbeitet hat, aus der Branch *main* auf seinem lokalen Rechner aktuell zu halten sollte man vor einem `git push` in das remote repository den folgenden Befehl ausführen

		git pull origin main 

		// dies kann zu Konflikten führen die man dann lokal lösen muss, alleine oder im team
		// "main" sollte als quelle vorrang haben
***lokal***		um die lokalen Inhalte aus der staging-area in das remote repository zu übertragen wird folgender Befehl benutzt

		git push origin *branch*
***online***	im Browser auf GitHub sollten nun unter `git-url` die Inhalte in der branch *branch* auftauchen

***online***	um die Änderungen von *branch* in die branch *main* zu überführen ist ein `merge request (pull request)` von *branch* zu "main" nötig.  _Anmerkung_: dieser kann zu Konflikten führen.

***online***	falls es Konflikte gibt müssen diese in einem review (alleine oder im Team) gelöst werden

***online***	falls keine Konflikte entstehen kann der merge direkt zu "main" durchgeführt werden und die anliefernde branch gelöscht werden. _Anmerkung_: die lokale branch *branch* ist beim developer noch vorhanden!

## 3. CHANGE
***lokal***		Arbeitsordner existiert lokal noch! diesen in vscode öffnen

***lokal***		die lokalen Dateien auf den neusten stand aus dem remote repository bringen mit 

		git pull origin main
***lokal***		die gewollten Änderungen durchführen und überprüfen welche Dateien betroffen sind

		git status
***lokal***		die betroffenen Dateien dem git-index hinzufügen mit

		git add *option*
				
		*option* "." für alles 
		oder selektiv einzelne Dateienamen
***lokal***		überprüfen ob die geänderten Dateien im git-index aufgenommen wurden

		git status
***lokal***		die im git-index vorhandenen Inhalte werden mit dem folgenden Befehl als _fertig_ bestätigt und somit in die staging-area verschoben

		git commit -m 'was wurde gemacht'
***lokal***		um mögliche Änderungen, während man gearbeitet hat, aus der branch *main* auf seinem lokalen Rechner aktuell zu halten sollte man vor einem push in das remote repository folgenden Befehl ausführen

		git pull origin main 

		// dies kann zu Konflikten führen die man dann lokal lösen muss
		// "main" sollte als Quelle vorrang haben
***lokal***		um die lokalen Inhalte aus der staging-area in das remote repository zu übertragen wird folgender Befehl benutzt

		git push origin *branch*
***online***	im Browser auf GitHub sollten nun die Inhalte in der branch *branch* auftauchen

***online***	um die Änderungen von  *branch* in die branch *main* zu überführen ist ein *merge request* (pull request) von *branch* zu *main* nötig. _Anmerkung_: dieser merge request kann zu Konflikten führen

***online***	falls es Konflikte gibt müssen diese in einem review (alleine/team) gelöst werden

***online***	falls keine Konflikte entstehen kann der merge direkt zu "main" durchgeführt werden und die anliefernde *branch* gelöscht werden. _Anmerkung:_ die lokale *branch* ist beim developer noch vorhanden! Beim nächsten push in die *branch* wird diese aber wieder im remote repository erstellt und sichtbar.
