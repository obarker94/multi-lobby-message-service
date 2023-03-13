# multi-lobby-message-service

Multi Lobby Message Service (MLMS) is a Shared-Nothing distributed computing solution to handling many concurrent connections and messages.

## Core Structure 

Highly subject to change and this will be updated as the project progresses.

1. Load balancer / connection broker to route incoming traffic.
2. On a valid connection, the user will be routed to a lobby.
    2a. If the lobby doesn't exist, a lobby will be created.
3. Redis will be used as a cache layer or message broker between different parts of the application.
4. Database will likely be MySQL.

Each element of the application will be containerised and managed through Docker. As the application grows, it may be required to use Kubernetes OR an AWS ECS.




