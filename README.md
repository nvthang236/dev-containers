## Container

### Run

```bash
  docker-compose -f <yaml_file_name> up -d
```

### Stop

```bash
  docker-compose -f <yaml_file_name> down -v
```

## MongoDB

### Dump

```bash
  docker exec -i mongo mongodump -d <db_name> -o .
```

```bash
  docker cp mongo:/<db_name> <db_folder_path>
```

### Restore

```bash
  docker cp <db_folder_path> mongo:/dump
```

```bash
  docker exec -i mongo mongorestore --drop -d <db_name> /dump
```

### Cleaning up afterwards

```bash
  docker exec -i mongo rm -rf /dump
```