# ansible-web

All the ansible playbook are straightforward and doesn't needs too much information but please feel free to leave me a comment here.

We also need a heatlthcheck for our Nginx in the docker container:
#docker run --name=nginx-proxy -d \
        --health-cmd='curl --fail http://nginx.host.com || exit 1' \
        --health-interval=5m \
        --health-timeout=3s \
        nginx:1.13
        
This is the simple check
