```mermaid
sequenceDiagram
    participant browser
    participant server

    browser->>server: form button clicked, user input sent, HTTP POST new note method send
    activate server
    server-->>browser:  new note HTTP Post recevied, and build new note on server. Send  HTTP 302 code

    browser->>server: send HTTP GET  in notes
    activate server
    server-->>browser: send  main.css, main.js and data.json 
    deactivate server

    server-->>browser: notes page update
    deactivate server