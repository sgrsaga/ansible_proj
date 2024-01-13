
### Run Play Book sample

#### ansible-playbook --inventory inventory/inventory.ini roles/setup-nginx.yaml


### Ansible Valut handling


Create Vault
#### ansible-vault create vault/myvault.yaml

View Vault details

#### ansible-vault view myvault.yaml

Edit Vault

#### ansible-vault edit vault/myvault.yaml

Calling Ansible Playbook by manually providing vault password

#### ansible-playbook -i inventory/inventory.ini roles/basics.yaml -e @vault/myvault.yaml --ask-vault-pass

Reset the Password
#### ansible-vault rekey vault/myvault.yaml



Create abase64 password file to use in valut in password file


Create password file

#### openssl rand -base64 2048 > passfile/file_pass.pass

Create vault with Pass file

#### ansible-vault create vault/vault_with_base64_pass.yaml --vault-password-file=passfile/file_pass.pass

View vault with  passfie

#### ansible-vault view ault/vault_with_base64_pass.yaml --vault-password-file=passfile/file_pass.pass

Run Ansible playbook with passfile given

#### ansible-playbook -i inventory/inventory.ini roles/basics.yaml -e @vault/vault_with_base64_pass.yaml --vault-password-file=passfile/file_pass.pass


Create an environment variable with password "ANSIBLE_VAULT_PASSWORD_FILE" this should be the end variable name

####  export ANSIBLE_VAULT_PASSWORD_FILE=/home/ubuntu/ansible_proj/passfile/file_pass.pass

####  ansible-playbook -i inventory/inventory.ini roles/basics.yaml -e @vault/vault_with_base64_pass.yaml
