
## Installation Steps

- wsl --install
- Install docker
	```bash
	# Add Docker's official GPG key:
	sudo apt-get update
	sudo apt-get install ca-certificates curl
	sudo install -m 0755 -d /etc/apt/keyrings
	sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
	sudo chmod a+r /etc/apt/keyrings/docker.asc
	
	# Add the repository to Apt sources:
	echo \
	  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu \
	  $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
	  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
	sudo apt-get update
	sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
	```
- Post docker setup
	```bash
	sudo groupadd docker
	sudo usermod -aG docker $USER
	sudo systemctl enable docker.service
	sudo systemctl enable containerd.service
	```
- Pull required images
	```bash
	docker pull jupyter/r-notebook jupyterhub/jupyterhub
	```
- Clone repo
	```bash
	git clone FalseDev/r-jupyterlab
	```
- Run jupyterlab
	```bash
	docker compose up
	```
- Install tailscale
	```bash
	curl -fsSL https://tailscale.com/install.sh | sh
	```
- Connect to tailscale
- Activate jupyterhub
- Port forward hoster:8000 to lab-machine:8000
- Open up port 8000 in azure network settings
- use frp to forward ports
	```bash
	frpc -c ./frpc.toml
	```
## References

- [Docker Setup](https://docs.docker.com/engine/install/ubuntu/)
- [Docker PostInstall](https://docs.docker.com/engine/install/linux-postinstall/)