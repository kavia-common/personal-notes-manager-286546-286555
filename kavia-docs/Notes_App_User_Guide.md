# Notes App - User Guide

This document provides comprehensive instructions for setting up, configuring, and using the Notes App frontend. The Notes App is a personal tool designed to help users create, view, edit, and delete their personal notes within a simple and modern interface.

## Overview

The Notes App frontend is built with React and focuses on simplicity and ease of use. It features a clean, modern interface with built-in theme management (Dark/Light modes) and a responsive layout that adapts to various screen sizes.

## Key Features

*   **Modern Architecture**: Built on React 18 for high performance and maintainability.
*   **Theme Management**: Integrated Dark and Light mode switching to suit user preference or lighting conditions.
*   **Responsive Design**: optimized layout that adjusts seamlessly for mobile and desktop viewing.
*   **Environment Configuration**: Extensive configuration options via environment variables for flexible deployment.

## System Requirements

To run this application locally, ensure your system meets the following requirements:

*   **Node.js**: Version 14.x or higher
*   **npm**: Version 6.x or higher (usually bundled with Node.js)
*   **Web Browser**: A modern web browser (Chrome, Firefox, Safari, or Edge)

## Quick Start

Follow these steps to set up the application in a local development environment.

1.  **Install Dependencies**
    Navigate to the project directory and install the necessary packages:
    ```bash
    cd notes_frontend
    npm install
    ```

2.  **Start the Application**
    Run the app in development mode:
    ```bash
    npm start
    ```
    The application will automatically open in your default browser at `http://localhost:3000`.

## Configuration (.env)

The application uses environment variables for configuration. You can define these in a `.env` file in the root of the `notes_frontend` directory.

| Variable | Description | Example |
| :--- | :--- | :--- |
| `REACT_APP_API_BASE` | Base path for API calls. | `/api/v1` |
| `REACT_APP_BACKEND_URL` | Full URL to the backend service. | `http://localhost:8000` |
| `REACT_APP_FRONTEND_URL` | URL where this frontend is hosted. | `http://localhost:3000` |
| `REACT_APP_WS_URL` | WebSocket URL for real-time updates. | `ws://localhost:8000` |
| `REACT_APP_NODE_ENV` | Environment mode (development/production). | `development` |
| `REACT_APP_PORT` | Port to run the server on. | `3000` |
| `REACT_APP_LOG_LEVEL` | Logging verbosity level. | `debug` |
| `REACT_APP_HEALTHCHECK_PATH` | Path for application health checks. | `/health` |
| `REACT_APP_FEATURE_FLAGS` | Comma-separated list of enabled feature flags. | `new-editor,beta-ui` |
| `REACT_APP_EXPERIMENTS_ENABLED`| Set to `true` to enable experimental features. | `true` |

*Note: Many of these variables are optional and can be left empty if not required for your specific environment.*

## Running the App (Preview)

In the managed preview environment, the application is configured to run automatically.

*   **Access**: The application runs on **port 3000**.
*   **Management**: The preview lifecycle (start/stop) is managed by the user externally. You do not need to run manual start commands inside the terminal.
*   **Usage**: Once the preview is active, you can interact with the application directly through the provided web interface.

## Using the App

### Accessing the Interface
Open your web browser and navigate to the application URL (e.g., `http://localhost:3000` or your preview URL).

### Switching Themes
The application supports both Light and Dark themes.
1.  Locate the theme toggle button in the header (top-right corner on desktop).
2.  Click the button to switch between **☀️ Light** and **🌙 Dark** modes.
3.  Your selection is applied instantly, changing background and text colors for optimal readability.

## Troubleshooting

### Common Issues

*   **Port 3000 is already in use**
    *   If you see an error indicating port 3000 is busy, you may have another instance of the app or another service running. Stop the other process or configure `REACT_APP_PORT` to use a different port.

*   **Blank Screen on Startup**
    *   Check your environment variables. An incorrect `REACT_APP_API_BASE` or missing configuration might cause the app to fail silently. Check the browser console (F12 > Console) for error messages.

*   **Changes not reflecting**
    *   If you edited `.env` files, you must restart the development server (`npm start`) for changes to take effect.

## FAQ

**Q: Can I change the default port?**
A: Yes, you can specify a different port by setting the `PORT` (or `REACT_APP_PORT` if supported by custom logic) environment variable before starting the app.

**Q: Where are the notes stored?**
A: This is a frontend application. Notes are typically stored in the backend database connected via `REACT_APP_BACKEND_URL`. Ensure your backend service is running.
