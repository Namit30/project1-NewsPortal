# ONGC News Portal

Welcome to the ONGC News Portal! This Vue.js application provides users with up-to-date news and events from ONGC (Oil and Natural Gas Corporation Limited). It features a clean and modern interface with user-friendly navigation and interactive elements.

## 📋 Project Overview

The ONGC News Portal consists of three main components:

### `App.vue`
- **Description**: The main layout of the application, including navigation and routing.
- **Features**: Navigation bar with links to different pages, linear gradient background, and smooth hover effects.

### `EventList.vue`
- **Description**: Displays a dashboard of news events with a grid layout and footer.
- **Features**: Dynamic display of news events using `EventCard` components, gradient background, and footer with contact information.

### `AboutView.vue`
- **Description**: Provides information about the portal and allows users to submit feedback.
- **Features**: Informative content about the ONGC News Portal, interactive image with hover effects, and a feedback form with modal confirmation.

## 🚀 Features

- **User Navigation**: 
  - Seamless navigation between the News Dashboard and About page.
  - Responsive design with smooth hover effects on navigation links.

- **News Dashboard**: 
  - Dynamic display of news events using `EventCard` components.
  - Gradient background and a footer with contact information.

- **About Page**: 
  - Informative content about the ONGC News Portal.
  - Interactive image with hover effects.
  - Feedback form with modal confirmation.

## 📦 Installation

To get started with the ONGC News Portal, follow these steps:

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/yourusername/ongc-news-portal.git
   cd ongc-news-portal
2. **Install Vue CLI:**

Install Vue CLI Globally:
You need Vue CLI to create and manage Vue.js projects. Install it globally using one of the following commands. You need administrator privileges to execute these unless npm was installed through a Node.js version manager (e.g., n or nvm):

```bash
Copy code
npm install -g @vue/cli
# OR
yarn global add @vue/cli
Verify Installation:
After installation, verify that Vue CLI is properly installed by running:
Copy code
vue --version
```
Open your browser and navigate to http://localhost:8080 to see the application in action.

# **📚 Usage**
Navigate Between Pages:
Use the navigation bar to switch between the News Dashboard and About page.

View News Events:
The News Dashboard displays events fetched from the API. The EventCard component is used to show individual events.

Submit Feedback:
On the About page, use the feedback form to submit suggestions. A modal will confirm the successful submission.

# ✨ Customization
Feel free to customize the application to fit your needs:

Change Styles: Update the CSS in each component to match your desired design.
Add Features: Extend functionality by modifying or adding new components.
API Integration: Update EventService.js to connect to your own API if needed.
# 📖 Documentation
For more details on Vue.js and its features, check out the official Vue.js documentation.

# 🛠️ Contributing
Contributions are welcome! If you have suggestions or find issues, please open an issue or submit a pull request.

# 📧 Contact
For any questions or feedback, feel free to reach out:

Email: namit752@gmail.com
