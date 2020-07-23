# Ansible Environment Setup

## Description
An easy way to automatize the initial setup and the package management of your developement machine, either it is macos or ubuntu.

## Tools 
- Ansible: https://www.ansible.com/  
- Ansible Molecule for testing: https://molecule.readthedocs.io/en/latest/

## How to run

### Requirements
- Ansible has to be installed: https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html

```
# clone first the repository, then:
ansible-playbook main.yml -v  
```
or    
```
ansible-pull -U git@github.com:ironoa/ansible-personal.git main.yml
```

## How to test

### Requirements
- if you have not yet run the ansible-playbook, you need to install python manually: https://github.com/pyenv/pyenv  

Molecule works only with linux-based docker images, therefore for now is possible to test only the debian Role:

```
python -m venv env    
source ./env/bin/activate    
pip install ansible    
pip install 'molecule[lint]'    
pip install 'molecule[docker]'  
cd roles/debian/  
molecule test  
deactivate  
```