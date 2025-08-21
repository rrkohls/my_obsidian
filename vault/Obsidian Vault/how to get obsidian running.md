This adds obsidian to a wsl as a docker vewable via windows browser

WSL:
mkdir docker
mkdir docker/obsidian
mkdir docker/obsidian/vault
cd docker/obsidian
vi docker-compose.yml

version: "3.8"
services:
  obsidian:
    image: ghcr.io/linuxserver/obsidian:latest
    container_name: obsidian
    ports:
      - "3000:3000"
    volumes:
      - ./vault:/config
    restart: unless-stopped
    environment:
      - PUID=1000

docker-compose up -d

go into github and create a new repo

in ~/docker/obsidian

git init
git add .
git commit -m "initial commit"
git remote add origin https://github.com/rrkohls/my_obsidian.git
git push

add notes in ~/docker/obsidian/vault/Obsidian\ Vault\ ad .md files
or use windows browser 
https://localhost:3000