# Git Credential Manager Installation Guide
**Platform**: Ubuntu
**Storage Method**: Plain Text
**Last Updated**: February 10, 2025

## Prerequisites
- Ubuntu 20.04 or later
- Git installed
- Administrator privileges

## Installation Steps

### 1. Install Required Dependencies
First, ensure all required dependencies are installed:
```bash
sudo apt-get update
sudo apt-get install -y curl libsecret-1-0 dotnet-runtime-6.0
```

### 2. Download Git Credential Manager
Download the latest version of Git Credential Manager:
```bash
curl -LO "https://github.com/GitCredentialManager/git-credential-manager/releases/latest/download/gcm-linux_amd64.deb"
```

### 3. Install the Package
Install the downloaded package:
```bash
sudo dpkg -i gcm-linux_amd64.deb
```

### 4. Configure Git to Use Plain Text Storage
Set up Git to use plain text storage for credentials:
```bash
git config --global credential.credentialStore plaintext
```

### 5. Configure Git Credential Manager
Initialize Git Credential Manager:
```bash
git-credential-manager configure
```

### 6. Verify Installation
Verify that Git Credential Manager is installed correctly:
```bash
git-credential-manager --version
```

## Configuration Testing

1. Try cloning a repository that requires authentication:
```bash
git clone https://github.com/username/repository.git
```

2. Enter your credentials when prompted
3. Verify that the credentials are stored by checking:
```bash
cat ~/.git-credentials
```

## Troubleshooting

### Common Issues and Solutions

1. **Installation Fails**
   - Ensure all dependencies are installed
   - Check system architecture compatibility
   - Verify administrator privileges

2. **Credentials Not Saving**
   - Confirm plain text storage is configured
   - Check file permissions on ~/.git-credentials
   - Ensure proper ownership of configuration files

3. **Authentication Errors**
   - Verify credentials are correct
   - Check network connectivity
   - Ensure repository URL is correct

## Uninstallation

If needed, remove Git Credential Manager:
```bash
sudo dpkg -r gcm
git config --global --unset credential.helper
git config --global --unset credential.credentialStore
rm ~/.git-credentials
```

## Support

For additional support:
- Visit the [Git Credential Manager GitHub repository](https://github.com/GitCredentialManager/git-credential-manager)
- Check Ubuntu documentation
- Consult your system administrator

## Security Notice

Please note that storing credentials in plain text is less secure than encrypted storage. Consider using this configuration only in controlled environments and never store sensitive credentials this way on shared or public systems.