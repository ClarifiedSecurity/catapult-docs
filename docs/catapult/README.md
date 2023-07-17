# Catapult

## What is Catapult?

Catapult has been built as easy-to-use framework around Ansible to deploy and/or configure different types of environments, such as Cyber Exercises, Trainings, Labs or even Production environments. It is designed to be used by people with some experience with Ansible, but it is a force multiplier for experienced Ansible users. Catapult does the heavy lifting in Virtual Machine creation so the developer can focus on the actual content of the machine.

Catapult needs [KeePass](https://keepassxc.org/) with a key file, to store all of your personal passwords, tokens etc. This way the developer can store all of their secrets in an encrypted container and not worry about them being exposed. Catapult will ask you to decrypt the KeePass database on first run and use the secrets stored there to configure the environment.

This is the core version of Catapult that supports VM creation and configuration on vSphere, AWS, Linode and even VMware Workstation running on the developers own machine. It is also possible to use Catapult to configure an already existing virtual or physical machine.

Catapult runs in a Docker container. This way the developer only needs a few dependencies installed on their own machine. The main requirement is Docker.

Catapult also designed to be modifiable by the developer or the organization using it without the need to modify this project itself.

Refer to [Catapult Docs](https://github.com/ClarifiedSecurity/Catapult-Docs/tree/main/docs) for getting started and usage instructions.
