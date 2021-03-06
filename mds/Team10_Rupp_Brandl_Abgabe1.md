Team10 - Moritz Rupp, Viktor Brandl
# 1.5 Kontrollfrage

Bearbeitet von Moritz Rupp und Victor Brandl

## Frage 1.1
>Beim ersten Login auf ihren neuen Maschinen über SSH wurden Sie mit einer
(ja/nein) Frage begrüßt. Welchen Sinn hatte diese Frage und was geschieht, wenn Sie diese
mit Ja beantworten.

Der Fingerprint des Remote-Servers wird mit denen bekannter Verbindungen abgeglichen. Damit bestätigt man dessen Identität. Wenn die Identität nicht bestätigt werden kann, kommt die Meldung.

Wird mit Ja geantwortet, wird der **Public-Key** gehashed in die Datei "**/.ssh/known_hosts**" geschrieben.

## Frage 1.2
>Welche Funktion hat die Datei sources.list und in welchem Zusammenhang
steht sie zur Sicherheit eines Systems?

Hier werden Paketquellen gelistet. Hier können Sicherheitskonfigurationen zu den einzelnen Paketquellen vorgenommen werden um z.B. Teile von **apt-secure** zu umgehen.

## Frage 1.3
>Was steht in der Datei /.ssh/authorized_keys und was bedeutet es, wenn
man einen Eintrag in ihr erstellt?

Hier legt ein Nutzer seine Public-Key ab bzw. ein Remote-Server seinen Private-Key. Diese werden unter anderem als Login-Credentials für den Client genutzt.
Mit ssh-keygen kann ein neuer Eintrag generiert werden, mit dem sich ein Nutzer auf einem Server identifizieren kann.

## Frage 1.4
>Warum war es nötig, die Benutzerrechte des Home Verzeichnisses von lab99 zu
ändern und welche Kommandos stehen dazu zur Verfügung?

>Um dem Benutzer die rechte 'Read', 'Write', 'Execute' zu gewähren. Anfangs wird user anhand von useradd -u 8000 -g lab99 -G sudo -m erstellt. '-m' legt hierbei das home verzeichnis an. Anschließend werden mit chmod 700 die benötigten rechte vergeben!
Das alles um lese- Schreiberechte zu gewähren die unseren Fortschritt auf der lab99 Domain analysieren und anzeigen.

## Frage 1.5
>Welche Rolle spielt die Zeitsynchronisation bei der Sicherheit eines Netzwerkes?
Nennen Sie Dinge, die schief gehen können, wenn keine gemeinsame Systemzeit zwischen
den Systemen vorliegt.
>Bei Auswertung von Protokolldateien. Für Autorisierung und Authentifizierung, Gültigkeit von Tokens etc.
- Konflikte bei Replikation. ---> Welche Datei ist die aktuellste?!
- Gültigkeit bzw. Ablauf von Zertifikaten/Schlüsseln etc.
