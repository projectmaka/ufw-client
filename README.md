# A UFW client for [Maka](https://projectmaka.io)

## Installation

The client can be used a few different ways, such as running in a screen session, or as a systemd service. We recommend the latter.

The steps for installation are as follows:

```
sudo apt install python3-pip -y
sudo useradd nlsd
sudo adduser nlsd adm
sudo mkdir /home/nlsd
sudo chown -R nlsd:nlsd /home/nlsd
sudo usermod -d /home/nlsd nlsd
sudo chmod -R 700 /home/nlsd
sudo su - nlsd
pip3 install requests --user
pip3 install sh --user
```

Save `nlsd.py` to the user's directory, and save the API key in the `key` file in the same directory.

You can create the service with the `nlsd.service` file in this repository.
Save the file to `/etc/systemd/system/nlsd.service`, then run `sudo systemctl start nlsd && sudo systemctl enable nlsd` to start and enable it at startup.

You should also add `/usr/sbin/nologin` to the nlsd user's line in `/etc/passwd`.
