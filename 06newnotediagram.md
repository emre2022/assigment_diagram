```mermaid
sequenceDiagram
    participant browser
    participant server

    browser->>server: form button clicked, user input sent,loading HTML file javascript file and make a HTTP GET demand
    activate server
    server-->>browser:  new note HTTP Post recevied, and build new note on server. Send  HTTP 302 code

 
    server-->>browser: send  main.css, main.js and data.json 
    deactivate server

    browser->>browser: load DOM-API and make new note and recreate the page
    browser->>server: sends new note with HTTP POST in JSON 
    activate server

    server-->>browser: 201 Created code, dont update the page more
    deactivate server
