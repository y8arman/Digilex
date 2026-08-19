Digilex Quiz
Multiplayer-Townhall-Quiz zu "Digilex - Das Epos der VD". Die komplette App
steckt in einer einzigen Datei (index.html): kein Build, keine Installation,
gehostet auf GitHub Pages, Spielstand live über Firebase Realtime Database.
Live: https://y8arman.github.io/digilex-quiz/
Funktionen
Host-Ansicht (Beamer) und Teilnehmeransicht (Handy), Beitritt per 6-stelligem Code oder QR-Code
30 einmalig wählbare Avatare, maximal 30 Teilnehmende
7 Fragen (Single, Multi, Wahr/Falsch) mit Timer, Antwort nach dem Absenden fix
Punkte nach Richtigkeit und Geschwindigkeit, Teilpunkte bei Mehrfachauswahl, Serien-Bonus ab 2 richtigen Antworten in Folge
Während der Frage sieht der Host nur die Antwortanzahl, nach jeder Frage die Top 3 schnellsten richtigen Antworten
Keine öffentliche Rangliste ausser den Top 3 im Finale, alle anderen erhalten ein persönliches Held:innenprofil
CSV-Export der Ergebnisse, kein Sound
Deployment
Neues Repository anlegen (Public), z. B. digilex-quiz.
index.html und README.md hochladen ("uploading an existing file"), Commit.
Settings, Pages, Branch main und "/ (root)", Save. Nach 1 bis 2 Minuten live.
Firebase: In dieser index.html ist bereits ein Firebase-Projekt eingetragen.
Für ein eigenes Projekt die vier Schritte im Kommentarblock
FIREBASE-KONFIGURATION in der index.html ausführen und die Werte ersetzen.
Vor dem Einsatz testen
Als Host anmelden (Admin-Code: Feld hostPassword im Block QUIZ-DATEN der
index.html, vor dem Einsatz ändern). In der Lobby Taste B drücken: pro Druck
spielen 5 Bots automatisch mit. Eine Runde durchspielen, mit dem Handy per QR
beitreten, danach "Session zurücksetzen".
Fragen ändern
Alle Inhalte stehen in der index.html im Block QUIZ-DATEN: Titel, Admin-Code,
Fragen, Podiumstexte, Held:innenprofile. Die App prüft die Fragen beim Laden
automatisch und meldet Fehler sichtbar (Details in der Browser-Konsole, F12).
Datei im Repo ändern: Datei anklicken, Stift-Symbol, bearbeiten, Commit.
Firebase-Regeln (wichtig)
Die Datenbank läuft im Testmodus, dessen Regeln nach 30 Tagen ablaufen
(aktuell bis 18.09.2026). Danach meldet die App "Permission denied". Fix:
Firebase-Konsole, Realtime Database, Tab Rules, Datum hochsetzen oder die
dauerhaften Regeln aus dem Kommentarblock der index.html veröffentlichen.
Technik
Vanilla JS in einer Datei, Firebase Realtime Database (compat SDK per CDN),
qrcodejs per CDN mit klickbarem Link als Fallback. Sichtbare Fehlermeldungen
mit 9-Sekunden-Timeout auf allen Firebase-Zugriffen, Verbindungsanzeige und
Versionsnummer im UI. Hinweis: Der Admin-Code ist eine Komfort-Sperre und
kein Sicherheitsmerkmal, er steht im Klartext im Quelltext.
App-Version: v2.4-single
