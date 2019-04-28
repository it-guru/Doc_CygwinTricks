## Cygwin Tips&Tricks

Die Perfekte Cygwin Einrichtung bedarf einiger Tricks.

### Enviroments bereits im Windows setzen

Einige Umgebunsvariablen sollen man in der Windows Umgebung global
setzen, damit diese nicht immer bei jedem Cygwin Kommando &uuml;ber
ein Profile geladen werden m&uuml;ssen.
Also im Windows-cmd:
```markdown
setx PATH "C:\Users\hvogler\AppData\Local\Microsoft\WindowsApps;C:\Program Files\Tools"
```
Unter Windows kann man dass dann &uuml;ber ...
```markdown
Systemsteuerung
  ->System und Sicherheit
    ->System
      ->Einstellungen aendern
        ->Erweitert
          ->Umgebunsvariablen
```

### Cygwin-Setup Icon erstellen

Damit man ohne gro&szlig; Aufwand Packete hinzuf&uuml;gen bzw. aktualisieren
kann, sollte man sich ein Setup-Icon erzeugen:
```markdown
"C:\Program Files\cygwin\setup-x86_64.exe" --root "C:\root" --no-admin -n -N  -l "C:\Program Files\cygwin"
```


### Windows Auth Proxy Problem - px.exe

Auf Enterprise Windows Umgebungen wird gerne WindowsAuth f&uuml;r den
Proxy Zugriff eingesetzt.
Wenn man in einer solchen WinAuth Proxy-Umgebung arbeiten mu&szlig;, 
so kann man das durch Starten von **[px.exe](https://github.com/genotrance/px)**
l&ouml;sen. Damit wird dann unter http://localhost:3128 ein "normaler"
Proxy verf&uuml;gbar, der mit allen GNU Tools arbeitet.
Das px.exe kann einfach in der Autostart Gruppe aufgerufen werden.
Damit dann idealerweise alle Gnu-Tools global immer auf den Proxy
zugreifen k&ouml;nnen, kann das einfach in der Windows-Env hinterlegen:

```markdown
setx HTTP_PROXY "http://localhost:3128"
setx http_proxy "http://localhost:3128"
setx HTTPS_PROXY "http://localhost:3128"
setx https_proxy "http://localhost:3128"
setx FTP_PROXY "http://localhost:3128"
setx ftp_proxy "http://localhost:3128"
```

### nsswitch.conf anpassen

Damit bei gro&szlig;en Domains auch der Aufruf von cygwin Kommandos
schnell geht, sollte man die passwd und group "cachen".

/etc/nsswitch.conf
```markdown
passwd:   files #db
group:    files #db
```
### Cygwin XWin automatisch starten

Installieren muss man xinit xorg-server und xterm . Dann kann man ein
Icon mit ...
```markdown
C:\root\bin\run.exe --quote /usr/bin/bash.exe -l -c "cd; /usr/bin/startxwin"
```
... in die AutoStart einbauen.

### definieren wo das HOME liegt

Das Home-Verzeichnis in der Cygwin Umgebung lege ich gerne
in das Windows-User Home ins Verzeichnis home. Damit das dann
korrekt ausgewertet wird, muss in die nsswitch.conf die folgende
Zeile.

/etc/nsswitch.conf
```markdown
db_home:  /cygdrive/c/Users/%U/home
```


### git 


Damit man nicht immer den User-Namen und das Passwort immerwieder
eingeben mu&szlig;
```markdown
#git config --global credential.helper cache
git config --global credential.helper 'store --file ~/.my-credentials'
```
Cache alleine ist nicht gut (da mu&szlig; man nach 15min das Passwort
erneut eingeben).

Standard Anpassungen, damit git "rund" l&auml;uft.
```markdown
git config --global user.name "Vorname Nachname"
git config --global user.email "i@t"
```




<hr>

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

