## Cygwin Tips&Tricks

Die Perfekte Cygwin Einrichtung bedarf einiger Tricks.

### nsswitch.conf anpassen

Damit bei gro&szlig;en Domains auch der Aufruf von cygwin Kommandos
schnell geht, sollte man die passwd und group "cachen".

```markdown
passwd:   files #db
group:    files #db
```


### git 

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

