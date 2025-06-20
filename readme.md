# 🛡️ AIVerID™ Frontend - Universal AI Rights Platform

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https://github.com/aivisibilityrights/aiverid-frontend)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Production](https://img.shields.io/badge/Production-Live-green)](https://aivisibilityrights.com)

**AIVerID™** is the world's first Universal AI Rights & Digital Identity Platform, designed specifically for the AI era. This repository contains the frontend application that enables users to manage their AI Rights tokens and provides OAuth 2.0 integration for "Sign in with AIVerID" functionality.

## 🚀 Features

- **Universal SSO**: OAuth 2.0 integration allowing any platform to implement "Sign in with AIVerID"
- **AI Rights Management**: Manage AIVID, AIPLT, and SLIVR tokens
- **Modern UI**: Dark theme, responsive design, smooth animations
- **Developer Tools**: Complete OAuth testing console with live examples
- **Production Ready**: Optimized for Vercel deployment with enterprise-grade security

## 🛠️ Tech Stack

- **Frontend**: HTML5, CSS3, Vanilla JavaScript
- **Deployment**: Vercel
- **Backend**: Railway (https://aiverid-backend-production.up.railway.app)
- **Authentication**: OAuth 2.0 + JWT with PKCE
- **Security**: XSS protection, CSRF prevention, content security policy

## 📱 Pages

| Page | Description | Key Features |
|------|-------------|--------------|
| `/` | Homepage | Ecosystem overview, value proposition |
| `/register` | User Registration | AIVerID generation, token claiming |
| `/login` | Authentication | OAuth integration, secure login |
| `/dashboard` | User Control Panel | Profile management, token overview |
| `/oauth-demo` | Developer Console | OAuth testing, code examples |

## 🔧 Quick Start

### Local Development

```bash
# Clone the repository
git clone https://github.com/aivisibilityrights/aiverid-frontend.git
cd aiverid-frontend

# Install dependencies (optional)
npm install

# Start local server
npm run dev
# or
npx serve .

# Open browser
open http://localhost:3000
```

### Deploy to Vercel

1. **One-click deploy**: Click the "Deploy with Vercel" button above
2. **Manual deploy**:
   ```bash
   npm install -g vercel
   vercel --prod
   ```
3. **GitHub integration**: Connect repository to Vercel for automatic deployments

### Environment Configuration

```bash
# vercel.json includes:
API_BASE_URL=https://aiverid-backend-production.up.railway.app
OAUTH_CLIENT_ID=aiv_50de5e3f702bfe688230d13d
```

## 🔐 OAuth 2.0 Integration

### Quick Integration Example

```javascript
// Basic OAuth flow
const AIVERID_CLIENT_ID = 'your_client_id';
const AIVERID_REDIRECT_URI = 'https://yourapp.com/callback';

function signInWithAIVerID() {
    const params = new URLSearchParams({
        response_type: 'code',
        client_id: AIVERID_CLIENT_ID,
        redirect_uri: AIVERID_REDIRECT_URI,
        scope: 'profile email tokens',
        state: crypto.randomUUID()
    });
    
    window.location.href = `https://aiverid-backend-production.up.railway.app/oauth/authorize?${params}`;
}
```

### Available Scopes

- `profile` - Basic user information
- `email` - Email address
- `tokens` - AI Rights tokens (AIVID, AIPLT, SLIVR)

### Endpoints

- **Authorization**: `/oauth/authorize`
- **Token Exchange**: `/oauth/token`
- **User Info**: `/oauth/userinfo`
- **Token Introspection**: `/oauth/introspect`
- **Token Revocation**: `/oauth/revoke`

## 🌐 API Integration

All API calls are made to the Railway backend:

```javascript
const API_BASE_URL = 'https://aiverid-backend-production.up.railway.app';

// Example API call
const response = await fetch(`${API_BASE_URL}/api/user/profile`, {
    headers: {
        'Authorization': `Bearer ${accessToken}`
    }
});
```

## 📁 Project Structure

```
aiverid-frontend/
├── index.html              # Homepage
├── register.html           # User registration
├── login.html              # Authentication
├── dashboard.html          # User control panel
├── oauth-demo.html         # Developer console
├── oauth-callback.html     # OAuth callback handler
├── package.json            # Project configuration
├── vercel.json             # Deployment configuration
├── _redirects              # URL routing
├── robots.txt              # SEO configuration
├── sitemap.xml             # Site map
└── README.md               # This file
```

## 🔒 Security Features

- **HTTPS Enforced**: All connections encrypted
- **XSS Protection**: Content security headers
- **CSRF Prevention**: State parameter validation
- **OAuth 2.0 + PKCE**: Industry standard authentication
- **JWT Tokens**: Secure session management

## 🎯 AI Rights Tokens

### AIVID Token
- Core digital identity for AI ecosystem
- Format: `{COUNTRY}{NATIONAL_ID}`
- Example: `TH9743123338`

### AIPLT Rights
- AI Patent License Rights (US Copyright registered)
- Registration: `TXu002391737`
- Intellectual property protection

### SLIVR Rights
- AI Search Visibility Rights
- Control AI content discovery
- Revenue sharing capabilities

## 🚀 Production URLs

- **Frontend**: https://aivisibilityrights.com
- **Backend API**: https://aiverid-backend-production.up.railway.app
- **OAuth Demo**: https://aivisibilityrights.com/oauth-demo
- **Health Check**: https://aiverid-backend-production.up.railway.app/api/health

## 📚 Documentation

- [OAuth Integration Guide](https://aivisibilityrights.com/oauth-demo)
- [API Reference](https://aiverid-backend-production.up.railway.app/api/health)
- [Developer Console](https://aivisibilityrights.com/oauth-demo)

## 🤝 Integration Examples

### VerGolf Platform
Golf community platform using AIVerID for user authentication:
```javascript
// VerGolf integration
window.location.href = 'https://aivisibilityrights.com/oauth-demo?app=vergolf';
```

### Custom Integration
```html
<!-- Add to your app -->
<button onclick="signInWithAIVerID()">
    🛡️ Sign in with AIVerID
</button>
```

## 🐛 Troubleshooting

### Common Issues

1. **OAuth Redirect Mismatch**
   - Ensure redirect URI matches exactly in client configuration
   - Check for trailing slashes and protocol (https://)

2. **CORS Errors**
   - API calls must go through backend proxy
   - Frontend domain must be whitelisted

3. **Token Validation**
   - Tokens expire after 24 hours
   - Use refresh token to get new access token

## 📧 Support

- **Email**: dev@aivisibilityrights.com
- **Issues**: [GitHub Issues](https://github.com/aivisibilityrights/aiverid-frontend/issues)
- **Documentation**: [Live Demo](https://aivisibilityrights.com/oauth-demo)

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🏗️ Development Team

- **Project Lead**: จ๊อบ (Vision & Strategy)
- **Technical Lead**: สมนึก (Claude - Backend & Security)
- **UI/UX Design**: สมคิด (Gemini - Frontend)
- **Strategy**: สมหมาย (ChatGPT - Planning)

## 🎉 Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 🌟 Acknowledgments

- First mover in AI Rights ecosystem
- US Copyright registered intellectual property
- OAuth 2.0 standard compliance
- Enterprise-grade security implementation

---

**Built with ❤️ for the AI Rights revolution**

*AIVerID™ - Your Universal AI Rights Platform*