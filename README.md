# pteroinstall
pterodactyl 1.0+ installation script

Made for Ubuntu 24.04 fresh install
Uses 1 FQDN for both panel and Daemon

- 2025 Ferox Hosting

## New Feature: Automatic Node Creation

The installation script now automatically creates a node in the Pterodactyl database when installing both panel and daemon together. This eliminates the need for manual node creation through the web interface.

### What happens automatically:
- **Machine specification detection**: Automatically detects CPU cores, RAM, and disk space
- **Node creation**: Creates a node entry in the database with detected specifications
- **Unique identification**: Generates a unique UUID and descriptive name for the node
- **Database integration**: Links the node to the database host configuration

### Important notes:
- Automatic node creation only works when installing **both panel and daemon** together
- For daemon-only installations, manual node creation is still required
- After automatic node creation, you must complete the configuration through the panel:
  1. Log into your Pterodactyl panel
  2. Go to Admin -> Nodes
  3. Click on the auto-created node
  4. Copy the configuration from the Configuration tab to `/etc/pterodactyl/config.yml`

### Machine specifications detected:
- **CPU Cores**: Total number of CPU cores available
- **RAM**: Total system memory in MB
- **Disk Space**: Total disk space of root filesystem in MB
- **Network**: Server's public IP address and provided FQDN
