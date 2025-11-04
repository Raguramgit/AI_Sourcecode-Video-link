# Sabari Musicals - AI-Powered Musical Instrument Recommendation System

## Overview

This project demonstrates an intelligent workflow that integrates n8n automation with the Model Context Protocol (MCP) and Claude AI to provide personalized musical instrument recommendations through a web interface.

## Video URL: **https://drive.google.com/file/d/1rk3N5iw89uZr8BbteFhI0hQBYGa3b7vx/view?usp=sharing**
## 🎯 Project Description

Sabari Musicals is an AI-powered platform that helps users discover the perfect musical instruments based on their preferences, experience level, and budget. The system uses a sophisticated workflow combining web forms, AI processing, and automated notifications.

## 🏗️ Architecture

### Workflow Components

The system consists of the following integrated components:

1. **Webhook Trigger** - Receives form submissions from the landing page
2. **Prepare Scraping Prompts** - Formats and structures data for AI processing
3. **Jina.ai Web Scraper** - Extracts relevant product information
4. **Process Scraped Data** - Cleans and organizes scraped content
5. **Code in JavaScript** - Custom data transformation logic
6. **MCP Client** - Connects to Claude AI via Model Context Protocol
7. **Jina.ai Web Scraping Agent** - Secondary scraping for comprehensive data
8. **Respond to Webhook** - Sends processed recommendations back to the user
9. **MCP Server Trigger** - Handles MCP protocol communications
10. **Gmail Integration** - Sends confirmation and recommendation emails

### Technology Stack

- **n8n** - Workflow automation platform
- **Claude AI** - AI model for generating personalized recommendations
- **MCP (Model Context Protocol)** - Communication protocol between n8n and Claude
- **Jina.ai** - Web scraping and data extraction
- **Lovable.dev** - Landing page hosting platform
- **Gmail API** - Email notifications
- **JavaScript** - Custom logic and data processing

## 📋 Features

### User-Facing Features

- **Personalized Form** - Collects user information including:
  - Full Name
  - Email Address
  - Mobile Number
  - Instrument Type preference
  - Budget Range
  - Personal message/requirements

- **AI-Powered Recommendations** - Intelligent suggestions based on:
  - User's musical goals
  - Experience level
  - Budget constraints
  - Instrument preferences

- **Email Notifications** - Automated email delivery of recommendations

### Technical Features

- **Real-time Processing** - Instant webhook-based form submissions
- **AI Integration** - Claude AI via MCP for contextual understanding
- **Web Scraping** - Automated product data collection
- **Data Transformation** - Custom JavaScript processing
- **Error Handling** - Robust workflow with fallback mechanisms

## 🚀 Setup Instructions

### Prerequisites

- n8n instance (self-hosted or cloud)
- Claude AI API access
- MCP server configuration
- Jina.ai API key
- Gmail API credentials
- Lovable.dev account

### Installation Steps

1. **Clone the Workflow**
   ```bash
   # Import the n8n workflow JSON into your n8n instance
   ```

2. **Configure Credentials**
   - Set up Claude AI API credentials
   - Configure MCP server connection
   - Add Jina.ai API key
   - Set up Gmail OAuth credentials
   - Configure webhook URL in Lovable.dev

3. **Deploy Landing Page**
   - Upload the landing page to Lovable.dev
   - Update webhook endpoint in the form
   - Configure CORS settings if needed

4. **Test the Workflow**
   - Submit a test form
   - Verify webhook reception
   - Check AI processing
   - Confirm email delivery

## 🔧 Configuration

### Webhook Setup

```javascript
// Example webhook payload structure
{
  "body": {
    "Name": "User Name",
    "Email": "user@example.com",
    "Mobile_No": "1234567890",
    "Product_type": "Flute",
    "Budget_Range": "Rs.1000 - Rs.5000",
    "Message": "Flute for beginner"
  }
}
```

### MCP Configuration

The workflow uses MCP to communicate with Claude AI for:
- Natural language processing of user requirements
- Contextual understanding of musical preferences
- Generation of personalized recommendations
- Budget-appropriate instrument suggestions

### Data Flow

1. User submits form → Webhook receives data
2. Data formatted → Sent to AI processing
3. Web scraping → Product data collection
4. AI analysis → Recommendation generation
5. Email dispatch → User receives recommendations
6. Webhook response → Confirmation to user

## 📊 Workflow Diagram

```
┌─────────────┐
│   Webhook   │
│  (On form   │
│ submission) │
└──────┬──────┘
       │
       ▼
┌─────────────────┐
│    Prepare      │
│    Scraping     │
│    Prompts      │
└────────┬────────┘
         │
         ▼
┌────────────────┐
│   Jina.ai Web  │
│    Scraper     │
└────────┬───────┘
         │
         ▼
┌────────────────┐
│    Process     │
│  Scraped Data  │
└────────┬───────┘
         │
         ▼
┌────────────────┐
│  Code in       │
│  JavaScript    │
└────────┬───────┘
         │
         ▼
┌────────────────┐
│  MCP Client    │◄────┐
└────────┬───────┘     │
         │             │
         ▼             │
┌────────────────┐     │
│  Jina.ai Web   │     │
│ Scraping Agent │     │
└────────┬───────┘     │
         │             │
         ▼             │
┌────────────────┐     │
│   Respond to   │     │
│    Webhook     │     │
└────────┬───────┘     │
         │             │
         ▼         ┌───┴────┐
┌────────────────┐ │  MCP   │
│  Send message  │ │ Server │
│   in Gmail     │ │Trigger │
└────────────────┘ └────────┘
```

## 🎨 Landing Page

### Features

- **Hero Section** - "Welcome to Sabari Musicals"
- **AI-Powered Badge** - Highlights intelligent assistance
- **Instrument Categories** - Comprehensive selection including:
  - Flutes
  - Guitars
  - Keyboards
  - Violins
  - And more

### Form Fields

- **Full Name** - User identification
- **Email Address** - For recommendations delivery
- **Mobile Number** - 10-digit contact number
- **Instrument Type** - Dropdown selection
- **Budget Range** - Budget preference selector
- **Your Message** - Additional requirements and preferences

### Call-to-Action

- **Primary Button** - "Get AI Recommendations" (Orange)
- **Secondary Button** - "Explore Instruments" (Blue)

## 🔐 Security Considerations

- Webhook URL should be secured with authentication
- API keys stored as environment variables
- Email credentials managed through OAuth2
- Form validation on client and server side
- Rate limiting on webhook endpoint
- HTTPS enforcement for all communications

## 🐛 Troubleshooting

### Common Issues

**Issue: Webhook not receiving data**
- Verify webhook URL is correctly configured
- Check CORS settings
- Ensure n8n instance is accessible

**Issue: AI recommendations not generating**
- Verify Claude API credentials
- Check MCP server status
- Review error logs in n8n

**Issue: Emails not being sent**
- Confirm Gmail API credentials
- Check OAuth token validity
- Verify recipient email addresses

**Issue: Web scraping failures**
- Validate Jina.ai API key
- Check target website availability
- Review scraping rate limits

## 📈 Future Enhancements

- [ ] Add user authentication system
- [ ] Implement recommendation history
- [ ] Create admin dashboard
- [ ] Add multi-language support
- [ ] Integrate payment gateway
- [ ] Build mobile application
- [ ] Add review and rating system
- [ ] Implement inventory management
- [ ] Create analytics dashboard
- [ ] Add chatbot for real-time support

## 🤝 Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create a feature branch
3. Commit your changes
4. Push to the branch
5. Create a Pull Request

## 📝 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 👥 Authors

- **Raguraman** - Initial work and development

## 📧 Contact

For questions or support, please contact:
- Email: raguraman7393@gmail.com
- Mobile: 8056443430

## 🙏 Acknowledgments

- Anthropic for Claude AI
- n8n community for workflow automation
- Jina.ai for web scraping capabilities
- Lovable.dev for landing page hosting
- Model Context Protocol (MCP) for AI integration

---

## Additional Resources

- [n8n Documentation](https://docs.n8n.io/)
- [Claude AI Documentation](https://docs.anthropic.com/)
- [Model Context Protocol](https://modelcontextprotocol.io/)
- [Jina.ai Documentation](https://jina.ai/docs/)

---

**Note**: This is a demonstration project showcasing the integration of various AI and automation technologies. Ensure proper security measures and compliance with data protection regulations when deploying in production.
