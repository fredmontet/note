SSH
===

Create a SSH keypair to put in a git repo for instance

    ssh-keygen -t ed25519 -C "your_email@example.com"

If you are using a legacy system that doesn't support ed25519, use :

    ssh-keygen -t rsa -b 4096 -C "your_email@example.com"

Reference
---------

https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent

