# SO Deploy

Instantly deploy a website to your Cloudflare domain with one command:

```bash
cd my-app
so
```

## What and why

I use [surge.sh](https://surge.sh/) to quickly deploy web projects for sharing and testing. SO Deploy does the same but using your own domain.

When you run the `so` command in a folder, it creates a new public subdomain (eg. `https://my-folder.my-domain.com`) and deploys the contents of that folder to it within seconds.

To remove this site, simply run `so teardown`

## Requirements

A domain hosted on Cloudflare.

## Install

```bash
# Install the script by moving it to /usr/local/bin/ 
sudo mv so /usr/local/bin/

# Give it the right permissions
chmod +x /usr/local/bin/so

# Install dependencies: curl and jq
brew install jq curl
```

## Setup

### 1. Create an API token with the following permissions: 
  - Account: Worker Scripts: Edit
  - Zone: Zone: Edit
  - Zone: DNS: Edit
  - Zone: Workers Routes: Edit

### 2. Run setup

```bash
# Run the setup
so setup
```

You'll need the following Cloudflare credentials:

- The API token you just created
- Account ID (account home settings -> Copy account ID)
- Zone ID (domain settings -> Copy zone ID)
- Base domain (eg. mydomain.com)


## Commands

```bash
# Deploy current folder
so

# Deploy with custom subdomain
so -d <name> 

# List all deployed sites
so list

# Delete current folder's site
so teardown

# Delete specific site
so teardown <name>

# Configure Cloudflare credential
so setup
```