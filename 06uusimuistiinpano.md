

```mermaid

sequenceDiagram
    participant user as User
    participant browser as Browser
    participant server as Server

    user->>browser: Type note into text field
    user->>browser: Click "Save" button
    activate browser
    Note right of browser: The browser captures the note content and updates the UI immediately
    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note_spa (with note data)
    activate server
    Note right of server: The server processes the new note and stores it
    server-->>browser: creates new node (no response body)
    deactivate server
    deactivate browser

    Note right of browser: The browser does not wait for the server response to update the UI
