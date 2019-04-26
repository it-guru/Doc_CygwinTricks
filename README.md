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
Systemsteuerung
```markdown
  ->System und Sicherheit
    ->System
      ->Einstellungen &auml;ndern
        ->Erweitert
          ->Umgebunsvariablen
```

### nsswitch.conf anpassen

Damit bei gro&szlig;en Domains auch der Aufruf von cygwin Kommandos
schnell geht, sollte man die passwd und group "cachen".

```markdown
passwd:   files #db
group:    files #db
```


### git 

Wenn man in einer Proxy-Umgebung arbeiten mu&szlig; die WinNT Auth
auf dem Proxy erfordert, so kann man das durch Starten von px.exe
l&ouml;sen. Damit wird dann unter http://localhost:3128 ein "normaler"
Proxy verf&uuml;gbar, der mit allen GNU Tools arbeitet.

Damit man nicht immer den User-Namen und das Passwort immerwieder
eingeben mu&szlig;
```markdown
git config --global credential.helper cache
```

Standard Anpassungen, damit git "rund" l&auml;uft.
```markdown
git config --global user.name "Vorname Nachname"
git config --global user.email "i@t"
```




<hr>

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text


For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

