
## Detailed Setup

### Method 1: Visual Studio Code with Live Server
1. Install VS Code.
2. Install the "Live Server" extension.
3. Open the project folder in VS Code.
4. Right-click on `pages/redirect.html`.
5. Select "Open with Live Server".

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
1. Install XAMPP or WAMP.
2. Copy your project folder to `htdocs` (XAMPP) or `www` (WAMP).
3. Start the Apache server.
4. Go to `http://localhost/smart-ape/pages/redirect.html` in your browser.

### Method 5: json-server (Port 3001)  
**Recommended for working with sample data!**
1. Install json-server:
    ```bash
    npm install -g json-server
    ```
2. Run the server on port 3001:
    ```bash
    cd path/to/smart-ape-project/data
    json-server --watch db.json --port 3001
    ```
3. Make sure your application is configured to use `http://localhost:3001` for API requests (adjust `js/config/api.js` if necessary).

## Important Note
If you have another service running on port 3000 (such as React or Node), using port 3001 for json-server will help you avoid conflicts.  
**Always check that your API configuration (typically in `js/config/api.js`) points to the correct port.**
