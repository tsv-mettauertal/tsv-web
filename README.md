tsv-web
=======

[![hugo-deploy](https://github.com/tsv-mettauertal/tsv-web/actions/workflows/hugo-deploy.yml/badge.svg)](https://github.com/tsv-mettauertal/tsv-web/actions/workflows/hugo-deploy.yml)

Das ist das [Hugo](https://gohugo.io)-Projekt für den Webauftritt des TSV Mettauertal.

Der Webauftritt ist erreichbar unter: [tsvmettauertal.ch](https://tsvmettauertal.ch).


Entwicklung
-----------

Installier Hugo z.B. unter Windows mit [Chocolatey](https://chocolatey.org/):

~~~~~~
choco install -y hugo-extended --version 0.148.2 --pin
~~~~~~

Die genau Version, welche zwingend verwendet werden muss, wird durch die Github Action definiert in:
[hugo-deploy.yml](.github/workflows/hugo-deploy.yml).

Nun kann lokal gearbeitet werden und mittels `hugo server` eine Server-Instanz gestartet werden,
die unter [localhost:1313](http://localhost:1313) erreichbar ist.
Diese aktualisiert sich bei den meisten Änderungen im Projekt automatisch.

Alternativ kann auch komplett ohne lokale Entwicklungsumgebung gearbeitet werden.
Dazu existiert die Github-Action: [hugo-deploy-dev.yml](.github/workflows/hugo-deploy-dev.yml)
welche durch den `dev`-Branch ausgelöst wird und den aktuellen Stand auf
[dev.tsvmettauertal.ch](https://dev.tsvmettauertal.ch) publiziert.


### Dokumentation

* Blowfish Homepage Layout: https://blowfish.page/docs/homepage-layout/
* Blowfish Shortcodes: https://blowfish.page/docs/shortcodes/
* Blowfish Front Matter: https://blowfish.page/docs/front-matter/
* Bootstrap CSS classes: https://bootstrapshuffle.com/de/classes
* Emoji code: https://unicode.org/emoji/charts/full-emoji-list.html
* Favicon converter: https://favicon.io/favicon-converter/


Deployment
----------

Das Deployment auf den echten Web-Server passiert automatisch bei einem Push auf den `main`-Branch
durch die Github-Action: [hugo-deploy.yml](.github/workflows/hugo-deploy.yml)


Photo-Galerie
-------------

Die ausgiebige Fotosammlung wird in einem separaten Tool unter:
[gallery.tsvmettauertal.ch](https://gallery.tsvmettauertal.ch) verwaltet.
Dazu wird [Piwigo](https://piwigo.org) selber gehostet.
Bilder werden immer nur in maximal 1920x1080 Pixel hochgeladen.
Die vollaufgelösten Bilder werden in der Nextcould archiviert: `TSV_Nextcloud/VereinsArchiv/Fotos/`.

Um zufällige Bilder auf der Homepage einzubeten wird eine angepasste Version von
[piwigo-random](https://github.com/moy/piwigo-random) verwendet.
Die angepassten Dateien, welche auf `gallery.tsvmettauertal.ch/piwigo-random/` verfügbar sein müssen, findet ihr hier:
[piwigo-random](/piwigo-random/).

Um ein spezifisches Album in einem Bericht zu verlinken, kann der entsprechende Shortcode verwendet werden:

~~~~~~
{{< piwigo category=11 >}}
~~~~~~


Kontaktformular
---------------

Die Kontakt-Funktion wird über [formspark.io](https://dashboard.formspark.io) gelöst.
Wir verwenden den existierenden Workspace `TSV JTF2025`, da wir sonst neue Submissions bezahlen müssten.

Zur Bot-Bekämpfung nutzen wir: [botpoison.com](https://botpoison.com/)


SEO
---

Für die Suchmaschinen-Optimierung kann die
[Google Search Console](https://search.google.com/search-console) verwendet werden.
Dort muss vor allem das `sitemap.xml` unter
[Sitemaps](https://search.google.com/search-console/sitemaps) hinzugefügt werden.
