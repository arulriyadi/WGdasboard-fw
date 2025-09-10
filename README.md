# WGDashboard with Firewall & Routing Extension

Complete WGDashboard setup with integrated firewall and routing management capabilities.

## Features

- **WireGuard VPN Management**: Full WireGuard server management
- **Firewall Management**: Add, delete, and reload iptables rules through web interface
- **Routing Management**: Manage static routes and view routing table
- **System Integration**: Seamlessly integrated into single dashboard interface

## Quick Start

### Prerequisites
- Ubuntu/Debian Linux system
- Python 3.6+
- iptables
- iproute2
- sudo access

### Installation & Running

1. **Clone the repository:**
   ```bash
   git clone https://github.com/arulriyadi/WGdasboard-fw.git
   cd WGdasboard-fw
   ```

2. **Run the application:**
   ```bash
   ./start.sh
   ```

3. **Access the dashboard:**
   - URL: `http://localhost:10086`
   - Username: `admin`
   - Password: `admin`

That's it! The script will automatically:
- Create virtual environment
- Install required dependencies
- Start the WGDashboard with firewall & routing features

## File Structure

```
WGdasboard-fw/
├── start.sh                 # Main startup script
├── requirements.txt         # Python dependencies
├── dashboard.py            # Main Flask application
├── wg-dashboard.ini        # Configuration file
├── modules/                # Backend modules
│   ├── FirewallManager.py  # iptables management
│   └── RouteManager.py     # routing table management
└── static/app/src/         # Frontend components
    ├── views/
    │   ├── firewall.vue    # Firewall management UI
    │   └── routing.vue     # Routing management UI
    ├── components/
    │   └── navbar.vue      # Navigation with new menu items
    ├── router/
    │   └── router.js       # Vue router configuration
    └── utilities/
        └── fetch.js        # API utilities
```

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

## Configuration

Edit `wg-dashboard.ini` to customize:
- Server port
- Admin credentials
- Database settings
- Other WGDashboard options

## Manual Installation (Alternative)

If you prefer manual setup:

1. **Install dependencies:**
   ```bash
   pip3 install -r requirements.txt
   ```

2. **Run directly:**
   ```bash
   python3 dashboard.py
   ```

## Troubleshooting

### Common Issues

1. **Permission denied on start.sh:**
   ```bash
   chmod +x start.sh
   ```

2. **Python packages not found:**
   ```bash
   pip3 install -r requirements.txt
   ```

3. **iptables permission denied:**
   - Run with sudo or ensure user is in appropriate groups
   - Check iptables is installed: `sudo apt install iptables`

4. **Port already in use:**
   - Change port in `wg-dashboard.ini`
   - Or kill existing process: `sudo lsof -ti:10086 | xargs kill`

## Security Notes

- Change default admin password in production
- Use HTTPS in production environments
- Consider firewall rules for production deployment
- Regular security updates recommended

## License

This project extends WGDashboard and follows the same license terms.
