# chibisafe-cli
A simple cli/shell script to install and manage your chibisafe instance

Check out [Pitu](https://github.com/pitu) and the [Chibisafe](https://github.com/chibisafe/chibisafe) project, they're awesome!

## ⚠️ Experimental Usage ⚠️
Please use this with care. I've tested it only on Debian 12 machines.
The best case would be a freshly installed VPS or virtual machine to use this script on.
It will install all dependencies (as root) but i'm considering building it in user-mode/sudo.

## What does it do?
It will do following steps for you:
 - It will install following prerequisites if they not already installed: `sudo, ffmpeg, git, screen, curl, debian-keyring, debian-archive-keyring, apt-transport-https, curl`
 - It will add the GPG keyring from chibisafe.dev
 - Installing `Caddy` onto the host if it's not installed already
 - Clones the recent chibisafe repository
 - Installs dependencies and building/migrating Chibisafe initially
 - Setting the BASE API URL for the frontend
 - Configuring the Caddyfile in `/etc/caddy/Caddyfile`
	 - It will ask you what domain you want to use for chibisafe, don't forget to point your domain DNS to your host.
	 - You can choose if your using Cloudflare behind it or use it as it is
 
After that you can start the services via the `./chibisafe-cli` and you should access your dashboard with your chosen domain from the setup process.

> The initial credentials for the dashboard are `admin/admin`.

## How to use?
Just download the bash script and upload it into your desired installation folder.
For example in your `home` directory.

Make the script executable:
```
chmod +x chibisafe-cli
```

Run it via 
```
./chibisafe-cli
```

## Planned features
 - [ ] Update functionality for frontend and backend seperately 
 - [ ] Backup functionality
 - [x] Proper cli commands for fast(er) accessibility
 - [x] Uninstall functionality
 - [ ] Choose between docker or standalone setup
 - [ ] Migrate database functionality
 - [ ] Check on which distro the cli is running
 - [ ] Add 'chibisafe-cli' as PATH command
 - [ ] Add cURL functionabity to use the API via cli
