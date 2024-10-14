# Dynamic Page Title with Visibility Change

Dies ist ein einfaches HTML-Projekt, das den Seitentitel dynamisch ändert, wenn der Benutzer die Tabs wechselt oder die Sichtbarkeit des Dokuments ändert. Das Skript wechselt den Dokumenttitel alle 2 Sekunden zwischen "Dynamischer Seitentitel" und "Dokumente", wenn die Seite nicht sichtbar ist, und stellt ihn wieder auf "Dynamischer Seitentitel" zurück, wenn die Seite wieder sichtbar ist.

## Wie es funktioniert

Das JavaScript in diesem Projekt hört auf das `visibilitychange`-Ereignis. Wenn das Ereignis ausgelöst wird (z.B. wenn der Benutzer die Tabs wechselt oder das Browserfenster minimiert), startet es ein Intervall, das den Dokumenttitel alle 2 Sekunden ändert. Wenn die Seite wieder sichtbar wird, wird das Intervall gelöscht und der Titel wird auf "Dynamischer Seitentitel" zurückgesetzt.

## Code

```html
<!DOCTYPE html>
<html lang="de">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Dynamischer Seitentitel</title>
</head>
<body>
  <script>
    let intervalId;

    document.addEventListener('visibilitychange', () => {
      if (document.hidden) {
        intervalId = setInterval(() => {
          document.title = document.title === 'Dynamischer Seitentitel' ? 'Dynamischer Titel' : 'Dynamischer Seitentitel';
        }, 2000);
      } else {
        clearInterval(intervalId);
        document.title = 'Dynamischer Seitentitel';
      }
    });
  </script>
</body>
</html>
```

