# Expense Tracker MCP Server

A local MCP (Model Context Protocol) server built with Python and FastMCP for daily expense tracking and management.

This project helps users manage day-to-day expenses directly through MCP-compatible clients like Claude Desktop. It supports adding expenses, categorizing them with subcategories, listing expenses within a specific date range, and generating summarized expense reports.

---

# Features

* Add daily expenses
* Category and sub-category based expense tracking
* Expense summaries by category
* List expenses within a date range
* SQLite-based lightweight local storage
* MCP compatible
* Works with Claude Desktop
* Fast and lightweight local setup

---

# Tech Stack

* Python
* FastMCP
* SQLite
* UV Package Manager
* Claude Desktop (MCP Client)

---

# Project Structure

```bash
expense-tracker-mcp-server/
│
├── main.py
├── expenses.db
├── categories.json
├── README.md
```

---

# Installation

## Clone the Repository

```bash
git clone <your-github-repo-url>
cd expense-tracker-mcp-server
```

---

# Install Dependencies

Using UV:

```bash
uv sync
```

Or install FastMCP manually:

```bash
uv tool install fastmcp
```

---

# Run the MCP Server

```bash
uv run fastmcp run main.py
```

---

# Claude Desktop Configuration

Add this configuration to your Claude Desktop MCP config file:

```json
{
  "mcpServers": {
    "ExpenseTracker": {
      "command": "C:\\Users\\YOUR_USERNAME\\.local\\bin\\uv.exe",
      "args": [
        "run",
        "--link-mode=copy",
        "--with",
        "fastmcp",
        "fastmcp",
        "run",
        "C:\\path\\to\\expense-tracker-mcp-server\\main.py"
      ],
      "env": {
        "UV_LINK_MODE": "copy"
      },
      "transport": "stdio"
    }
  }
}
```

---

# Available MCP Tools

## add_expense

Add a new expense entry.

### Parameters

* `date`
* `amount`
* `category`
* `subcategory`
* `note`

---

## list_expenses

List expenses within a given date range.

### Parameters

* `start_date`
* `end_date`

---

## summarize

Generate expense summaries grouped by category.

### Parameters

* `start_date`
* `end_date`
* `category` (optional)

---

# Example Use Cases

* Daily expense tracking
* Monthly expense summaries
* Food and travel expense monitoring
* Budget analysis
* Personal finance management
* AI-assisted financial tracking through Claude Desktop

---

# Example Prompts

```text
Add today's grocery shopping expense of 450 Rs under Grocery category.
```

```text
Show all expenses from 2026-05-01 to 2026-05-10.
```

```text
Summarize all expenses for May 2026.
```

---

# Database

This project uses SQLite for local data storage.

Database file:

```bash
expenses.db
```

---

# Future Improvements

* Budget limits
* Expense analytics
* Charts and visualizations
* Multi-user support
* Export to CSV/Excel
* Recurring expenses
* AI-powered spending insights

---

# Author

Subhankar Mukherjee
