# Azure infrastructure as code using both ansible &amp; terraform.

- For Ansible based automation:
  
    a. Install python3-pip and then install the ansible collection related to azure:

    ```
    $ sudo apt-get install python3-pip -y
    $ sudo pip3 install 'ansible[azure]'
    ```

    b. Create a Azure service principal and collect the following information:
    ```
    subscription_id
    client_id
    secret
    tenant
    ```

    c. Make a hidden folder under your parent directory and load the credentials
    ```
    $ mkdir ~/.azure
    $ vi ~/.azure/credentials
    
    [default]
    subscription_id='<your-subscription_id>'
    client_id='<security-principal-appid>'
    secret='<security-principal-password>'
    tenant='<security-principal-tenant>'  
    ```

    d. To deploy the azure resource use the playbooks available under 'Ansible/deploy' folder. Eg:
    ```
    $ ansible-playbook  Ansible/deploy/resource-group.yaml
    $ ansible-playbook  Ansible/deploy/virtual-network.yaml
    $ ansible-playbook  Ansible/deploy/vm-deploy.yaml
    ```
    
    e. To delete the fullstack solution use the below playbook:
    ```
    $ ansible-playbook  Ansible/delete/vm-delete.yaml
    ```
