# Home Web Server
- Launch web apps with Docker
- Port forwarding
- Firewall config

## Docker commands
- `docker ps [-a]`
- `docker images`
- `docker stop CONTAINER_ID`
- `docker rm CONTAINER_ID`
- `docker rmi IMAGE_ID`
- `docker run -d -p LOCAL_PORT:CONTAINER_PORT IMAGE_NAME`

## Port Forwarding
- Login to gateway router from browser
    - Find IP with `netstat -nr`
- Look for port forwarding settings and expose desired port
- Have the app bind on desired port

## Firewall
- `sudo apt install ufw`
- Enable port 22 for ssh and ports for web app