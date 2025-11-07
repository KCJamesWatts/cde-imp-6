# CDE Imp 6
Repository: https://github.com/KCJamesWatts/cde-imp-6

Packages:
- ghcr.io/KCJamesWatts/cde-imp-6-frontend
- ghcr.io/KCJamesWatts/cde-imp-6-backend

## Connecting to Dev Containers

Open VS Code from the root folder of the project:

```
> code .
```

Once the project is open in VS Code, open the command palette (Ctrl + Shift + P)  and choose **Dev Containers: Reopen in Container**.  You will be shown and a group of  available dev containers for the project, select the one you want to connect to.
```
Dev Container: Reopen in Container
> cde-imp-6 - cde-imp-6-frontend (.devcontainer/cde-imp-6-frontend/devcontainer.json)
> cde-imp-6 - cde-imp-6-backend (.devcontainer/cde-imp-6-backend/devcontainer.json)
```
## Containers
Useful Docker Commands:

Start the container and all contained services:
```
docker compose up --detach
```
Stop and Remove the container:
```
docker compose down --remove-orphans
```

