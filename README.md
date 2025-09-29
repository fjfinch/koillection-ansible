# koillection-ansible
Ansible playbook for deploying and configuring a Koillection container.

## Install & setup
To use this repo, a couple of tools are required:

* git (to clone the repo)
* pipx (to install ansible)
* ansible (to configure the system)

1 - Oneliner to install all above:
```bash
sudo apt update && sudo apt install -y git pipx && pipx install ansible --include-deps && . ~/.profile

# PIPX from APT is often outdated. PIPX from PIP:
sudo apt update &&\
sudo apt install -y git python3-pip python3-venv &&\
pip install --break-system-packages --user pipx &&\
python3 -m pipx ensurepath &&\
. ~/.profile &&\
pipx install ansible --include-deps
```

2 - Clone this repository:
```bash
git clone https://github.com/fjfinch/koillection-ansible.git
```

3 - Pull the required roles:
```bash
ansible-galaxy collection install -r requirements.yml
```

4 - Execute the playbook:
> Note: first create the `files/secret.yml` file and add the database password
```bash
ansible-playbook main.yml -K
```
