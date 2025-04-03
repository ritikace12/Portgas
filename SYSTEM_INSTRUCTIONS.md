# Portgas UI - System Instructions

## Project Overview
Portgas UI is a modern web application built with React, Node.js, and Express, featuring a beautiful UI design system, AI-powered chatbot, and responsive components. This document serves as a comprehensive guide to the project's architecture, components, and functionality.

## Table of Contents
1. [Project Structure](#project-structure)
2. [Theme System](#theme-system)
3. [Components](#components)
4. [Pages](#pages)
5. [API Integration](#api-integration)
6. [Chatbot Functionality](#chatbot-functionality)
7. [Common Issues & Solutions](#common-issues--solutions)

## Project Structure

```
Portgas_UI/
├── frontend/                 # React frontend application
│   ├── src/
│   │   ├── components/      # Reusable UI components
│   │   │   ├── Navbar.jsx   # Navigation component
│   │   │   ├── Footer.jsx   # Footer component
│   │   │   ├── Chatbot.jsx  # AI Chatbot component
│   │   │   └── ...         # Other components
│   │   ├── context/        # React context providers
│   │   │   └── ThemeContext.jsx
│   │   ├── pages/          # Page components
│   │   ├── services/       # API services
│   │   └── App.jsx         # Main application component
│   └── package.json
│
└── backend/                 # Node.js backend server
    ├── routes/             # API route handlers
    ├── config/            # Configuration files
    └── server.js          # Main server file
```

## Theme System

### Theme Context
The theme system is managed through React Context and provides:
- Light/Dark mode support
- Persistent theme preference (localStorage)
- Consistent color scheme across components

### Color Schemes
```javascript
// Light Theme
{
  primary: '#14b8a6',    // teal-500
  secondary: '#f8fafc',  // slate-50
  background: '#ffffff', // white
  text: '#000000',      // black
  border: '#e2e8f0',    // slate-200
  hover: '#e2e8f0',     // slate-200
  accent: '#14b8a6'     // teal-500
}

// Dark Theme
{
  primary: '#84cc16',    // lime-500
  secondary: '#1a1a1a',  // slightly lighter black
  background: '#000000', // black
  text: '#ffffff',      // white
  border: '#333333',    // darker gray
  hover: '#333333',     // darker gray
  accent: '#84cc16'     // lime-500
}
```

## Components

### 1. Navbar
- Responsive navigation bar
- Theme toggle functionality
- Mobile menu support
- Active link highlighting

### 2. Chatbot
- AI-powered chat interface
- Real-time message handling
- Smooth animations
- Mobile-responsive design
- Features:
  - Message history
  - Auto-scrolling
  - Loading states
  - Error handling

### 3. Footer
- Social media links
- Quick navigation
- Contact information
- Responsive layout

## Pages

### 1. Home Page
- Hero section with call-to-action
- Features showcase
- Service highlights
- Animated sections

### 2. About Page
- Company information
- Mission and vision
- Team values
- Interactive cards

### 3. Action Page
- Project requirements form
- Dynamic form validation
- Success/error handling
- Loading states

### 4. Contact Page
- Contact form
- Social media integration
- Location information
- Form validation

## API Integration

### Frontend-Backend Communication
1. **Chat API**
   ```javascript
   POST /api/chat
   Request: { message: string }
   Response: { message: string, timestamp: string }
   ```

2. **Project Requirements API**
   ```javascript
   POST /api/project-requirements
   Request: {
     name: string,
     email: string,
     projectType: string,
     description: string,
     budget: string,
     timeline: string
   }
   Response: { message: string }
   ```

3. **Contact Form API**
   ```javascript
   POST /api/contact
   Request: {
     name: string,
     email: string,
     subject: string,
     message: string
   }
   Response: { message: string }
   ```

## Chatbot Functionality

### Features
1. **Message Handling**
   - Real-time message processing
   - Message history persistence
   - Auto-scrolling to latest messages
   - Loading states during API calls

2. **UI/UX**
   - Responsive design
   - Smooth animations
   - Mobile-friendly interface
   - Theme-aware styling

3. **Error Handling**
   - Network error handling
   - API error responses
   - User-friendly error messages

### Integration with Gemini AI
- Uses Google's Gemini AI for responses
- Model: gemini-2.0-flash
- Error handling and fallback responses

## Common Issues & Solutions

### 1. Theme Not Persisting
**Issue**: Theme resets when navigating through buttons
**Solution**: 
- Ensure ThemeProvider wraps the entire app
- Check localStorage implementation
- Verify theme state management

### 2. CORS Errors
**Issue**: API requests blocked by CORS
**Solution**:
- Verify CORS configuration in backend
- Check allowed origins
- Ensure proper headers

### 3. Chatbot Not Responding
**Issue**: Blank responses from chatbot
**Solution**:
- Check API endpoint configuration
- Verify Gemini API key
- Ensure proper error handling

### 4. Form Submission Issues
**Issue**: Forms not submitting correctly
**Solution**:
- Check API endpoint URLs
- Verify form data structure
- Ensure proper error handling

### 5. Mobile Responsiveness
**Issue**: Layout issues on mobile devices
**Solution**:
- Check media queries
- Verify component styles
- Test on different screen sizes

## Best Practices

1. **Theme Usage**
   - Always use theme colors from context
   - Maintain consistency across components
   - Test both light and dark modes

2. **Component Development**
   - Follow responsive design principles
   - Implement proper error handling
   - Use consistent styling patterns

3. **API Integration**
   - Handle loading states
   - Implement proper error handling
   - Validate responses

4. **Performance**
   - Optimize image loading
   - Implement code splitting
   - Use proper caching strategies

## Troubleshooting Guide

### 1. Theme Issues
- Check ThemeContext implementation
- Verify localStorage functionality
- Test theme toggle in different scenarios

### 2. API Integration
- Verify endpoint URLs
- Check CORS configuration
- Test with different data payloads

### 3. UI Components
- Test responsive behavior
- Verify theme integration
- Check accessibility

### 4. Chatbot
- Test message handling
- Verify API integration
- Check error scenarios

## Support Resources

1. **Documentation**
   - Component documentation
   - API documentation
   - Theme system guide

2. **Development Tools**
   - React DevTools
   - Browser DevTools
   - Network monitoring

3. **Testing**
   - Component testing
   - API testing
   - Theme testing

## Getting Help

If you encounter issues:
1. Check the Common Issues section
2. Review the Troubleshooting Guide
3. Consult the documentation
4. Contact support

Remember to provide:
- Error messages
- Steps to reproduce
- Environment details
- Expected vs actual behavior 