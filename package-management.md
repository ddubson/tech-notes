## Package Management

Yum is getting replaced!

YUM and RPM are currently standard to install apps

```bash
# List all applications that are installed:
yum list installed

# Download package, not install it
yumdownloader [packagename]

# Install locally
yum localinstall [rpm-name]

# Figure out what package provides a certain command
yum provides [command]

# Check if there are updates
yum check-update

# Get information on a package
yum info [package]

# List the repositories on the system
yum repolist

# Enable a repository if disabled
yum --enablerepo=[repository]
```



