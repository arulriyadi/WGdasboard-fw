# WGDashboard Firewall & Routing Extension

This repository contains the firewall and routing management modules for WGDashboard, a WireGuard VPN management interface.

## Features

- **Firewall Management**: Add, delete, and reload iptables rules through web interface
- **Routing Management**: Manage static routes and view routing table
- **System Integration**: Seamlessly integrated into WGDashboard interface

## Files

### Backend Modules
- `FirewallManager.py` - Python module for managing iptables firewall rules
- `RouteManager.py` - Python module for managing routing tables

### Frontend Components
- `firewall.vue` - Vue.js component for firewall management interface
- `routing.vue` - Vue.js component for routing management interface

## Installation

1. Copy the Python modules to your WGDashboard `src/modules/` directory
2. Copy the Vue components to your WGDashboard `src/static/app/src/views/` directory
3. Update your WGDashboard router and navbar components to include the new menu items
4. Restart WGDashboard service

## API Endpoints

### Firewall Management
- `GET /api/firewall/rules` - Get current firewall rules
- `POST /api/firewall/rules` - Add new firewall rule
- `DELETE /api/firewall/rules` - Delete firewall rule
- `POST /api/firewall/reload` - Reload firewall rules

### Routing Management
- `GET /api/routes` - Get current routing table
- `POST /api/routes` - Add new route
- `DELETE /api/routes` - Delete route
- `GET /api/system/info` - Get system information

## Requirements

- Python 3.6+
- iptables (for firewall management)
- iproute2 (for routing management)
- WGDashboard base application

## License

This project is part of WGDashboard and follows the same license terms.
