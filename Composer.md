Here’s a straightforward, official way to install **Composer** (the PHP dependency manager) on Linux/macOS/WSL:

---
### 1. Prerequisites

Make sure you have PHP installed:

```bash
php -v
```

If not installed, install PHP first (depending on your system, e.g., on Ubuntu/Debian):

```bash
sudo apt update
sudo apt install php-cli unzip curl
```

---
### 2. Download and install Composer globally

Run these commands step-by-step in your terminal:

```bash
# Download the Composer installer script
php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"

# (Optional) Verify the installer SHA-384 hash (recommended for security)
HASH="$(curl -s https://composer.github.io/installer.sig)"
php -r "if (hash_file('SHA384', 'composer-setup.php') === '$HASH') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;"

# Run the installer (this installs composer.phar in current directory)
php composer-setup.php

# Remove the installer script
php -r "unlink('composer-setup.php');"

# Move composer.phar to a directory in your PATH to run it globally
sudo mv composer.phar /usr/local/bin/composer

# Make it executable
sudo chmod +x /usr/local/bin/composer
```

---
### 3. Test Composer installation

```bash
composer --version
```

You should see something like:

```
Composer version 2.x.x ...
```

---
### Alternative: Install Composer per-project only

You can just run `php composer-setup.php` inside your project folder, then run Composer with

```bash
php composer.phar [commands]
```

But installing globally as above is easier for day-to-day use.