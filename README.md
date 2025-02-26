# Welcome to Nuxt.js on Profihost!

A modern, production-ready template for deploying Nuxt.js applications on Profihost hosting services.

## Features

- 🚀 Server-side rendering with Nuxt.js
- ⚡️ Hot Module Replacement (HMR) for development
- 📦 Asset bundling and optimization
- 🔄 Automatic API route generation
- 🔒 TypeScript support out of the box
- 🌐 Easy deployment on Profihost servers
- 🔄 Daemon service for continuous uptime
- 🔀 Apache reverse proxy configuration
- 📖 [Nuxt.js docs](https://nuxt.com/docs)

## Getting Started

### Prerequisites

First, install Node Version Manager (NVM) to manage your Node.js versions:

```bash
# Install NVM
wget -qO- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.5/install.sh | bash

# Load NVM environment
export NVM_DIR="$HOME/.nvm"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"
[ -s "$NVM_DIR/bash_completion" ] && \. "$NVM_DIR/bash_completion"

# Install latest LTS version of Node.js
nvm install --lts
```

### Installation

Create a new Nuxt project and install dependencies:

```bash
# Create a new Nuxt project
npx nuxi@latest init my-nuxt-app

# Navigate to project directory
cd my-nuxt-app

# Install dependencies
npm install
```

### Development

Start the development server with HMR:

```bash
npm run dev
```

Your application will be available at `http://localhost:3000`.

## Building for Production

Create a production build:

```bash
npm run build
```

## Deployment on Profihost

### 1. Set Up a Service Daemon

To keep your Nuxt application running continuously:

```bash
# Download the preconfigured daemon script
wget -O nuxt-daemon.json https://raw.githubusercontent.com/haupt-pascal/profihost-nuxt/main/daemon.sh
```

After downloading the daemon file:

1. Log in to your Profihost customer center
2. Navigate to your server settings
3. Look for the "Daemon" or "Service Daemon" option
4. Upload the `daemon.sh` file to your storage
5. Adjust the paths within the script as needed
6. Set the path to the script as the command/script
7. Activate the daemon

### 2. Configure Reverse Proxy with .htaccess

Set up an Apache reverse proxy to make your Nuxt application accessible through your domain:

```bash
# Create an .htaccess file in your website's root directory
cat > .htaccess << 'EOL'
DirectoryIndex disabled

RewriteEngine On

RewriteRule (.*) http://DAEMON_IP_ADDRESS:3000/$1 [P,L]
EOL

# Alternatively, download a preconfigured .htaccess file
wget -O .htaccess https://raw.githubusercontent.com/haupt-pascal/profihost-nuxt/main/.htaccess
```

Don't forget to replace `DAEMON_IP_ADDRESS` with your actual server IP address.

## Configuration Options

### nuxt.config.ts

Optimize your Nuxt configuration for Profihost:

```typescript
// nuxt.config.ts
export default defineNuxtConfig({
  // Enable SSR mode
  ssr: true,
  
  // Set host to listen on all network interfaces
  devServer: {
    host: '0.0.0.0'
  },
  
  // Configure server preset
  nitro: {
    preset: 'node-server'
  }
})
```

## Troubleshooting

- If you encounter port conflicts, modify the port (default: 3000) in your daemon configuration
- For any issues, contact Profihost support at support@profihost.com

## Additional Resources

- [Nuxt Documentation](https://nuxt.com/docs) - Comprehensive guide to Nuxt features
- [Profihost Nuxt Examples](https://github.com/haupt-pascal/profihost-nuxt) - Sample configurations for Profihost deployments

---

Built with ❤️ using Nuxt.js and hosted on Profihost.
