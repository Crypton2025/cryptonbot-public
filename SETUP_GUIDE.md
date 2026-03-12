# SETUP GUIDE - CryptonBot Pro+ Testnet

## Step 1: Create Binance Testnet Account

1. Go to https://testnet.binance.vision
2. Click "Log In with GitHub"
3. You get free testnet funds automatically

## Step 2: Generate API Keys

1. Click your profile on testnet.binance.vision
2. Click "Generate HMAC_SHA256 Key"
3. Copy API Key and Secret Key (shown only once!)

## Step 3: Configure the Bot

Copy .env.example to .env and fill in:
BINANCE_API_KEY=your_key
BINANCE_API_SECRET=your_secret
BINANCE_TESTNET=true

## Step 4: Run

docker compose up --build

## Step 5: Verify

Open http://localhost:8000/api/system/health

Questions? Telegram: https://t.me/+ghE0DKmPOmtlZDNk

Always use TESTNET first!
