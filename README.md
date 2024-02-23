# GDI+
Eine Sammlung von Tipps und Tricks zum Thema Grafikprogrammierung mit GDI+.

## Klassen / Ereignisse
### Timer
Ein Timer führt in regelmäßigen Abständen ein `Tick`-Event aus. Der [`System.Windows.Forms`.`Timer`](https://learn.microsoft.com/de-de/dotnet/api/system.windows.forms.timer?view=windowsdesktop-8.0&viewFallbackFrom=net-6.0) kann über die Toolbox auf die GUI gezogen werden. 

Anschließend können wir 
- die Zeit zwischen jedem `Tick`-Event einstellen (`+ Interval { get; set; }: int`) und
- den Timer starten (`+ Start():void`) oder
- stoppen (`+ Stop():void`) oder
- den Zustand abfragen. (`+ Enabled{ get; set; }: bool`) (Standard ist ausgeschaltet: `enabled = false`)



## Tipps und Tricks
Ergänzen Sie hier die notwendigen Code-Ausschnitte, um zu zeigen, wie man es macht. 
- Sie können [CodeBlöcke mit Syntax-Highlighting](https://docs.github.com/en/get-started/writing-on-github/working-with-advanced-formatting/creating-and-highlighting-code-blocks#syntax-highlighting) einsetzen
- Wird es zu unübersichtlich? Sie können auch Unterordner mit Beispiel-Code anlegen und auf die entsprechenden Dateien verlinken. [Inspiration](https://github.com/gsoTH/flaskShowcase/tree/master/datenbanken).
- Die folgende Liste kann gerne ergänzt werden :)

### Bewegung animieren

### Objekte mit Tasten steuern

`Rectangle spieler;`



-Mit einem If statment kann ich sagen welche Taste für welche bewegung des Objektets zuständig ist.

- Sorgt dafür das der Spieler nach oben läuft

`if (e.KeyCode == Keys.Up)
{
        spieler.Y -= hoeheJeBereich;
}
`

-Sorgt dafür das der Spieler nach unten läuft

`if (e.KeyCode == Keys.Down)
{
        spieler.Y += hoeheJeBereich;
}
`

-Sorgt dafür das der Spieler nach Links läuft

`if (e.KeyCode == Keys.Left)
{
        spieler.X -= breite / anzahlBereiche
}
`

-Sorgt dafür das der Spieler nach Rechts läuft

`if (e.KeyCode == Keys.Right)
{
        spieler.X += breite / anzahlBereiche;
}
`

### Verhindern, dass ein Spieler aus dem Bild läuft


`static int anzahlBereiche = 6;`

`int breite = -1;`

`int hoehe = -1;`

`int hoeheJeBereich = -1;`

`Rectangle[] alleBahnen = new Rectangle[anzahlBereiche];`

`Rectangle spieler;`


-Mann kann mit eine if Statment prüfen ob das Objekt den angegeben Spielbereich verlassen möchte oder nicht und so die Bewegung des Objekts einschrenken
dass das Spielfeld nicht verlassen werden kann. 

- Spieler darf nicht nach oben aus dem Spielfeld laufen

`if (e.KeyCode == Keys.Up)
{
    if (spieler.Y - hoeheJeBereich >= 0) // Überprüfen, ob die Bewegung nach oben innerhalb des Spielfelds bleibt
    {
        spieler.Y -= hoeheJeBereich;
    }
}
`


-Spieler darf nicht nach unten aus dem Spielfeld laufen

`if (e.KeyCode == Keys.Down)
{
    if (spieler.Y + spieler.Height + hoeheJeBereich <= hoehe) // Überprüfen, ob die Bewegung nach unten innerhalb des Spielfelds bleibt
    {
        spieler.Y += hoeheJeBereich;
    }
 }
 `

-Spieler darf nicht nach links aus dem Spielfeld laufen

`if (e.KeyCode == Keys.Left)
{
    if (spieler.X - breite / anzahlBereiche >= 0) // Überprüfen, ob die Bewegung nach links innerhalb des Spielfelds bleibt
    {
        spieler.X -= breite / anzahlBereiche;
    }
}
`

-Spieler darf nicht nach rechts aus dem Spielfeld laufen

`if (e.KeyCode == Keys.Right)
{
    if (spieler.X + spieler.Width + breite / anzahlBereiche <= breite) // Überprüfen, ob die Bewegung nach rechts innerhalb des Spielfelds bleibt
    {
        spieler.X += breite / anzahlBereiche;
    }
}
`
  
### Spiel pausieren

### Ihr schönstes Ergebnis





