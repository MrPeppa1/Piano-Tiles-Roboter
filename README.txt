 2. Aufgabenstellung

In der Projektarbeit soll eine Aufgabenstellung aus dem Elektrotechnikbereich sowie dem Anwendungsentwicklungsbereich selbststaendig bearbeitet werden. Die Aufgabenstellung soll praxisbezogen und komplex sein. Ich habe mir dazu den Piano-Tiles Roboter ausgedacht. Der soll auf einem Smartphone das Spiel ÑPiano-Tilesì Spielen koennen.

3. Projektziele

Die einzelnen Teile des Roboters sollen sinnvoll zusammenarbeiten und der Roboter muss das Spiel selbststaendig und automatisch Spielen koennen. Der Mikrocontroller ist per Usb mit dem PC verbunden und uebertraegt die Sensordaten.

4. Kurze Allgemeine Erklaerung zu ÑPiano-Tilesì

Piano-Tiles ist ein ein Einzelspieler-spiel, entwickelt von Umoni Studio, fuer Android, IOS und Windows-Phone, in dem man 4 Vertikale reihen auf dem Bildschirm hat, in denen sich schwarze Tasten auf einem weiﬂen Hintergrund von oben nach unten bewegen, die man nacheinander antippen muss um an das ziel zu gelangen. Es gibt verschiedene Modi, die sich in einigen Kleinigkeiten voneinander unterscheiden, was aber die Funktionalitaet des Roboters in den meisten Faellen nicht beeintraechtigt.

5. Projektverlauf

Ich hatte die Idee zu diesem Projekt schon bevor die Schule dieses Projekt startete, also sah ich in dieser Projektarbeit die Chance meine Idee zu verwirklichen, da ich selbst sehr gespannt auf des Ergebnis war. Es hieﬂ wir sollen Gruppen bilden, um das Projekt zu bewaeltigen. Ich schloss mich dazu mit Ciar·n Schmidt zusammen, und wir fingen an zu planen. Es verging eine weile bis wir die

Logik des Projekts verstanden hatten, und eine erste Skizze zeichnen konnten. Auch ueberlegten wir, wie viel Arbeit es wohl sein wird und wie viel Zeit wir brauchen werden. Nun war es so, das Ciar·n in der darauf folgenden Schulwoche fehlte und ich ihn daraufhin per E-Mail kontaktierte. Er meinte nur dass er krank sei und die naechste Woche wieder gesund werde. Es stellte sich heraus, dass er gar nicht mehr kam und ich das Projekt alleine machen muesse. Also erkundigte ich mich im Internet, ob es schon aehnliche oder gar gleiche Projekte wie meins gibt, um mir Ideen zur genauen Funktionsweise einzuholen. Es gab zwei Loesungswege

Loesungsweg 1

Mechanische ìFingerì, die mit bestimmten Materialien an den spitzen den Fingerdruck auf dem Touchscreen simulieren. Jedoch ist dies aufwendig, weil man erst eine solche Konstruktion bauen muss, die schnell und so einfach wie moeglich den Fingerdruck simulieren.

Loesungsweg 2

Mit bestimmten teilen, die auf dem Bildschirm liegen wird ein Leiter mit Erdung also aehnlich des menschlichen Fingers simuliert, der den Touchscreen an der stelle ausloest. Mit diesem Loesungsweg ist es viel einfacher, schneller und effektiver die Fingerdruecke zu simulieren, also entschied ich mich diesen Loesungsweg zu verwirklichen.

Daraufhin machte ich mir Gedanken ueber die Schaltung bzw. den Schaltplan zur Erkennung der schwarzen Tasten mithilfe von Fotowiderstaenden und dem Mikrocontroller.

Diese liefern analoge Werte zu dem Mikrocontroller, damit der entscheiden kann, ob jetzt eine schwarze oder eine weiﬂe taste unter dem Fotowiderstand ist. Dementsprechend gibt er entweder den Befehl zum druecken oder nicht druecken an die ÑDrueckerì.

Danach ueberlegte ich mir wie ich den Ausgangsstrom (den Drueckbefehl) in einen Fingerdruck auf dem Touchscreen umwandeln koennte. Dieses Problem hat die meiste Zeit in Anspruch genommen, denn mein Ziel war es dies zu schaffen, ohne mechanische Teile zu benutzen. Ich habe auf diversen Websites gesucht und Foren durchstoebert um die Perfekte Loesung zu finden.

Es werden vier 1 Cent-Muenzen (fuer jede Reihe eine) auf den Touchscreen gelegt.

Wenn man nur eine Muenze durch ein Kabel mit einer Erdung verbindet, denkt der Touchscreen dass ein Finger ihn an der stelle beruehrt hat und schaltet dementsprechend.

Irgendwann entschloss ich mich ein paar Elektroteile einzukaufen und die theoretischen Ideen in der Praxis umzusetzen. Also besorgte ich mir ein Mosfet und ein Breadboard. Dazu noch ein paar Steckkabel und einen Summer.

Im Internet schaute ich mir das Datenblatt zum Mosfet an, um zu verstehen wie es anzuschlieﬂen ist. Danach probierte ich eine funktionierende Schaltung mit dem Summer aufzubauen.

Ich hatte einige Probleme damit die Schaltung alleine zusammenzubauen, aber nach ein bisschen tuefteln habe ich herausgefunden, wie es richtig angeschlossen wird. Das war jedoch nur ein Test, um zu sehen ob das alles so funktioniert. Ein paar Tage spaeter besorgte ich mir Fotowiderstaende, um diese naeher kennenzulernen. Stundenlang saﬂ ich da und versuchte eine Schaltung zu bauen, die die Werte des Fotowiderstandes auswerten kann.

Ich bemerkte, dass die Schaltung mir nur analoge Werte zurueckgeben muesste, damit ich sie auswerten koenne, also habe ich eine solche Schaltung aufgebaut, und ausprobiert. Nun stellte ich mit bedauern fest, dass der Msp430 Mikrocontroller, den wir benutzen keine analogen Daten lesen kann.

Also suchte ich nochmal im Internet und fand raus, das die anderen Projekte, die meinem aehneln alle mit einem Arduino Mikrocontroller umgesetzt wurden.

Bei diesem Modell ist es moeglich von Pin PC0 bis PC5 analoge Daten im Wertebereich 0 bis 1024 einzulesen.

Ich musste also nur noch alles irgendwie miteinander verbinden und den Code fuer den Arduino schreiben. Erst muss das Layout fuer die Pins ausgewaehlt werden, obwohl es da nicht viel Auswahl gibt, denn ich brauche fuer den Eingang von den Analogsignalen 4 von 6 Pins, die sich auf der einen Seite des Arduino befinden. Und ich brauche 4 digitale Pins auf der anderen Seite zum steuern der Relais.

Ausserdem brauchen die Relais und die Fotowiderstaende noch eine Verbindung zu Ground(Erdung). Zusaetzlich gibt es noch eine Verbindung von Vcc zu den Fotowiderstaenden, als Stromversorgung.

Auf dem Foto sieht man welcher Analogpin fuer welchen Digitalout-Pin zustaendig ist. Rechts sind die analogen Eingaenge, die werte, die sich aus diesen ergeben werden in der Codelogik ausgewertet und wenn der wert eine definierte Zahl ueberschreitet, wird der zugehoerige Digitalpin auf HIGH umgeschaltet.

Erst werden die pins initialisiert, indem sie in der Setup Methode alle auf die richtigen werte gesetzt werden.

Erst wird der Modus fuer den bestimmten Pin auf Output gesetzt, dann wird auf ihn zugegriffen und er wird auf LOW gestellt, also 0Volt Ausgangsstrom.

Hier sieht man, wie der Analogpin ausgelesen wird und direkt verglichen wird. Wenn der wert kleiner als 700 ist,

wird im ersten Schritt der digitale Pin auf HIGH, also an gestellt, sodass aus diesem nun ~5Volt flieﬂen. Dann wird ein ÑDelayì eingeschaltet, um sicherzustellen, dass der Touchscreen den ÑFingerdruckì auch registriert. Dieser wird in Millisekunden angegeben. In diesem Fall ist der unter der variable delay21 gespeichert.

Direkt danach wird der digitale Pin wieder auf LOW, also 0Volt gestellt.

Danach wird wieder gewartet, bevor die naechste Schleife anlaeuft.

Dieser Vorgang wird 4 mal wiederholt, fuer jeden Fotowiderstand einmal.

Als ich alles verkabelt habe, und den code auf den Arduino compiliert habe, funktionierte alles wunderbar. Abgesehen vom Touch. Der Bildschirm reagierte komischerweise nicht auf die Fingerdrucksimulation. Ich habe an diesem Problem lange herumgetueftelt, bis ich bemerkte, dass das Handy an der selben Erdung wie der Arduino angeschlossen sein muss.

Als ich das Handy sowie auch den Arduino an den selben Laptop anschloss hatten sie die gleiche Erdung, und nun funktionierte auch das Programm. Und die Fingerdrucksimulation.

Nun Ging es zuguterletzt an die GUI, die in Java geschrieben werden sollte.

Ich habe den GUI-Builder von Netbeans benutzt um eine einfache GUI zu bauen, mit einem StartStop Button und einem Textfeld. Diese GUI zeigt die Anzahl aller Klicks des Roboters.

Es Gibt zahlreiche Schnittstellen, die einem helfen, den Arduino mit einem Java Programm zu vereinen um z.B. eine Grafische Oberflaeche zu erzeugen, die dem Nutzer des Mikrocontrollers eine erleichterte Bedienung ermoeglicht. Da ich alleine an dieser GUI arbeiten musste, wollte ich sie lieber einfach halten, um Probleme zu vermeiden. 