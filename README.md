# My Personal Homelab

## Overview

I created a small homelab with several services that I use for daily tasks such as:

- Saving and viewing my pictures and backing them up
- Writing documents like mails and notes
- Storing favorite YouTube videos for offline viewing
- Accessing my personal files securely

Developing this home lab required several weeks of iterative research, testing and troubleshooting. While some services were easy to deploy, others required intense configuration and debugging. The learning process involved many failed attempts, a great many hours of research and a systematic approach to problem-solving across the infrastructure's various components.

## Security Architecture

Access to my homenetwork is exclusively available via VPN. I chose this approach for the following reasons:

- **Reduced maintenance burden**: I don't need to keep multiple services constantly patched and up to date - lack of time are a reason for this
- **Minimal attack surface**: All services are isolated from the internet – they are only reachable through the VPN connection
- **Single point of security**: Only the VPN service needs to be extremely secure; all other services are protected by isolation
- **Device limitation awareness**: I understand that I can only access these services from devices with the VPN client installed, and I accept this trade-off

## Hardware Configuration

### System Specifications

- **Host Machine**: Dell computer (gifted)
- **Processor**: Intel Core i7-6700
- **Reason for Choice**: 
  - Built-in video encoding capabilities (enables streaming without dedicated graphics card)
  - Free acquisition reduced initial cost
  - The system consumes approximately 30 watts at idle (measured with CPU cores disabled and all boost functions deactivated in BIOS).

### Hardware Considerations

I'm aware that other configurations (such as Dell Wyse terminals) would be more power-efficient. However, these alternatives have limitations:

- Dell Wyse systems lack sufficient power supply capacity for more than one SATA hard drives
- My setup requires two HDDs, so Wyse would necessitate additional hardware investment
- The cost and complexity of upgrading would outweigh the benefits of my current system
- I would need a new case to properly mount and store the hard drives
- Since this hardware was free, further investment wasn't justified

## Software Stack

### Virtualization

- **Hypervisor**: Proxmox
- **Performance**: Runs very well with excellent performance for my use case
- **Easy to use**: Lots of tutorials for Proxmox in the internet, comprehensive documentation, and an intuitive user interface
- **Virtual Machines**: All VMs run fast enough for my daily needs

### Key Services

- **Nextcloud Container**: Includes Collabora Suite for document editing
- **Nginx**: Provides HTTPS encryption for secure connections
- **Etherpad**: Self-hosted note-taking application
- **Jellyfin**: Media server for viewing tutorials and videos offline
- **Adguard**: Network-wide ad blocking and DNS filtering (alternative to BIND, which proved overly complex for my needs)
- **Samba**: File sharing across network devices with native Windows compatibility
- Additional services running smoothly

## Performance Summary

Both Proxmox and all running VMs provide excellent performance. The system is fast enough for all my intended use cases, and I am satisfied with the current configuration.

---

## Appendix

For detailed setup instructions, architecture diagrams, and service configurations, see the `/docs` folder.

# Sources

The following tutorials, manuals, and guides helped me create this homelab:

## Language and Documentation Tools

- **DeepL Translator**: [https://www.deepl.com/de/translator](https://www.deepl.com/de/translator) - assisted in correcting this documentation and other project files
- **Perplexity AI**: [https://www.perplexity.ai/](https://www.perplexity.ai/) - used as a complementary research tool after extensive independent research through Google, forum posts, YouTube videos, and technical manuals

## Infrastructure and Virtualization

- **Proxmox Wiki**: [https://pve.proxmox.com/wiki/Main_Page](https://pve.proxmox.com/wiki/Main_Page) - primary resource for Proxmox configuration and troubleshooting
- **Thomas-Krenn Wiki**: [https://www.thomas-krenn.com/en/wiki/Main_Page](https://www.thomas-krenn.com/en/wiki/Main_Page) - general Linux and server administration guides
- **Quick and Easy Local SSL Certificates for Your Homelab** (Wolfgang's Channel): [https://www.youtube.com/watch?v=qlcVx-k-02E&t=598s](https://www.youtube.com/watch?v=qlcVx-k-02E&t=598s) - HTTPS/SSL certificate setup tutorial

## Container Images and Deployment

- **Docker Hub**: [https://hub.docker.com/search?badges=official&badges=verified_publisher&badges=open_source](https://hub.docker.com/search?badges=official&badges=verified_publisher&badges=open_source) - official and verified container images

## Service-Specific Documentation

### Nextcloud

- **Nextcloud All-in-One**: [https://github.com/nextcloud/all-in-one](https://github.com/nextcloud/all-in-one) - official Nextcloud installation and deployment method
- **Nextcloud AIO Quick Tutorial**: [https://blog.admin-intelligence.de/nextcloud-aio/](https://blog.admin-intelligence.de/nextcloud-aio/) - setup guide for the all-in-one installation

### Etherpad

- **Etherpad Docker Documentation**: [https://docs.etherpad.org/docker.html](https://docs.etherpad.org/docker.html) - Docker deployment guide

### AdGuard Home

- **AdGuardHome**: [https://github.com/AdguardTeam/AdGuardHome](https://github.com/AdguardTeam/AdGuardHome) - DNS filtering and ad blocking service

### Jellyfin

- **Jellyfin Downloads**: [https://jellyfin.org/downloads/linux](https://jellyfin.org/downloads/linux) - media server installation for Linux

### Standard Notes

- **Standard Notes**: [https://standardnotes.com/](https://standardnotes.com/) - best note taking app

