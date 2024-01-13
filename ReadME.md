
### Run Play Book
"
ansible-playbook --inventory inventory/inventory.ini roles/setup-nginx.yaml
"

### Ansible Valut handling

"
Create Vault
# ansible-vault create vault/myvault.yaml

View Vault details

# ansible-vault view myvault.yaml

Edit Vault

# ansible-vault edit vault/myvault.yaml

Calling Ansible Playbook by manually providing vault password

# ansible-playbook -i inventory/inventory.ini roles/basics.yaml -e @vault/myvault.yaml --ask-vault-pass

Reset the Password
# ansible-vault rekey vault/myvault.yaml

"

### Create abase64 password file to use in valut in environment variable password file

"
Create password file

"