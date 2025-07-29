# Smart APE - Instructions for Setup and Usage

## Table of Contents
- [Quick Start](#quick-start)
- [Detailed Setup](#detailed-setup)
- [User Guide](#user-guide)
- [Technical Details](#technical-details)
- [Troubleshooting](#troubleshooting)
- [Advanced Features](#advanced-features)

## Quick Start

### Prerequisites
- Modern web browser (Chrome 60+, Firefox 55+, Safari 12+, Edge 79+)
- Local web server (Live Server, XAMPP, WAMP, or similar)

### 5-Minute Setup
1. Download or clone the project files
2. Open the project folder in your preferred code editor
3. Start a local web server (recommended: Live Server extension in VS Code)
4. Navigate to `pages/redirect.html` in your browser
5. Create a new account or use demo credentials

### Demo Credentials
- **Email**: user@company.com
- **Password**: user123

## Detailed Setup

### Method 1: Visual Studio Code with Live Server
1. Install VS Code
2. Install the "Live Server" extension
3. Open the project folder in VS Code
4. Right-click on `pages/redirect.html`
5. Select "Open with Live Server"

### Method 2: Python Simple Server
```bash
# Navigate to project directory
cd path/to/smart-ape-project

# Python 3
python -m http.server 8000

# Python 2
python -m SimpleHTTPServer 8000

# Open browser to http://localhost:8000/pages/redirect.html
```

### Method 3: Node.js http-server
```bash
# Install globally
npm install -g http-server

# Navigate to project directory
cd path/to/smart-ape-project

# Start server
http-server -p 8000

# Open browser to http://localhost:8000/pages/redirect.html
```

### Method 4: XAMPP/WAMP
1. Install XAMPP or WAMP
2. Copy project folder to `htdocs` (XAMPP) or `www` (WAMP)
3. Start Apache server
4. Navigate to `http://localhost/smart-ape/pages/redirect.html`

## User Guide

### Getting Started

#### 1. Account Creation
- Click "Register" on the landing page
- Fill in your full name, email, and password
- Password must be at least 6 characters
- Each user's data is completely isolated

#### 2. First Login
- Use your registered credentials
- You'll be redirected to the main dashboard
- Default categories will be created automatically

### Dashboard Overview

#### Navigation Bar
- **Smart APE Logo**: Returns to balance view
- **Balance**: Main dashboard with operations and filters
- **Categorías**: Manage your expense/income categories
- **Reportes**: View financial analytics and reports
- **Logout**: Safely exit the application

#### Balance Section
- **Ganancias**: Total income amount (green)
- **Gastos**: Total expenses amount (red)
- **Total**: Net balance (green if positive, red if negative)

### Managing Operations

#### Adding New Operations
1. Click "+ Nueva operación" button
2. Fill in the form:
   - **Descripción**: Brief description of the transaction
   - **Monto**: Amount (positive number)
   - **Tipo**: Choose "Ganancia" (Income) or "Gasto" (Expense)
   - **Categoría**: Select from your categories
   - **Fecha**: Transaction date (defaults to today)
3. Click "Agregar" to save

#### Editing Operations
1. Click the edit button (✏️) on any operation
2. Modify the desired fields
3. Save changes

#### Deleting Operations
1. Click the delete button (🗑️) on any operation
2. Confirm deletion in the popup

### Filtering Operations

#### Available Filters
- **Tipo**: Filter by income, expenses, or both
- **Categoría**: Filter by specific category
- **Desde**: Show operations from a specific date
- **Ordenar por**: Sort by date or amount

#### Using Filters
1. Adjust any filter in the left sidebar
2. Results update automatically
3. Click "Ocultar filtros" to hide/show filter panel

### Category Management

#### Adding Categories
1. Navigate to "Categorías" section
2. Enter category name in the input field
3. Click "Agregar" or press Enter
4. Category will appear with auto-assigned icon and color

#### Category Features
- **Visual Cards**: Each category displays as an attractive card
- **Statistics**: Shows number of operations and total amount
- **Icons**: Each category has a representative emoji
- **Grid Layout**: Categories arrange horizontally across the screen

#### Editing Categories
1. Click "✏️ Editar" on any category card
2. Modify the category name
3. Save changes

#### Deleting Categories
1. Click "🗑️ Eliminar" on any category card
2. Confirm deletion
3. Note: Categories with associated operations cannot be deleted

### Reports and Analytics

#### Summary Section
- **Top earning category**: Category with highest income
- **Top spending category**: Category with highest expenses
- **Best balance category**: Category with best net balance
- **Top earning month**: Month with highest income
- **Top spending month**: Month with highest expenses

#### Category Totals Table
- Complete breakdown by category
- Shows income, expenses, and balance for each
- Sorted by balance (highest to lowest)
- Color-coded values (green for positive, red for negative)

### Data Management

#### Data Storage
- All data is stored locally in your browser
- Each user's data is completely separate
- Data persists between sessions
- No data is sent to external servers

#### Data Security
- User isolation through email-based keys
- Input validation and sanitization
- Secure session management
- Protected route access

## Technical Details

### File Structure
```
smart-ape/
├── pages/          # HTML pages
│   ├── app.html    # Main application
│   ├── login.html  # User login
│   ├── register.html # User registration
│   └── redirect.html # Landing page
├── css/            # Stylesheets
│   ├── styles.css  # Main application styles
│   ├── auth.css    # Authentication styles
│   └── redirect.css # Landing page styles
├── js/             # JavaScript modules
│   ├── financial/  # Financial management
│   ├── auth/       # Authentication
│   ├── utils/      # Utility functions
│   └── config/     # Configuration
├── images/         # Assets
│   ├── favicon.png # Browser icon
│   └── logo.png    # Application logo
└── data/           # Sample data
    └── db.json     # Sample database structure
```

### Browser Compatibility
- **Chrome**: 60+ (full support)
- **Firefox**: 55+ (full support)
- **Safari**: 12+ (full support)
- **Edge**: 79+ (full support)
- **Internet Explorer**: Not supported

### Performance Considerations
- Lightweight vanilla JavaScript (no frameworks)
- Local storage for fast data access
- Minimal external dependencies
- Optimized CSS with efficient selectors
- Responsive design for all devices

## Troubleshooting

### Common Issues

#### "Access to fetch blocked by CORS policy"
**Solution**: You must use a local web server, not file:// protocol
- Use Live Server, http-server, or similar
- Never open HTML files directly in browser

#### "Data not saving"
**Solution**: Check browser settings
- Ensure localStorage is enabled
- Check if browser is in private/incognito mode
- Clear browser cache if needed

#### "Login not working"
**Solution**: Verify credentials
- Check email format is correct
- Ensure password matches registration
- Try creating a new account

#### "Categories not showing"
**Solution**: Check browser console
- Press F12 to open developer tools
- Look for JavaScript errors in console
- Refresh the page

#### "Responsive issues on mobile"
**Solution**: Check viewport settings
- Ensure proper viewport meta tag
- Test in different browsers
- Check CSS media queries

### Browser Console Debugging
1. Press F12 to open developer tools
2. Go to Console tab
3. Look for error messages in red
4. Check Network tab for failed requests

### Data Reset
If you need to reset all data:
1. Open browser developer tools (F12)
2. Go to Application/Storage tab
3. Find localStorage section
4. Delete all Smart APE related entries
5. Refresh the page

## Advanced Features

### Customization Options

#### Theme Colors
The application uses a banana yellow theme. To customize:
1. Edit `css/styles.css`
2. Search for color values like `#ffd93d`
3. Replace with your preferred colors
4. Maintain contrast ratios for accessibility

#### Default Categories
To modify default categories:
1. Edit `js/financial/categoriesManager.js`
2. Find `defaultCategories` array
3. Modify names, icons, and colors
4. Save and refresh application

#### Date Formats
To change date display format:
1. Edit `js/financial/operationsManager.js`
2. Find `formatDate` method
3. Modify the format string
4. Test with sample data

### Development Mode

#### Adding New Features
1. Follow existing code patterns
2. Use ES6+ JavaScript features
3. Maintain separation of concerns
4. Add proper error handling

#### Testing Changes
1. Always test with sample data
2. Test on multiple browsers
3. Verify responsive design
4. Check browser console for errors

### Integration Possibilities

#### Export Data
The application structure supports easy data export:
- Operations data: `operationsManager.getAllOperations()`
- Categories data: `categoriesManager.getAllCategories()`
- User data: Accessible through SessionUtils

#### API Integration
To connect with external APIs:
1. Modify `js/config/api.js`
2. Update storage methods in managers
3. Add error handling for network requests
4. Implement data synchronization

### Performance Optimization

#### Large Datasets
For users with many operations:
1. Implement pagination in operation lists
2. Add lazy loading for reports
3. Consider data archiving strategies
4. Optimize filter performance

#### Mobile Optimization
- Touch-friendly button sizes (44px minimum)
- Optimized images for different screen densities
- Efficient scroll handling
- Minimized repaints and reflows

## Support and Maintenance

### Regular Maintenance
- Clear browser cache periodically
- Keep browser updated
- Monitor localStorage usage
- Backup important data manually

### Feature Requests
This is a self-contained educational project. For additional features:
1. Fork the codebase
2. Implement desired functionality
3. Test thoroughly
4. Document changes

### Security Best Practices
- Use HTTPS in production
- Regular browser updates
- Be cautious with browser extensions
- Don't share login credentials
- Use strong, unique passwords

---

**Smart APE - Your intelligent financial companion**

For technical support or questions about the codebase, refer to the README.md file or examine the well-documented source code.
