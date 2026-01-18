# PrestaShop Module Installer

A bash script to manage PrestaShop module installation, uninstallation, and deployment in Docker environments.

## Features

- Interactive menu with keyboard navigation
- Install/Uninstall/Reinstall modules via PrestaShop CLI
- Automatic backup before each installation (keeps last 5)
- Restore from backup
- Clear PrestaShop cache
- Restart Docker containers
- Build production-ready ZIP archives
- Auto-update from remote repository
- CLI flags for automation/scripting

## Requirements

- Docker with a running PrestaShop container
- Bash shell
- `zip` command (for building archives)

## Setup

1. Copy the configuration example:
   ```bash
   cp .env.install.example .env.install
   ```

2. Edit `.env.install` with your settings:
   ```bash
   PRESTASHOP_PATH="/path/to/your/prestashop"
   DOCKER_CONTAINER="your_container_name"
   MODULE_NAME="yourmodulename"
   ```

3. Place your module folder next to `install.sh`:
   ```
   Module Installer/
   ├── install.sh
   ├── .env.install
   └── yourmodulename/
       └── yourmodulename.php
   ```

4. Make executable:
   ```bash
   chmod +x install.sh
   ```

## Usage

### Interactive Mode

```bash
./install.sh
```

Use arrow keys (or `j`/`k`) to navigate, Enter to select, `q` or Esc to quit.

### CLI Mode

```bash
./install.sh --install      # Install / Reinstall
./install.sh --uninstall    # Uninstall
./install.sh --reinstall    # Uninstall then Reinstall
./install.sh --delete       # Delete files
./install.sh --reset        # Delete then Reinstall
./install.sh --restore      # Restore from backup
./install.sh --cache        # Clear cache
./install.sh --restart      # Restart Docker containers
./install.sh --zip          # Build ZIP archive
./install.sh --update-script # Check for script updates
./install.sh --help         # Show help
```

## License

MIT
