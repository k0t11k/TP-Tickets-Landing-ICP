Tickets Partner - Event Ticketing DApp on Internet Computer

Tickets Partner is a decentralized application built on the Internet Computer (ICP) for purchasing event tickets via a Telegram bot. It provides a seamless user experience with a React-based frontend and a Motoko-based backend, supporting payments in cryptocurrencies (e.g., USDT, BTC) and fiat via LiqPay. The platform enables fast, secure, and transparent ticketing for concerts, theater performances, sports events, and more. Table of Contents

Features Architecture Tech Stack Prerequisites Installation Building and Deploying Locally Deploying to ICP Usage File Structure Contributing License Contact

Features

Fast Ticket Purchases: Buy tickets for events directly through a Telegram bot (@TP_TicketsPartner). Flexible Payments: Supports cryptocurrencies (USDT, BTC, SOL) and fiat payments via LiqPay (Visa, MasterCard, Privat24). Secure Transactions: Uses QR codes for ticket validation and SSL encryption for data protection. Event Management: Organizers can create events, manage tickets, and track sales via the Telegram bot. Responsive Frontend: Built with React, Tailwind CSS, and Slick Carousel for a modern, mobile-friendly interface. Decentralized Backend: Powered by Motoko on ICP for transparent and persistent data storage.

Architecture The DApp consists of two main components:

Frontend Canister: A React-based single-page application (SPA) served as an asset canister. Integrates with Telegram Web App for seamless user interaction. Styled with Tailwind CSS and includes a carousel for showcasing top events.

Backend Canister: Written in Motoko, a programming language for ICP. Manages basic greeting logic (extendable for event and ticket management). Persists data using stable variables for canister upgrades.

The canisters are configured via dfx.json and deployed to the ICP blockchain using the DFX CLI or ICP Ninja. Tech Stack

Frontend: React 18.2.0 Tailwind CSS (CDN) Slick Carousel jQuery Telegram Web App SDK

Backend: Motoko DFX (Internet Computer SDK)

Configuration: dfx.json for canister definitions mops.toml for Motoko dependencies

Deployment: Internet Computer (ICP) ICP Ninja (optional for quick deployments)

Prerequisites Before setting up the project, ensure you have the following installed:

Node.js (v18.x or later) DFX CLI (v0.15.x or later)sh -ci "$(curl -fsSL https://internetcomputer.org/install.sh)"

MOPS (Motoko package manager)npm install -g @dfinity/mops

A code editor (e.g., VS Code with the Motoko extension) An ICP wallet with cycles for deployment (e.g., via NNS)

Installation

Clone the Repository:git clone https://github.com/your-username/tickets-partner.git cd tickets-partner

Install Frontend Dependencies (if using a build tool like Vite):npm install

Note: The current frontend uses CDN links, so this step is optional unless you add a build tool. Install Motoko Dependencies:mops install

Start the Local ICP Replica:dfx start --background

Building and Deploying Locally

Build the Project:dfx build

This compiles the Motoko backend and prepares the frontend assets. Deploy Locally:dfx deploy

Access the frontend at http://localhost:4943/?canisterId= and the backend at .localhost:4943. Test the Backend:Use the Candid UI (available at .localhost:4943/candid) to call methods like greet or setGreeting.

Deploying to ICP

Configure Your Identity:dfx identity new --storage-mode=plaintext dfx identity use

Fund Your Wallet:Acquire cycles via the NNS or another ICP wallet provider. Deploy to the Mainnet:dfx deploy --network ic

The frontend will be available at .icp0.io, and the backend at .icp0.io. Alternative: Use ICP Ninja: Open ICP Ninja. Upload your project files (frontend/, backend/, dfx.json, mops.toml). Click "Build & Deploy" to deploy to ICP.

Usage

Access the Frontend: Visit the deployed URL (e.g., .icp0.io). Explore top events, features, and FAQs. Use the "Try Now" button to interact with the Telegram bot (@TP_TicketsPartner).

Interact with the Telegram Bot: Open @TP_TicketsPartner in Telegram. Follow the bot's instructions to browse events, purchase tickets, or create new events.

Backend Interaction (for developers): Call the greet method to retrieve a greeting:dfx canister call backend greet '("World")'

Update the greeting prefix:dfx canister call backend setGreeting '("Hello, ICP")'

File Structure tickets-partner/ ├── backend/ │ └── app.mo # Motoko backend logic ├── frontend/ │ └── index.html # React-based frontend ├── dfx.json # Canister configuration ├── mops.toml # Motoko dependencies └── README.md # Project documentation

Contributing Contributions are welcome! To contribute:

Fork the repository. Create a new branch (git checkout -b feature/your-feature). Make your changes and commit (git commit -m "Add your feature"). Push to your branch (git push origin feature/your-feature). Open a Pull Request with a detailed description of your changes.

Please follow the Code of Conduct and ensure your code adheres to the project's style guidelines. License This project is licensed under the MIT License. Contact For questions or support, contact: Founder creator Y Telegram contact https://t.me/project_t1p

Follow us on Telegram for updates and event announcements!
