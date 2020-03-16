# Ansible playbook for Jitsi Meet

This playbook sets up [Jitsi Meet](https://jitsi.org/jitsi-meet/) so that it can be used to have video conferences via the Internet.

It has been tested on Debian Buster servers.

It uses the [official docker-compose setup](https://github.com/jitsi/docker-jitsi-meet).

## Configuration

You have to create an `inventory` file. It should look something like the following:

```ini
meet.example.com ansible_user=root letsencrypt_email=contact@example.com
```

`meet.example.com` should be replaced by the name where your server is reachable.

`contact@example.com` should be replaced by your email address where you will be notified for any administrative tasks related to let's encrypt.

## Installation

Run the Ansible playbook:

```console
ansible-playbook -i inventory site.yml
```

It should complete without any errors.

## Usage

Once all the containers have started up (this may take a minute or two), your new Jitsi Meet installation should now be reachable at `https://meet.example.com`.
