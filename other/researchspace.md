# ResearchSpace
> (2026-02-16) This document is deprecated as it contains information on a old version of Research Space

## Links and documentation
- Main site: https://researchspace.org/
- GitHub (project): https://github.com/researchspace/researchspace
- GitHub (docker-compose): https://github.com/researchspace/researchspace-docker-compose
- GitHub (ontologies): https://github.com/researchspace/researchspace-instance-configurations

## How to install
### Docker
```shell
$ git clone git@github.com:researchspace/researchspace-docker-compose.git
$ cd researchspace-docker-compose/
$ cd basic/
```

Edit `.env` file: 
- Change `COMPOSE_PROJECT_NAME` to a proper prefix for docker containers
- **IMPORTANT (18/06/2024)**: Increase `BLAZEGRAPH_MEMORY` (values <4g seems to not work on first launch )
- **IMPORTANT (18/06/2024)**: Increase `RESEARCHSPACE_MEMORY` (values <4g seems to cause error 503)
- Add `RESEARCHSPACE_JAVA_OPTS=-Xms1450m -Xmx1450m -Dlog4j2.formatMsgNoLookups=true` (solve https://github.com/researchspace/researchspace/issues/339)
- Add `BLAZEGRAPH_JAVA_OPTS=-Xms1450m -Xmx1450m -Dlog4j2.formatMsgNoLookups=true` (solve https://github.com/researchspace/researchspace/issues/339)

Generate folders
```shell
$ sudo chmod +x fix-folder-permissions.sh
$ sudo ./fix-folder-permissions.sh  # sudo is required as it changes blazegraph to 999:adm
```

> NOTE: to reset folders to default use
> ```shell
> $ sudo rm -rf blazegraph researchspace/data
> ```

Generate docker containers
```shell
$ docker compose up -d
```

Check if it works at http://localhost:10214 (user: admin, password: admin)

To check logs
```shell
$ docker compose logs -f
$ docker compose logs -f <container>
```

## First launch
Add ontologies as explained in https://github.com/researchspace/researchspace-instance-configurations
