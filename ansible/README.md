# Enable EPEL repository
sudo dnf install -y epel-release

# Remove existing packages
sudo dnf remove -y podman-docker docker-ce docker-ce-cli

# Install Docker official repo
sudo dnf config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo

# Install Docker with --allowerasing
sudo dnf install -y ansible-core docker-ce docker-ce-cli containerd.io --allowerasing

# Start Docker
sudo systemctl start docker
sudo systemctl enable docker

# Verify installation 
sudo docker --version

# run playbook
ansible-playbook site.yml
