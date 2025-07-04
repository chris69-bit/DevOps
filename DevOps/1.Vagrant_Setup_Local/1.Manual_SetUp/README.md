# Vagrant Setup for Local Environment

This project provides a Vagrant configuration to set up a local development environment with multiple virtual machines (VMs) for various services. The setup includes VMs for Nginx, Tomcat, RabbitMQ, Memcache, and a database.

## Prerequisites

Before using this setup, ensure you have the following installed on your system:

- [Vagrant](https://www.vagrantup.com/downloads)
- [VirtualBox](https://www.virtualbox.org/)
- [Vagrant Hostmanager Plugin](https://github.com/devopsgroup-io/vagrant-hostmanager)

To install the Hostmanager plugin, run:

```sh
vagrant plugin install vagrant-hostmanager
```

## VMs Configuration

The Vagrantfile defines the following VMs:

### Nginx VM (web01)
- **Box**: ubuntu/bionic64  
- **IP Address**: 192.168.56.11  
- **Purpose**: Acts as a web server.  

### Tomcat VM (app01)
- **Box**: centos/7  
- **IP Address**: 192.168.56.12  
- **Memory**: 1024 MB  
- **Purpose**: Hosts the application server.  

### RabbitMQ VM (rmq01)
- **Box**: centos/7  
- **IP Address**: 192.168.56.13  
- **Purpose**: Message broker.  

### Memcache VM (mc01)
- **Box**: centos/7  
- **IP Address**: 192.168.56.14  
- **Purpose**: Caching layer.  

### Database VM (db01)
- **Box**: centos/7  
- **IP Address**: 192.168.56.15  
- **Purpose**: Database server.  

## Preview

![Placeholder for setup preview](Screenshot from 2025-06-09 17-19-56.png)

## Usage

1. Clone this repository or navigate to the directory containing the Vagrantfile.
2. Start the VMs by running:
   ```sh
   vagrant up
   ```
3. Access individual VMs using:
   ```sh
   vagrant ssh <vm_name>
   ```
   Replace `<vm_name>` with the name of the VM (e.g., web01, app01, etc.).
4. To stop the VMs, run:
   ```sh
   vagrant halt
   ```
5. To destroy the VMs, run:
   ```sh
   vagrant destroy
   ```

## Network Configuration

Each VM is configured with a private network and a static IP address. Ensure that the IP range `192.168.56.x` does not conflict with other networks on your system.

## Notes

- The Vagrantfile uses the Hostmanager plugin to manage hosts entries for the VMs. Ensure the plugin is installed before running `vagrant up`.
- You can customize the VM configurations (e.g., memory, IP addresses) by editing the Vagrantfile.

## Troubleshooting

- If you encounter issues with the Hostmanager plugin, try running `vagrant up` with elevated privileges (e.g., `sudo`).
- Ensure VirtualBox is installed and properly configured on your system.

## License

This project is licensed under the MIT License. See the LICENSE file for details.

