name: Build Angular App

on:
  push:
    branches:
      - main
  pull_request:
    branches:
      - main

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout repository
        uses: actions/checkout@v3

      - name: Setup Node.js
        uses: actions/setup-node@v3
        with:
          node-version: 18.x  # ✅ Fixed this

      - name: Install dependencies  # ✅ Fixed the incorrect indentation
        run: npm install

      - name: Build Angular App
        run: npm run build
g
