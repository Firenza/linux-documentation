1. Create a new user called plex `sudo adduser plex`
1. Create a new group called plexusers `sudo groupadd plexusers`
1. Add plex user to new group `sudo usermod -a -G plexusers plex`
1. Create a new docker-compose file with the content from https://hub.docker.com/r/linuxserver/plex
1. Update the PUID and PGID with the user id and group ids from the above groups
1. Update the ownership of your plex folder `sudo chown -R plex:plexusers YOUR_PLEX_FOLDER`
