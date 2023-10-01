graph TD
    subgraph Browser
        subgraph User Interface
            User --> Home Page
            Home Page --> Notes Page
            Notes Page --> Create Note Page
            Notes Page --> View Note Page
        end

        subgraph Client-Side Rendering
            Home Page --> Load JavaScript (main.js)
            Notes Page --> Load JavaScript (main.js)
            Create Note Page --> Load JavaScript (main.js)
            View Note Page --> Load JavaScript (main.js)

            Load JavaScript (main.js) --> Fetch Notes Data
            Fetch Notes Data --> Display Notes
            Notes Page --> Handle User Interactions
            Create Note Page --> Handle User Interactions
            View Note Page --> Handle User Interactions
        end
    end

    subgraph Server
        subgraph API
            Notes Page --> GET /api/notes
            Create Note Page --> POST /api/notes
            View Note Page --> GET /api/notes/:id
        end

        subgraph Database
            POST /api/notes --> Create New Note
            GET /api/notes --> Retrieve Notes
            GET /api/notes/:id --> Retrieve Note by ID
        end
    end

    subgraph Database Server
        Database --> Save Note Data
    end
