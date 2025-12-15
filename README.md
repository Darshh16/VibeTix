# VibeTix - Event Booking Progressive Web App 🎫

A modern, full-featured Progressive Web App (PWA) for discovering and booking tickets to events. Built with seamless payment integration, user authentication, and offline capabilities for the ultimate event booking experience.

![PWA](https://img.shields.io/badge/PWA-Enabled-5A0FC8?logo=pwa)
![Payment](https://img.shields.io/badge/Payment-Razorpay-02042B?logo=razorpay)
![License](https://img.shields.io/badge/license-MIT-blue.svg)

## ✨ Features

### 🎯 Core Functionality
- **Event Discovery**: Browse upcoming events by category, location, and date
- **Advanced Search**: Filter events by venue, price range, and event type
- **Real-time Availability**: Check seat availability and ticket status instantly
- **Secure Booking**: End-to-end encrypted booking process
- **E-Tickets**: Digital tickets delivered instantly to your device
- **QR Code Generation**: Unique QR codes for event entry verification

### 💳 Payment Integration
- **Razorpay Gateway**: Secure payment processing with PCI compliance
- **Multiple Payment Methods**: 
  - Credit/Debit Cards
  - UPI (Google Pay, PhonePe, Paytm)
  - Net Banking
  - Wallets (Paytm, PhonePe, Amazon Pay)
- **Instant Confirmation**: Immediate booking confirmation and receipt
- **Refund Management**: Easy cancellation and automated refund processing
- **Payment History**: Track all your transactions in one place

### 🔐 Authentication & Security
- **User Authentication**: Secure login/signup with JWT tokens
- **Social Login**: Quick sign-in with Google/Facebook
- **Two-Factor Authentication**: Optional 2FA for enhanced security
- **Session Management**: Secure session handling with auto-logout
- **Password Recovery**: Easy password reset via email/SMS
- **Profile Management**: Update personal details and preferences

### 📱 Progressive Web App Features
- **Offline Mode**: Browse events and view bookings without internet
- **Add to Home Screen**: Install like a native app
- **Push Notifications**: Real-time updates on events and bookings
- **Fast Loading**: Optimized performance with service workers
- **Responsive Design**: Seamless experience across all devices
- **Background Sync**: Auto-sync data when connection is restored

### 🎨 User Experience
- **Intuitive Interface**: Clean and modern UI/UX design
- **Personalized Recommendations**: AI-powered event suggestions
- **Favorites**: Save events to wishlist for later
- **Booking History**: Access all past and upcoming bookings
- **Ratings & Reviews**: Read and write event reviews
- **Share Events**: Share events with friends via social media

## 🛠️ Tech Stack

### Frontend
- **React.js / Next.js**: Component-based UI development
- **Redux / Context API**: State management
- **Tailwind CSS / Material-UI**: Styling and components
- **PWA Tools**: Workbox for service worker management
- **Axios**: API communication

### Backend
- **Node.js + Express**: RESTful API development
- **MongoDB / PostgreSQL**: Database for event and user data
- **JWT**: Secure authentication tokens
- **Bcrypt**: Password encryption
- **Nodemailer**: Email notifications

### Payment & Integration
- **Razorpay SDK**: Payment gateway integration
- **Razorpay Webhooks**: Real-time payment status updates
- **QR Code Generator**: Ticket validation system

### DevOps & Hosting
- **Vercel / Netlify**: Frontend deployment
- **AWS / Heroku**: Backend hosting
- **MongoDB Atlas / AWS RDS**: Cloud database
- **Cloudinary**: Image storage and optimization
- **GitHub Actions**: CI/CD pipeline

## 📋 Prerequisites

- Node.js 16.x or higher
- npm or yarn
- MongoDB or PostgreSQL database
- Razorpay account ([Sign up here](https://razorpay.com/))
- Email service (Gmail SMTP or SendGrid)

## 🚀 Installation & Setup

### 1. Clone the repository
```bash
git clone https://github.com/yourusername/eventhub-pwa.git
cd eventhub-pwa
```

### 2. Install dependencies

**Frontend:**
```bash
cd client
npm install
```

**Backend:**
```bash
cd server
npm install
```

### 3. Environment Configuration

Create `.env` files in both client and server directories:

**Client `.env`:**
```env
REACT_APP_API_URL=http://localhost:5000/api
REACT_APP_RAZORPAY_KEY=your_razorpay_key_id
REACT_APP_GOOGLE_CLIENT_ID=your_google_client_id
```

**Server `.env`:**
```env
PORT=5000
MONGODB_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret_key
JWT_EXPIRE=7d

# Razorpay Configuration
RAZORPAY_KEY_ID=your_razorpay_key_id
RAZORPAY_KEY_SECRET=your_razorpay_key_secret

# Email Configuration
EMAIL_HOST=smtp.gmail.com
EMAIL_PORT=587
EMAIL_USER=your_email@gmail.com
EMAIL_PASSWORD=your_app_password

# Cloud Storage
CLOUDINARY_NAME=your_cloudinary_name
CLOUDINARY_API_KEY=your_api_key
CLOUDINARY_API_SECRET=your_api_secret
```

### 4. Run the Application

**Development Mode:**

Terminal 1 (Backend):
```bash
cd server
npm run dev
```

Terminal 2 (Frontend):
```bash
cd client
npm start
```

**Production Build:**
```bash
# Frontend
cd client
npm run build

# Backend
cd server
npm start
```

Access the app at `http://localhost:3000`

## 📁 Project Structure

```
eventhub-pwa/
│
├── client/                      # Frontend React App
│   ├── public/
│   │   ├── manifest.json       # PWA manifest
│   │   ├── service-worker.js   # Service worker
│   │   └── icons/              # App icons
│   │
│   ├── src/
│   │   ├── components/
│   │   │   ├── Auth/           # Login, Signup components
│   │   │   ├── Events/         # Event listing, details
│   │   │   ├── Booking/        # Booking flow components
│   │   │   ├── Payment/        # Razorpay integration
│   │   │   └── Profile/        # User profile pages
│   │   │
│   │   ├── pages/
│   │   │   ├── Home.jsx
│   │   │   ├── EventDetails.jsx
│   │   │   ├── Checkout.jsx
│   │   │   └── MyBookings.jsx
│   │   │
│   │   ├── services/
│   │   │   ├── api.js          # API calls
│   │   │   ├── auth.js         # Auth service
│   │   │   └── payment.js      # Payment service
│   │   │
│   │   ├── utils/
│   │   │   ├── storage.js      # LocalStorage helpers
│   │   │   └── validators.js   # Form validation
│   │   │
│   │   ├── context/            # Context API providers
│   │   ├── hooks/              # Custom React hooks
│   │   └── App.jsx
│   │
│   └── package.json
│
├── server/                      # Backend Node.js API
│   ├── controllers/
│   │   ├── authController.js
│   │   ├── eventController.js
│   │   ├── bookingController.js
│   │   └── paymentController.js
│   │
│   ├── models/
│   │   ├── User.js
│   │   ├── Event.js
│   │   ├── Booking.js
│   │   └── Payment.js
│   │
│   ├── routes/
│   │   ├── auth.js
│   │   ├── events.js
│   │   ├── bookings.js
│   │   └── payments.js
│   │
│   ├── middleware/
│   │   ├── auth.js             # JWT verification
│   │   ├── errorHandler.js
│   │   └── validator.js
│   │
│   ├── utils/
│   │   ├── razorpay.js         # Razorpay helper
│   │   ├── emailService.js     # Email sender
│   │   └── qrGenerator.js      # QR code generator
│   │
│   ├── config/
│   │   └── database.js         # DB connection
│   │
│   ├── server.js
│   └── package.json
│
├── .gitignore
├── README.md
└── LICENSE
```

## 💻 Usage Guide

### For Users

#### 1. **Discovering Events**
- Browse the homepage for featured events
- Use search and filters to find specific events
- View detailed event information including venue, date, and pricing

#### 2. **Booking Tickets**
- Select your desired event
- Choose ticket quantity and category
- Review booking details
- Proceed to secure checkout

#### 3. **Payment Process**
- Choose your preferred payment method
- Complete payment via Razorpay
- Receive instant confirmation email
- Download e-ticket with QR code

#### 4. **Managing Bookings**
- View all bookings in "My Bookings" section
- Download tickets anytime
- Cancel bookings and get refunds
- Rate and review attended events

### For Event Organizers (Admin)

#### 1. **Creating Events**
- Access admin dashboard
- Fill in event details (name, description, venue, date)
- Upload event images
- Set ticket prices and availability
- Publish event

#### 2. **Managing Events**
- Track ticket sales in real-time
- Update event information
- Monitor attendee list
- Generate sales reports
- Process refunds

## 🔒 Security Features

- **Data Encryption**: All sensitive data encrypted in transit and at rest
- **SQL Injection Protection**: Parameterized queries and ORM usage
- **XSS Prevention**: Input sanitization and output encoding
- **CSRF Protection**: Token-based CSRF prevention
- **Rate Limiting**: API rate limiting to prevent abuse
- **Secure Headers**: HTTP security headers via Helmet.js
- **Payment Security**: PCI DSS compliant Razorpay integration

## 📱 PWA Features Explained

### Offline Functionality
```javascript
// Service worker caches essential resources
- Event listings cached for offline viewing
- User bookings available without internet
- Graceful degradation for unavailable features
```

### Push Notifications
```javascript
// Users receive notifications for:
- Booking confirmations
- Event reminders (24 hours before)
- Cancellation updates
- Special offers and promotions
```

### Installation
```javascript
// Installable on:
- Android devices (Chrome)
- iOS devices (Safari 11.3+)
- Desktop (Chrome, Edge)
```

## 🎨 Customization

### Branding
Update the following files to customize branding:
- `client/public/manifest.json` - App name and theme color
- `client/public/icons/` - Replace with your logo
- `client/src/styles/theme.js` - Update color scheme

### Payment Gateway
While Razorpay is integrated, you can switch to other gateways:
```javascript
// In client/src/services/payment.js
// Replace Razorpay logic with your preferred gateway
```

## 🧪 Testing

### Run Tests
```bash
# Frontend tests
cd client
npm test

# Backend tests
cd server
npm test

# E2E tests
npm run test:e2e
```

### Test Coverage
```bash
npm run test:coverage
```

## 🚀 Deployment

### Frontend (Vercel/Netlify)
```bash
# Build the app
cd client
npm run build

# Deploy to Vercel
vercel --prod

# Or deploy to Netlify
netlify deploy --prod
```

### Backend (Heroku/AWS)
```bash
# Heroku deployment
cd server
heroku create your-app-name
git push heroku main

# Or use Docker
docker build -t eventhub-api .
docker run -p 5000:5000 eventhub-api
```

### Database
- **MongoDB Atlas**: Cloud-hosted MongoDB
- **AWS RDS**: For PostgreSQL deployment

## 📊 Features Roadmap

- [ ] Multi-language support
- [ ] Virtual events integration
- [ ] Seat map selection
- [ ] Group booking discounts
- [ ] Loyalty rewards program
- [ ] Event recommendations AI
- [ ] Live chat support
- [ ] Calendar integration
- [ ] Social sharing enhancements
- [ ] Advanced analytics dashboard

## 🐛 Known Issues & Solutions

| Issue | Solution |
|-------|----------|
| Payment popup blocked | Allow popups in browser settings |
| Offline sync delay | Clear cache and reload app |
| Push notifications not working | Enable notification permissions |

## 🤝 Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

### Coding Guidelines
- Follow ESLint rules
- Write meaningful commit messages
- Add tests for new features
- Update documentation

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- [Razorpay](https://razorpay.com/) for secure payment processing
- [React](https://react.dev/) for the amazing UI framework
- [Workbox](https://developers.google.com/web/tools/workbox) for PWA tools
- All open-source contributors

## 📞 Support

- **Documentation**: [Full Docs](https://docs.eventhub.com)
- **Issues**: [GitHub Issues](https://github.com/yourusername/eventhub-pwa/issues)
- **Email**: support@eventhub.com
- **Discord**: [Join our community](https://discord.gg/eventhub)

## 📈 Performance Metrics

- **Lighthouse Score**: 95+ (Performance, PWA, Accessibility)
- **First Contentful Paint**: < 1.5s
- **Time to Interactive**: < 3s
- **Bundle Size**: < 200KB (gzipped)

---

<div align="center">

**Built with ❤️ for seamless event booking experiences**

⭐ Star this repo if you find it helpful!

[Live Demo](https://eventhub-demo.vercel.app) | [Documentation](https://docs.eventhub.com) | [Report Bug](https://github.com/yourusername/eventhub-pwa/issues)

</div>
