

sequenceDiagram
    participant browser
    participant server
 
%% user writes notes and presses "save" 

    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note \n{"content": "New note"}
    activate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/notes 
    activate server
    server-->>browser: HTML document
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
    activate server
    server-->>browser: the css file
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.js
    activate server
    server-->>browser: the JavaScript file
    deactivate server
    
    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
    activate server
    server-->>browser: [{"content": "New note"}]
    deactivate server   

  