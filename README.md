# FreeTDS Development Environment
Docker containers for FreeTDS development.

## FreeTDS C Development Container
Has most of (all?) the tools needed for compiling and debugging the FreeTDS C library.
- **gcc**
- **gdb**
- **make**
- ...

## Docker Compose File
The docker compose file starts the following containers:
- FreeTDS C dev container (blieusong/freetds-dev-c),
- Sybase ASE container (blieusong/sybase-ase),
- MSSQL Server container (Microsoft's official container)

# Getting Started
Run
```
docker-compose up -d
```

If you don't want to start all the databases at the same time, just specify which services **docker-compose** shall start. For example, if you only need the FreeTDS container and an ASE Server:
```
docker-compose up -d freetds-dev ase-server
