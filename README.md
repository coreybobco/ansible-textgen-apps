# ansible-textgen-apps

### What is this?
[Markov Mutagen](http://markovmutagen.net) is a web app that combines and trarnsforms texts from Project Gutenberg and Archive.org with text generation algorithms. This is an Ansible playbook to deploy it to a server:
- Markov Mutagen: https://github.com/coreybobco/markov-mutagen

### How to Use:
- On an Ubuntu-based control machine, running `preinstall-control-machine.sh` will install the latest ansible from their PPA.
- Set all the environment variables listed in group_vars/all before proceeding. I recommend creating a .envrc file and using [direnv](https://direnv.net/).
- You will need to install Python 2.7 on your server. This doesn't come with Ubuntu 17.10, so ssh into your server and install python with apt: `apt install python`
- Now you can run the playbooks from your control machine. 
- `ansible-playbook - i inventory setup.yml` run this if you only have root ssh access to your to secure your server by disabling root ssh access and creating a user which will have ssh access and passwordless sudo
- `ansible-playbook - i inventory site.yml` -- run this to set up Markov Mutagen