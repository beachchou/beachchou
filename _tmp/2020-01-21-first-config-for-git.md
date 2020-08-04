---
---
1. ssh key

    ```sh
    ssh-keygen -t rsa -b 4096 -C "you@example.com"
    # -rw------- id_rsa
    # -rw-r--r-- id_rsa.pub
    ```

2. config

    ```sh
    git config --global user.email "you@example.com"
    git config --global user.name "Your Name"
    ```