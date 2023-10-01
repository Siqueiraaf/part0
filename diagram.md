sequenceDiagram
    participant browser
    participant server
    participant user

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/notes
    activate server
    server-->>browser: HTML document
    deactivate server

    user->>browser: Escreve nova nota e clica em 'Submit'
    activate user
    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note
    activate server
    server-->>browser: Nota criada com sucesso
    deactivate server
    deactivate user

    Note right of browser: O navegador atualiza a lista de notas na página
