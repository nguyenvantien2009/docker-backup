# Docker Backup

backup a docker container including its volumes

## Install
`npm i -g docker-backup`

## Usage

### Backup
`docker-backup <container> [dest] [--name newname]`

### Restore Image
`docker-backup restore <path-to-image.tar>`

### Restore Container
`docker-backup restore <path-to_create.sh>`

### Restore Volume
`docker-backup restore <path-to-volume.tar> [container name]`


## Example

Run docker image.

```
docker run --name some-ghost -p 8080:2368 -d ghost
```

Backup Docker

```
docker-backup some-ghost /backups --name ghost-backup
```

Restore Docker

```
docker-backup restore /backups/ghost-backup_image.tar
docker-backup restore /backups/ghost-backup_create.sh
docker-backup restore /backups/ghost-backup_volume_xx.tar ghost-backup
docker start ghost-backup
```
