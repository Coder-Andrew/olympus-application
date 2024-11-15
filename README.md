# Olympus Application

A simple CRUD (Create, Read, Update, Delete) web application built with Vue 3 using the Composition API and Single File Components (SFC) syntax. This project demonstrates basic CRUD functionality, routing, and in-memory data management.

## Project Overview

This CRUD app allows users to:
- **Create** new items using a form.
- **Read** and view a list of items.
- **Update** item details by editing existing items.
- **Delete** items to remove them from the list.

### Features
- **In-Memory Data Management**: Uses a local array to store items without backend integration.
- **Basic Routing**: Implements basic Vue routing to navigate between pages.
- **Minimal Styling**: Focuses on functionality with simple, centered styles.

## Project Structure

- **`App.vue`**: Main app component with routing setup.
- **`components`**: 
  - `ItemForm.vue`: A form component for adding or updating items.
  - `ListItems.vue`: Displays a list of items with edit and delete functionality.
  - `NotFound.vue`: A simple component to handle 404 errors.

## Getting Started

### Prerequisites
- **Node.js** (version 12.x or later)
- **npm** (Node Package Manager)

### Installation

1. Clone the repository:
    ```bash
    git clone https://github.com/Coder-Andrew/olympus-application.git
    ```
2. Navigate into the project directory:
    ```bash
    cd olympus-application
    ```
3. Install the required dependencies:
    ```bash
    npm install
    ```

### Running the Application

To start the application in development mode with hot reloading, run:
```bash
npm run serve
