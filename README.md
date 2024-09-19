:warning: Hinweis des Entwicklers (05/10/2024): :warning:

:airplane: Ich bin kürzlich in ein anderes Land gezogen und konzentriere mich derzeit darauf, mich in meinem neuen Zuhause einzuleben und verschiedene logistische Angelegenheiten zu regeln. Aus diesem Grund hat sich der Fortschritt bei neuen Funktionen für Deep Chat verlangsamt, und ich entschuldige mich für die Verzögerungen bei der Beantwortung von Anfragen.

:heart: Deep Chat war eines meiner lohnendsten Projekte, und ich freue mich darauf, so bald wie möglich wieder zu meinem üblichen Entwicklungstempo zurückzukehren. Vielen Dank für Ihr Verständnis und Ihre Geduld in dieser Zeit.

<br />

![Deep Chat](./assets/readme/banner-2.png)

<b>Deep Chat</b> ist eine vollständig anpassbare KI-Chat-Komponente, die mit minimalem Aufwand in Ihre Website integriert werden kann. Egal, ob Sie einen Chatbot erstellen möchten, der beliebte APIs wie ChatGPT nutzt, oder eine Verbindung zu Ihrem eigenen benutzerdefinierten Dienst herstellen möchten – diese Komponente kann alles! Erkunden Sie [deepchat.dev](https://deepchat.dev/), um alle verfügbaren Funktionen, Anleitungen, Beispiele und mehr zu entdecken!

### :rocket: Hauptfunktionen

- Verbindung zu beliebigen APIs
- Avatare
- Namen
- Dateien senden/empfangen
- Fotos über die Webcam aufnehmen
- Audio über das Mikrofon aufnehmen
- Spracherkennung für die Nachrichteneingabe
- Text-zu-Sprache zur Wiedergabe von Nachrichtenantworten
- Unterstützung für MarkDown und benutzerdefinierte Elemente zur Strukturierung von Text und zur Darstellung von Code
- Einführungspanel und dynamische Modale zur Beschreibung der Funktionalität für Ihre Nutzer
- Verbindung zu beliebten KI-APIs wie OpenAI, HuggingFace, Cohere direkt über den Browser
- Unterstützung für alle wichtigen UI-Frameworks/Bibliotheken
- Hosting eines Modells im Browser
- Alles ist anpassbar!

### :tada: :tada: Version 2.0 ist jetzt verfügbar :tada: :tada:

Wir präsentieren Deep Chat 2.0! Basierend auf Ihrem großzügigen Feedback haben wir Deep Chat neu gestaltet und verbessert. Es ist jetzt viel einfacher, es in jede Website zu integrieren und zu konfigurieren, um das bestmögliche Chat-Erlebnis für Ihre Nutzer zu bieten. Schauen Sie sich die [Release Notes](https://github.com/OvidijusParsiunas/deep-chat/releases/tag/2.0.0) für weitere Informationen an.

<p align="center">
    <img width="1200" src="https://github.com/user-attachments/assets/ea88cdd8-6197-4322-8e16-3908f69a7eb5" alt="Version 2.0">
</p>

### :computer: Erste Schritte

```
npm install deep-chat
```

Wenn Sie React verwenden, installieren Sie stattdessen Folgendes:

```
npm install deep-chat-react
```

Fügen Sie einfach Folgendes zu Ihrem Markup hinzu:

```
<deep-chat></deep-chat>
```

Die genaue Syntax für den obigen Code hängt vom Framework Ihrer Wahl ab ([siehe hier](https://deepchat.dev/examples/frameworks)).

### :zap: Verbindung

![Connect](./assets/readme/connect.png)

Die Verbindung zu einem Dienst ist einfach. Sie müssen nur die API-Details mit der [`request`](https://deepchat.dev/docs/connect#request)-Eigenschaft definieren:

```
<deep-chat request='{"url":"https://service.com/chat"}'/>
```

Der Dienst muss in der Lage sein, das von Deep Chat verwendete Anfrage- und Antwortformat zu verarbeiten. Bitte lesen Sie den Abschnitt [Connect](https://deepchat.dev/docs/connect) in der Dokumentation und schauen Sie sich die [Server-Vorlagen](https://deepchat.dev/examples/servers) an.

Alternativ, wenn Sie eine Verbindung ohne Änderung des Zielservers herstellen möchten, verwenden Sie die [`interceptor`](https://deepchat.dev/docs/interceptors)-Eigenschaften, um die übertragenen Objekte zu erweitern, oder die [`handler`](https://deepchat.dev/docs/connect#Handler)-Funktion, um den Anforderungscode zu steuern.

### :electric_plug: Direkte Verbindung

![Direct connection](./assets/readme/direct-connect.png)

Verbinden Sie sich direkt über den Browser mit beliebten KI-APIs mithilfe der [`directConnection`](https://deepchat.dev/docs/directConnection/#directConnection)-Eigenschaft:

```
<deep-chat directConnection='{"openAI":true}'/>

<deep-chat directConnection='{"openAI":{"key": "optional-key-here"}}'/>
```

Bitte beachten Sie, dass dieser Ansatz nur für lokale/Prototypen-/Demo-Zwecke verwendet werden sollte, da er den API-Schlüssel für den Browser freigibt. Wenn Sie bereit sind, live zu gehen, wechseln Sie bitte zur Verwendung der oben beschriebenen [`connect`](https://deepchat.dev/docs/connect#connect-1)-Eigenschaft zusammen mit einem [Proxy-Dienst](https://github.com/OvidijusParsiunas/deep-chat/tree/main/example-servers).

Derzeit unterstützte direkte API-Verbindungen:
[OpenAI](https://openai.com/blog/openai-api), [HuggingFace](https://huggingface.co/docs/api-inference/index), [Cohere](https://docs.cohere.com/docs), [Stability AI](https://stability.ai/), [Azure](https://learn.microsoft.com/en-gb/azure/cognitive-services/), [AssemblyAI](https://www.assemblyai.com/)

### :robot: Web-Modell

![Web Model](https://github.com/OvidijusParsiunas/deep-chat/assets/18709577/83936e6f-d0c1-42b7-ab61-ac75d7803660)

Keine Server, keine Verbindungen – hosten Sie ein LLM-Modell vollständig in Ihrem Browser.

Fügen Sie einfach das [deep-chat-web-llm](https://deepchat.dev/examples/externalModules)-Modul hinzu und definieren Sie die [webModel](https://deepchat.dev/docs/webModel)-Eigenschaft:

```
<deep-chat webModel="true" />
```

### :camera: :microphone: Kamera und Mikrofon

![Capture](./assets/readme/capture.png)

Verwenden Sie Deep Chat, um Fotos mit Ihrer Webcam aufzunehmen und Audio mit dem Mikrofon aufzunehmen. Sie können dies mit den [`camera`](https://deepchat.dev/docs/files#camera)- und [`microphone`](https://deepchat.dev/docs/files#microphone)-Eigenschaften aktivieren:

```
<deep-chat camera="true" microphone="true" ...other properties />
```

### :microphone: :sound: Sprache

https://github.com/OvidijusParsiunas/deep-chat/assets/18709577/e103a42e-b3a7-4449-b9db-73fed6d7876e

Geben Sie Text mit Ihrer Stimme ein, indem Sie die Spracherkennungsfunktion nutzen, und lassen Sie sich die Antworten mit der Text-zu-Sprache-Funktion vorlesen. Sie können diese Funktionalität über die [`speechToText`](https://deepchat.dev/docs/speech#speechToText)- und [`textToSpeech`](https://deepchat.dev/docs/speech#textToSpeech)-Eigenschaften aktivieren.

```
<deep-chat speechToText="true" textToSpeech="true" ...other properties />
```

### :beginner: Beispiele

Schauen Sie sich Live-Codepen-Beispiele für Ihr [UI-Framework/Bibliothek](https://deepchat.dev/examples/frameworks) Ihrer Wahl an:

| React                                                                                                                                                   | Vue 2                                                                                                                                                   | Vue 3                                                                                                                                                | Svelte                                                                                                                                                       | SvelteKit                                                                                                                                                                                               | Angular                                                                                                                                                                             | Solid                                                                                                                                                   | Next                                                                                                                                  | Nuxt                                                                                                                                                 | VanillaJS                                                                                                                                                         |
| ------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <a href="https://stackblitz.com/edit/deep-chat-react?file=src%2FApp.tsx" target="_blank"><img src="./website/static/img/reactLogo.png" width="60"/></a> | <a href="https://codesandbox.io/s/deep-chat-vue2-cdqpt2?file=/src/App.vue" target="_blank"><img src="./website/static/img/vueLogo.png" width="60"/></a> | <a href="https://stackblitz.com/edit/deep-chat-vue3?file=src%2FApp.vue" target="_blank"><img src="./website/static/img/vueLogo.png" width="60"/></a> | <a href="https://stackblitz.com/edit/deep-chat-svelte?file=src%2FApp.svelte" target="_blank"><img src="./website/static/img/svelteLogo.png" width="45"/></a> | <div align="center"><a href="https://stackblitz.com/edit/deep-chat-sveltekit?file=src%2Froutes%2F%2Bpage.svelte" target="_blank" ><img src="./website/static/img/svelteLogo.png" width="45"/></a></div> | <a href="https://stackblitz.com/edit/stackblitz-starters-7gygrp?file=src%2Fapp%2Fapp.component.ts" target="_blank"><img src="./website/static/img/angularLogo.png" width="66"/></a> | <a

 href="https://stackblitz.com/edit/deep-chat-solid?file=src%2FApp.tsx" target="_blank"><img src="./website/static/img/solidLogo.png" width="60"/></a> | <a href="https://deepchat.dev/examples/frameworks#next" target="_blank"><img src="./website/static/img/nextLogo.png" width="60"/></a> | <a href="https://stackblitz.com/edit/nuxt-starter-vwz6pg?file=app.vue" target="_blank"><img src="./website/static/img/nuxtLogo.png" width="70"/></a> | <a href="https://codesandbox.io/s/deep-chat-vanillajs-v2ywnv?file=/index.html" target="_blank"><img src="./website/static/img/vanillaJSLogo.png" width="60"/></a> |

Die Einrichtung eines eigenen Servers war noch nie so einfach mit den folgenden [Server-Vorlagen](https://deepchat.dev/examples/servers). Vom Erstellen Ihres eigenen Dienstes bis hin zum Einrichten von Proxys für andere APIs wie OpenAI – alles ist dokumentiert und mit klaren Beispielen versehen, damit Sie in Sekundenschnelle loslegen können:

| Express                                                                                                                                                                          | Nest                                                                                                                                                                         | Flask                                                                                                                                                                          | Spring                                                                                                                                                                                 | Go                                                                                                                                                                | SvelteKit                                                                                                                                                                                               | Next                                                                                                                                                                    |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <a href="https://github.com/OvidijusParsiunas/deep-chat/tree/main/example-servers/node/express" target="_blank"><img src="./website/static/img/expressLogo.png" width="60"/></a> | <a href="https://github.com/OvidijusParsiunas/deep-chat/tree/main/example-servers/node/nestjs" target="_blank"><img src="./website/static/img/nestLogo.png" width="60"/></a> | <a href="https://github.com/OvidijusParsiunas/deep-chat/tree/main/example-servers/python/flask" target="_blank"><img src="./website/static/img/flaskLogo.png" width="60"/></a> | <a href="https://github.com/OvidijusParsiunas/deep-chat/tree/main/example-servers/java/springboot" target="_blank"><img src="./website/static/img/springBootLogo.png" width="50"/></a> | <a href="https://github.com/OvidijusParsiunas/deep-chat/tree/main/example-servers/go" target="_blank"><img src="./website/static/img/goLogo.png" width="40"/></a> | <div align="center"><a href="https://github.com/OvidijusParsiunas/deep-chat/tree/main/example-servers/sveltekit" target="_blank" ><img src="./website/static/img/svelteLogo.png" width="45"/></a></div> | <a href="https://github.com/OvidijusParsiunas/deep-chat/tree/main/example-servers/nextjs" target="_blank"><img src="./website/static/img/nextLogo.png" width="55"/></a> |

Alle Beispiele sind bereit, auf einer Hosting-Plattform wie [Vercel](https://vercel.com/) bereitgestellt zu werden.

## :tv: Tutorials

Demovideos sind auf [YouTube](https://www.youtube.com/@ovi-il4rg/videos) verfügbar:

<p align="center">
    <a href="https://www.youtube.com/@ovi-il4rg/videos">
        <img width="1000" src="https://github.com/OvidijusParsiunas/deep-chat/assets/18709577/29cc292b-5964-4f06-ba39-6ae3f8585944" alt="Videos">
    </a>
</p>

## :joystick: Playground

Erstellen, konfigurieren und verwenden Sie Deep-Chat-Komponenten, ohne eine einzige Codezeile zu schreiben, im offiziellen [Playground](https://deepchat.dev/playground)!

<p align="center">
    <img width="750" src="https://github.com/OvidijusParsiunas/deep-chat/assets/18709577/57ab8d3f-defe-40f3-a0af-451f6159bbb2" alt="Playground">
</p>

:tada: <b>Update</b> – Komponenten können jetzt mit der neuen <b>Erweiterten Ansicht</b> auf Vollbildgröße erweitert werden:

<p align="center">
    <img width="750" src="https://github.com/OvidijusParsiunas/deep-chat/assets/18709577/6b78907c-c4c2-44de-b4c7-d73c1e887fa8" alt="Erweiterte Ansicht">
</p>

## :star2: Sponsoren

Danke an unsere großzügigen Sponsoren!

<p align="center">
    &nbsp; &nbsp; &nbsp; 
    <img src="https://github.com/matthiasamberg.png" width="110px"/>
    &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;
    <img src="https://github.com/dorra.png" width="110px"/>
    &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;  
    <img src="https://github.com/techpeace.png" width="110px" />
    &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;  
    <img src="https://github.com/aquarius-wing.png" width="110px" />
</p>
<p align="center">
     &nbsp; &nbsp;&nbsp;&nbsp;&nbsp;
    <a href="https://github.com/matthiasamberg">matthiasamberg</a>
    &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; 
    <a href="https://github.com/dorra">dorra</a>
    &nbsp; &nbsp;  &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;&nbsp;&nbsp;&nbsp; 
    <a href="https://github.com/techpeace">techpeace</a>
      &nbsp; &nbsp;  &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;&nbsp;
    <a href="https://github.com/aquarius-wing">aquarius-wing</a>
     &nbsp;
</p>

## :heart: Beiträge

Open Source wird von der Community für die Community entwickelt. Alle Beiträge zu diesem Projekt sind willkommen!<br>
Darüber hinaus, wenn Sie Vorschläge für Verbesserungen haben, Ideen, wie das Projekt weiterentwickelt werden kann, oder einen Fehler entdeckt haben, zögern Sie nicht, ein neues Issue-Ticket zu erstellen, und wir werden uns so schnell wie möglich darum kümmern!
