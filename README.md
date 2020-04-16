The goal of this role is to install a webcam server on your Raspberry Pi.

# Prerequisites

- You need to have Raspbian Buster installed on your Pi.
- You need to have `ansible-playbook` installed locally.
- You need to have SSH enabled and have access.
- You need to enable the camera on the Pi.

SSH and the camera can be enabled by running `sudo raspi-config` and then navigating to the `Interfacing Options` menu.

# How to run

First clone this repository:

```
git clone https://github.com/michielgerritsen/ansible-webcam-live-stream-for-raspberry.git
```

Then run this command:

```
ansible-playbook -i 192.168.178.47, -u pi webcam.yml
```

You need to adapt the following to your situation:
- IP address (192.168.178.47).
- User (pi)

# Variables:
- `stream_port` (optional, default: 8081). Note: Motion uses 8080 for the web interface, you can't use that.

# Troubleshooting

- Make sure you add your SSH key first: `ssh-copy-id pi@192.168.178.47`
- Not finding a specific version of a package? The repository might be updated. Try to find the correct number yourself:
`apt-cache search libx264`