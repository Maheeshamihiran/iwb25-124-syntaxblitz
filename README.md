# iwb25-124-syntaxblitz

A comprehensive full-stack weather application featuring real-time weather data, marine forecasts, astronomical information, and an integrated news management system.

## 🌟 Overview

This project combines multiple technologies to deliver a complete weather information platform:
- **Frontend**: React.js weather dashboard
- **Admin Panel**: React.js news management interface
- **Backend**: Ballerina microservices for weather data and news management
- **APIs**: Integration with OpenWeatherMap and StormGlass for comprehensive weather data

## 🛠️ Tech Stack

- **Frontend**: React.js, CSS, HTML
- **Backend**: Ballerina (14.7%)
- **Languages**: JavaScript (43.6%), CSS (36.7%), Ballerina (14.7%), HTML (5%)

## 📋 Prerequisites

Before you begin, ensure you have the following installed:
- Node.js (v14 or higher)
- npm or yarn
- Ballerina (latest version)

## 🔑 API Keys Setup

### Required API Keys

1. **OpenWeatherMap API Key**
   - Visit: https://openweathermap.org/api
   - Sign up for a free account
   - Generate an API key from your dashboard

2. **StormGlass API Key** (for marine weather)
   - Visit: https://stormglass.io/
   - Sign up for a free account
   - Generate an API key from your dashboard

### Configuration Steps

#### Backend Configuration
1. Navigate to the backend directory:
   ```bash
   cd "Mobile Application/backend"
   ```

2. Copy the example configuration file:
   ```bash
   cp Config.example.toml Config.toml
   ```

3. Edit `Config.toml` and replace placeholder values with your actual API keys:
   ```toml
   [weatherAPI]
   openWeatherMapKey = "your_actual_openweathermap_api_key"
   stormGlassKey = "your_actual_stormglass_api_key"
   
   [server]
   port = 9090
   ```

#### Frontend Configuration
1. Copy environment files:
   ```bash
   cd "Mobile Application/frontend"
   cp .env.example .env
   
   cd "../admin"
   cp .env.example .env
   ```

2. Update URLs if needed (default values work for local development)

## 🚀 Installation & Running

### 1. Backend Services

Start the main weather service:
```bash
cd "Mobile Application/backend"
bal run main.bal
```

Start the news service (in a separate terminal):
```bash
cd "Mobile Application/backend"
bal run news_service.bal
```

### 2. Frontend Application

```bash
cd "Mobile Application/frontend"
npm install
npm start
```

The frontend will be available at: http://localhost:3000

### 3. Admin Panel

```bash
cd "Mobile Application/admin"
npm install
npm start
```

The admin panel will be available at: http://localhost:3001 (or the next available port)

## ✨ Features

### Weather Application
- 🌤️ **Real-time Weather Data**: Current weather conditions for multiple cities
- 🌊 **Marine Weather**: Specialized marine forecasts and conditions
- 🌅 **Astronomical Data**: Sunrise, sunset, moonrise, and moonset times
- 📍 **Multi-city Support**: Track weather for your favorite locations
- 📱 **Responsive Design**: Works seamlessly on desktop and mobile devices

### News Management System
- ✍️ **Content Creation**: Add news articles with title and content
- 📋 **News Dashboard**: View all news items with timestamps
- 🗑️ **Content Management**: Delete outdated news items
- ⚡ **Real-time Updates**: Instant synchronization across the platform

### Admin Panel
- 🎛️ **Intuitive Interface**: Easy-to-use content management
- 🔄 **Live Preview**: See changes in real-time
- 📊 **News Overview**: Comprehensive list of all published content

## 📁 Project Structure

```
iwb25-124-syntaxblitz/
├── Mobile Application/
│   ├── backend/          # Ballerina backend services
│   │   ├── main.bal      # Weather API service
│   │   ├── news_service.bal  # News management service
│   │   └── Config.toml   # Configuration file
│   ├── frontend/         # React weather application
│   │   ├── src/
│   │   └── public/
│   └── admin/            # React admin panel
│       ├── src/
│       └── public/
└── README.md
```

## 🔒 Security Notes

- **Never commit API keys** to the repository
- All configuration files with sensitive data are in `.gitignore`
- Use environment variables for production deployments
- Keep your API keys secure and rotate them regularly

## 🌐 API Endpoints

### Weather Service (Port 9090)
- Weather data endpoints (managed by Ballerina backend)

### News Service
- `GET /news/list` - Retrieve all news items
- `POST /news/add` - Add a new news article
- `DELETE /news/{id}` - Delete a news article by ID

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📝 License

This project is part of the IWB25-124 program by SyntaxBlitz team.

## 🐛 Troubleshooting

### Common Issues

**Port Already in Use**
- Check if another application is using ports 3000, 3001, or 9090
- Stop conflicting services or change the port in configuration files

**API Keys Not Working**
- Verify your API keys are correctly copied to `Config.toml`
- Ensure there are no extra spaces or quotes
- Check if your API keys are active and have sufficient quota

**Backend Not Starting**
- Verify Ballerina is properly installed: `bal version`
- Check if all dependencies are resolved
- Review the console for specific error messages

## 📧 Support

For issues and questions, please open an issue in the GitHub repository.

---

**Built with ❤️ by Team SyntaxBlitz**
