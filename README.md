# Konnect

A modern financial management platform built with Next.js, React, and TypeScript. Konnect enables users to securely connect their bank accounts, view transaction histories, and manage payment transfers all in one intuitive interface.

## Features

- **Bank Account Integration**: Securely connect multiple bank accounts using Plaid
- **Transaction Tracking**: View and analyze your complete transaction history
- **Payment Transfers**: Transfer money between accounts using Dwolla
- **Dashboard Analytics**: Visualize your financial data with interactive charts and balance information
- **Responsive Design**: Fully responsive UI that works seamlessly on desktop and mobile devices
- **Authentication**: Secure user authentication and authorization
- **Real-time Updates**: Live data synchronization with banking partners

## Tech Stack

### Frontend
- **Framework**: Next.js 14+ (React)
- **Language**: TypeScript
- **Styling**: Tailwind CSS
- **UI Components**: Shadcn/ui
- **Form Handling**: React Hook Form
- **Charts**: Chart.js / Doughnut Charts

### Backend
- **Runtime**: Node.js
- **API Routes**: Next.js API Routes
- **Database**: Appwrite
- **Banking Integration**: Plaid (account linking)
- **Payment Processing**: Dwolla (money transfers)
- **Error Tracking**: Sentry

### DevOps
- **Containerization**: Docker
- **Orchestration**: Docker Compose
- **Package Manager**: npm/yarn

## Project Structure

```
├── app/                       # Next.js app directory
│   ├── (auth)/               # Authentication pages (sign-in, sign-up)
│   ├── (root)/               # Main app pages
│   │   ├── my-banks/         # Bank accounts page
│   │   ├── payment-transfer/ # Transfer funds page
│   │   └── transaction-history/ # Transaction history page
│   └── api/                  # API routes
├── components/               # Reusable React components
│   ├── ui/                  # Shadcn UI components
│   └── [component files]    # Custom components
├── lib/                      # Utility functions & configurations
│   ├── actions/             # Server actions
│   ├── appwrite.ts          # Appwrite client
│   ├── plaid.ts             # Plaid integration
│   └── utils.ts             # Helper functions
├── constants/               # Application constants
├── public/                  # Static assets
└── types/                   # TypeScript type definitions
```

## Getting Started

### Prerequisites

- Node.js 18+ and npm/yarn
- Docker & Docker Compose (optional, for containerized setup)
- Appwrite account
- Plaid account
- Dwolla account

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/konnect.git
   cd konnect
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Environment Variables**
   
   Create a `.env.local` file in the root directory:
   ```env
   # Appwrite
   NEXT_PUBLIC_APPWRITE_ENDPOINT=your_appwrite_endpoint
   APPWRITE_API_KEY=your_appwrite_api_key
   
   # Plaid
   NEXT_PUBLIC_PLAID_CLIENT_ID=your_plaid_client_id
   PLAID_SECRET=your_plaid_secret
   
   # Dwolla
   DWOLLA_APP_TOKEN=your_dwolla_token
   DWOLLA_APP_SECRET=your_dwolla_secret
   
   # Sentry
   NEXT_PUBLIC_SENTRY_AUTH_TOKEN=your_sentry_token
   ```

4. **Run the development server**
   ```bash
   npm run dev
   ```

   Open [http://localhost:3000](http://localhost:3000) in your browser.

### Docker Setup

To run the application using Docker:

```bash
docker-compose up
```

## Available Scripts

- `npm run dev` - Start development server with hot reload
- `npm run build` - Build for production
- `npm start` - Start production server
- `npm run lint` - Run ESLint for code quality
- `npm run format` - Format code with Prettier (if configured)

## Key Components

### Authentication
- **AuthForm**: Handles user sign-in and sign-up
- Located in `(auth)/` directory

### Dashboard
- **HeaderBox**: Page headers and titles
- **TotalBalanceBox**: Displays total account balance
- **BankCard**: Shows individual bank account details
- **DoughnutChart**: Visualizes spending by category

### Banking
- **PlaidLink**: Bank account connection integration
- **BankDropdown**: Select between connected bank accounts
- **BankTabItem**: Display bank information tabs
- **BankInfo**: Detailed bank account information

### Transactions
- **RecentTransactions**: Shows latest transactions
- **TransactionsTable**: Detailed transaction list with pagination
- **PaymentTransferForm**: Form for transferring money between accounts

## API Integration

### Plaid Integration
- Securely connect and authenticate bank accounts
- Retrieve account and transaction data
- File: `lib/plaid.ts`

### Dwolla Integration
- Process payment transfers between accounts
- Handle transaction settlement
- File: `lib/dwolla.ts`

### Appwrite Integration
- Store user data and banking information
- Manage user sessions and authentication
- File: `lib/appwrite.ts`

## Error Handling & Monitoring

Sentry is configured for error tracking and performance monitoring:
- `sentry.client.config.ts` - Client-side error handling
- `sentry.server.config.ts` - Server-side error handling
- `sentry.edge.config.ts` - Edge runtime error handling

## Security

- **Secure Authentication**: Industry-standard user authentication
- **Data Encryption**: All sensitive data is encrypted in transit and at rest
- **Bank-grade Security**: Plaid and Dwolla provide bank-level security
- **Environment Variables**: Sensitive credentials stored securely

## Performance

- **Server-Side Rendering**: Leverages Next.js SSR for optimal performance
- **Image Optimization**: Automatic image optimization
- **Code Splitting**: Automatic code splitting for faster load times
- **Tailwind CSS**: Optimized CSS with PurgeCSS

## Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Support

For support, email support@konnect.dev or open an issue on GitHub.

## Acknowledgments

- [Next.js](https://nextjs.org/) - React framework
- [Shadcn/ui](https://ui.shadcn.com/) - UI components
- [Plaid](https://plaid.com/) - Banking integration
- [Dwolla](https://www.dwolla.com/) - Payment processing
- [Appwrite](https://appwrite.io/) - Backend-as-a-Service
- [Sentry](https://sentry.io/) - Error tracking
