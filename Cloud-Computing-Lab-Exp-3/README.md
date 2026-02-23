# Cloud Computing Lab: Experiment 3
## Deployment of Bare-Metal Hypervisor (XenServer) in a Virtualized Environment

### Objective
The primary goal of this experiment is to demonstrate the installation and configuration of a Type-1 (Bare-metal) Hypervisor using Nested Virtualization techniques.

### Methodology
1. **Virtual Machine Creation**: Configured a VirtualBox VM with 4096 MB RAM and 2 CPUs.
2. **Enabling Nested Virtualization**: Enabled hardware virtualization assist inside the VM using the command: `VBoxManage modifyvm "XenServer_Lab" --nested-hw-virt on`.
3. **Hypervisor Installation**:
   - Booted from XenServer 8.4 ISO.
   - Configured local storage and skipped supplemental packs for a minimal setup.
   - Set administrative (root) credentials and network parameters.
4. **Network Reconfiguration**: Switched the network adapter from NAT to **Host-only Adapter** to allow communication between the host and hypervisor.
5. **Remote Management**: Used **XenCenter** on the host machine to connect to the server via its management IP (192.168.56.101).

### Observations
- **Nested Virtualization**: Initially, XenServer showed a hardware warning because nested virtualization wasn't enabled via CLI.
- **Connection Refused**: The connection was initially refused on the default NAT IP (10.0.2.15), necessitating a change to a Host-only network.
- **Management Console**: Once connected, XenCenter successfully displayed the server status, including CPU and Memory health.

### Result
The experiment was successful. A functional Bare-metal virtualization environment was successfully established, proving that Type-1 hypervisors can be effectively simulated in a nested virtual environment.
