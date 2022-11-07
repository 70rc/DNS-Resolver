# Firefox mit DoH

Mozilla hat DoH ab Firefox Version 62 integriert.


## Grundeinstellung

Diese Einstellungen sind alle per grafischem User Interface (GUI) durchführbar und können relativ einfach und schnell konfiguriert werden.

  0. Öffne die _Einstellungen_ via _Extras_ im Menü.
  0. Scrolle im Bereich _Allgemein_ ganz nach unten und wähle in der Sektion Verbindungs-Einstellungen den Knopf _Einstellungen_.
  0. Aktiviere _DNS über HTTPS aktivieren_ und wähle Benutzerdefiniert. Im neuen Feld nun URL `https://dns.digitale-gesellschaft.ch/dns-query` eingeben.

![Firefox mit DoH konfigurieren](img/ff-doh-EN.png)


## Experten

Diese Konfigurationsvorschläge richten sich an sehr erfahrene Personen. Es muss zum Teil Drittsoftware nach installiert werden oder Einstellungen in den Konfigurationsdateien angepasst werden.

Firefox kann DoH im Strict Mode verwenden. Dazu sind Anpassungen in about:config nötig:

- network.trr.custom_uri = https://dns.digitale-gesellschaft.ch/dns-query
- network.trr.mode = 3

Die verschiedenen Modi von network.trr.mode:

- Wert 3: Verwende nur DoH (DoH-only Mode)
- Wert 2: DoH wird präferiert aber reguläres DNS ist auch möglich (Doh-first Mode / default Einstellung)
- Wert 1: FF wählt zwischen DoH und DNS (das schnellere)
