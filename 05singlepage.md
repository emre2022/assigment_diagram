```mermaid
sequenceDiagram
    participant browser
    participant server

    browser->>server: loading HTML file javascript file and make a HTTP GET demand
    activate server

    server-->>browser: sends notes in JSON file
    deactivate server

    browser->>browser: load DOM-API and make new note and recreate the page
    browser->>server: sends new note with HTTP POST in JSON 
    activate server

    server-->>browser:  201 Created code, dont update the page more
    deactivate server