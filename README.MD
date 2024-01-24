
# clog - Clear Docker Container Logs

## Description

The `clog` script is a Bash shell script designed to clear logs for a specified Docker container.

## Usage

## Code

```bash
#!/bin/bash

if [ -z "$1" ]; then
    echo "Usage: $0 CONTAINER_ID"
    exit 1
fi

log_path=$(docker inspect --format='{{.LogPath}}' "$1")

if [ -z "$log_path" ]; then
    echo "Error: Unable to get log path for container $1"
    exit 1
fi

echo "" > "$log_path"
echo "Logs cleared for container $1"
```

Save this script in a file named `clog`, and then make it executable:

```bash
chmod +x clog
```

## Run anywhere

 Move the script to `/usr/local/bin` to make it accessible from anywhere:

   ```bash
   sudo mv clog /usr/local/bin/
   ```

Now, you can run the script from any location by simply typing `clog CONTAINER_ID`.


Replace `CONTAINER_ID` with the actual ID or name of the Docker container whose logs you want to clear.

## Prerequisites

- Docker installed on the system
- Permission to access Docker daemon (typically, the script should be run by a user in the `docker` group)

## License

This script is licensed under the [MIT License](LICENSE).
```

Save this content in a file named `README.MD`. You can modify the content as needed, and it provides basic information about the script, its usage, prerequisites, and licensing.