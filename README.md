# Note-App-React

A repository containing two JavaScript applications:

1. **Expense Tracker GUI** — a React-based web application for adding, filtering, and visualizing expenses.
2. **Command-Line Notes App** — a Node.js CLI application for creating, listing, and removing notes using a local JSON file.

The project demonstrates fundamental concepts in **React, component-based UI development, state management, Node.js, command-line interfaces, file-system persistence, and npm package management**.

---

## Repository Structure

```text
Note-App-React/
│
├── GUI/
│   ├── public/
│   ├── src/
│   │   ├── components/
│   │   │   ├── Chart/
│   │   │   ├── Expenses/
│   │   │   ├── NewExpense/
│   │   │   └── UI/
│   │   ├── App.js
│   │   ├── App.css
│   │   ├── index.js
│   │   └── index.css
│   ├── package.json
│   └── package-lock.json
│
└── commandline/
    ├── noteHandler.js
    ├── notes.js
    ├── notes.json
    ├── package.json
    └── package-lock.json
```

---

# 1. Expense Tracker GUI

The `GUI` directory contains a React application for managing and visualizing expenses.

### Features

* Add new expenses
* Enter expense title, amount, and date
* Display expenses as individual items
* Filter expenses by year
* Visualize expenses using a chart
* Component-based React architecture
* React state management using `useState`
* Responsive UI styling using CSS

### Application Flow

```text
User
 │
 ├── Add Expense
 │       │
 │       ▼
 │   NewExpense
 │       │
 │       ▼
 │   App State
 │       │
 │       ▼
 │   Expenses
 │       │
 ├───────┼───────────────┐
 │       │               │
 ▼       ▼               ▼
List   Filter          Chart
```

### Main Components

#### `NewExpense`

Responsible for collecting information about a new expense and passing it back to the application.

```text
Title
Amount
Date
   │
   ▼
NewExpense
   │
   ▼
addNewExpense()
```

#### `Expenses`

Displays the collection of expenses and coordinates filtering and visualization.

#### `ExpenseItem`

Represents an individual expense.

#### `ExpenseFilter`

Provides year-based filtering for the displayed expenses.

#### `ExpensesChart`

Provides a visual representation of expenses across the selected period.

#### `Chart` and `ChartBar`

Reusable chart components used to visualize expense data.

#### `Card`

A reusable UI wrapper component used to provide consistent styling.

---

## React Technologies

The GUI uses:

* React `17`
* React DOM
* Create React App
* JavaScript
* CSS
* React Hooks

### Dependencies

```text
react
react-dom
react-scripts
@testing-library/react
@testing-library/jest-dom
@testing-library/user-event
web-vitals
```

---

# 2. Command-Line Notes Application

The `commandline` directory contains a Node.js command-line notes application.

Notes are stored locally in:

```text
commandline/notes.json
```

The application supports creating, listing, and deleting notes.

## Features

* Add a note
* List all notes
* Remove a note
* Prevent duplicate note titles
* Persist notes using a JSON file
* Command-line argument parsing
* Colored terminal output

---

## CLI Commands

Navigate to the command-line application:

```bash
cd commandline
```

Install dependencies:

```bash
npm install
```

### Add a Note

```bash
node notes.js add --title="Shopping" --body="Buy groceries"
```

The application creates a note containing:

```text
Title: Shopping
Contents: Buy groceries
```

### List Notes

```bash
node notes.js list
```

This displays all notes stored in `notes.json`.

### Remove a Note

```bash
node notes.js remove --title="Shopping"
```

The note with the specified title is removed from the local storage file.

---

## Command-Line Architecture

```text
notes.js
   │
   │ CLI commands
   ▼
noteHandler.js
   │
   ├── addNote()
   ├── getNote()
   ├── listNote()
   └── removeNote()
          │
          ▼
      notes.json
```

### `notes.js`

Handles the command-line interface using **Yargs**.

Supported commands:

| Command  | Description       |
| -------- | ----------------- |
| `add`    | Add a new note    |
| `list`   | Display all notes |
| `remove` | Remove a note     |

### `noteHandler.js`

Contains the core note-management logic:

* Reading notes
* Writing notes
* Creating notes
* Removing notes
* Listing notes
* Detecting duplicate titles

### `notes.json`

Acts as the local persistence layer for the CLI application.

---

# Technologies Used

| Area               | Technology         |
| ------------------ | ------------------ |
| GUI                | React              |
| Frontend           | JavaScript, CSS    |
| UI Architecture    | React Components   |
| State Management   | React `useState`   |
| CLI                | Node.js            |
| CLI Arguments      | Yargs              |
| Terminal Styling   | Chalk              |
| Validation         | Validator          |
| Persistence        | JSON / File System |
| Package Management | npm                |

---

# Getting Started

## Prerequisites

Install the following:

* Node.js
* npm

Verify your installation:

```bash
node --version
npm --version
```

---

# Running the React Application

Navigate to the GUI directory:

```bash
cd GUI
```

Install dependencies:

```bash
npm install
```

Start the development server:

```bash
npm start
```

The application will be available at:

```text
http://localhost:3000
```

---

## Create a Production Build

Inside the `GUI` directory:

```bash
npm run build
```

The optimized production files will be generated in:

```text
GUI/build/
```

---

## Run Tests

```bash
npm test
```

---

# Running the Command-Line Application

Navigate to the CLI directory:

```bash
cd commandline
```

Install dependencies:

```bash
npm install
```

Then run commands using:

```bash
node notes.js <command>
```

For example:

```bash
node notes.js add --title="Project" --body="Complete the project documentation"
```

```bash
node notes.js list
```

```bash
node notes.js remove --title="Project"
```

---

# Learning Objectives

This project demonstrates several fundamental software development concepts.

### React

* Functional components
* Props
* State management
* Event handling
* Component composition
* Conditional rendering
* Reusable UI components

### Node.js

* CommonJS modules
* File-system operations
* Command-line applications
* JSON-based persistence
* Package management

### Software Design

The project separates functionality into smaller modules and components rather than placing all application logic in a single file.

---

# Future Improvements

Potential improvements include:

* Add persistent storage for the React expense tracker
* Add edit and delete functionality to expenses
* Add expense categories
* Add monthly and yearly summaries
* Add responsive/mobile UI improvements
* Add automated tests for the CLI application
* Add automated tests for React components
* Replace JSON storage with a database
* Add a backend API
* Connect the React frontend with persistent backend storage
* Add authentication and user-specific data

