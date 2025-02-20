
sequenceDiagram
    participant browser
    participant server
 
% user writes notes and presses "save" %

    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note \n{"content": "New note"}
    activate server
    server-->>browser: 200 %% code 200 = success
    deactivate server
    
    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
    activate server
    server-->>browser: [{"content": "New note"}]
    deactivate server   

  