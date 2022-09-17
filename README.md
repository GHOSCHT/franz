# Franz
<div align="center">
  <img src="assets/logo.png" alt="Logo" width="80" height="80">
  <p>Collection of Docker Compose files for my homeserver</p>
</div>

## Structure

The server is divided into several modular components which can be startet and stopped almost independently from one another.
Some are optional, while others are mandatory.

## Modules

### [dns](/dns)

An instance of pihole with unbound as a recursive dns for more privacy.

### [infrastructure](/infrastructure)

Traefik runs as a reverse proxy with pihole supplying the custom domain. Homarr was chosen as a dashboard for all services.

### [media](/media) (Optional)

An automated media server setup with jellyfin, radarr, sonarr, bazarr, prowlarr, transmission and windscribe

### [nas](/nas) (Optional)

An instance of nextcloud and a smb share.

### [volman](/volman) (Optional)

My default setup to manage docker volume contents. Mount several data volumes or path mappings to exchangel, position and backup data.

## Setup

Use `sudo docker network create -d bridge traefik-net` to create network for traefik.
In every module subfolder you can run `sudo docker compose up -d` to start a module and `sudo docker compose down` to stop it.

## License

Distributed under the MIT License. See `LICENSE` for more information.
