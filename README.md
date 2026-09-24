# TicketSystem Mobile PoC

Testbare mobile-first PWA für den TicketSystem-Prototyp.

## Was du testen kannst

- Ticketliste mit Beispiel-Tickets
- Neues Ticket anlegen
- Titel, Beschreibung und Priorität erfassen
- Kamera direkt öffnen
- Mehrere Fotos aus Kamera/Galerie auswählen
- Foto-Vorschau
- Admin/User-Modus umschalten
- Admin-Dashboard mit KPI-Karten und Statusübersicht
- Responsive Darstellung auf Smartphone und Desktop
- PWA-Manifest / Standalone-Installation

**Wichtig:** Diese Version ist bewusst ein UX-/Frontend-PoC. Tickets und Fotos werden noch nicht an die bestehende API übertragen und nicht dauerhaft gespeichert.

## GitHub Pages

Die App wird über GitHub Actions nach GitHub Pages deployt. HTTPS ist damit verfügbar und ermöglicht Kameratests auf Smartphones.

## Lokal testen

```powershell
python -m http.server 8080
```

Dann `http://localhost:8080` öffnen. Für Smartphone-Kameratests HTTPS verwenden; `localhost` ist ebenfalls ein sicherer Kontext.

## Nächster technischer Schritt

Authentication/Login, Ticket-API, Multipart-Foto-Upload, Attachment-Galerie, Admin-Dashboard-API sowie Autorisierungs- und Integrationstests.

## API-Anbindung

Branch `feature/api-integration` enthält die erste echte API-Anbindung. Die App nutzt `/api/User/login`, `/api/User/me`, `/api/Tickets`, `/api/tickets/create` und den bestehenden Multipart-Endpunkt `/api/tickets/{ticketId}/uploadAttachment`. Die API-URL kann beim Login eingegeben und wird lokal gespeichert. Der Token wird aktuell für den PoC im Browser gespeichert; für Produktion sollte die Authentifizierung auf eine sichere Cookie-basierte Strategie umgestellt werden.
