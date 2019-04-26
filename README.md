## Cygwin Tips&Tricks

Die Perfekte Cygwin Einrichtung bedarf einiger Tricks.

### nsswitch.conf anpassen

Damit bei grossen Domains auch der Aufruf von cygwin Kommandos
schnell geht, sollte man die passwd und group "cachen".

```markdown
passwd:   files #db
group:    files #db
```


### git


- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text


For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

