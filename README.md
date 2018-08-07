# ansible-web

1. Setup Aws Credentials
2. Setup Ansible reqirement
3. Inventory  file "hosts"  which will automatically updated as instance is up. 

Step1 
.  - Create Instance  , Security Group ,Keys 
           cd ec2 
           ansible-playbook   -i ../hosts ec2_provision.yml
Step 2
.- Update the Allowed IP address in main.yml under roles 
             ansible-playbook -i ../hosts firewall.yml
Step 3
   - Install docker and configure docker nginx image.
             ansible-playbook -i ../hosts docker.yml

We also need a heatlthcheck for our Nginx in the docker container:
#docker run --name=nginx-proxy -d \
        --health-cmd='curl --fail http://nginx.host.com || exit 1' \
        --health-interval=5m \
        --health-timeout=3s \
        nginx:1.13
        
This is the simple check
