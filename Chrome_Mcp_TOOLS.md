# Chrome MCP Server API Reference 📚

## Table of Contents

- [Chrome MCP Server API Reference 📚](#chrome-mcp-server-api-reference-)
  - [Table of Contents](#table-of-contents)
  - [Overview](#overview)
  - [API Endpoints](#api-endpoints)
    - [Navigation](#navigation)
    - [Content Extraction](#content-extraction)
    - [Element Interaction](#element-interaction)
    - [Network Operations](#network-operations)
  - [Usage Examples](#usage-examples)

## Overview

The Chrome MCP Server provides a comprehensive set of tools for browser automation and web scraping. It allows you to control Chrome browser instances, navigate web pages, extract content, and interact with web elements programmatically.

## API Endpoints

### Navigation

- `chrome_navigate`: Navigate to a URL or refresh the current tab
- `chrome_go_back_or_forward`: Navigate back or forward in browser history
- `get_windows_and_tabs`: Get all currently open browser windows and tabs
- `chrome_close_tabs`: Close one or more browser tabs

### Content Extraction

- `chrome_get_web_content`: Fetch content from a web page
- `chrome_get_interactive_elements`: Get interactive elements from the current page
- `chrome_screenshot`: Take a screenshot of the current page or a specific element

### Element Interaction

- `chrome_click_element`: Click on an element in the current page or at specific coordinates
- `chrome_fill_or_select`: Fill a form element or select an option with the specified value

### Network Operations

- `chrome_network_request`: Send a network request from the browser with cookies and other browser context
- `chrome_network_debugger_start`: Start capturing network requests from a web page using Chrome Debugger API
- `chrome_network_debugger_stop`: Stop capturing network requests using Chrome Debugger API and return the captured data
- `chrome_network_capture_start`: Start capturing network requests from a web page using Chrome webRequest API
- `chrome_network_capture_stop`: Stop capturing network requests using webRequest API and return the captured data

## Usage Examples

1. Navigate to a website and extract content:
   ```javascript
   await chrome_navigate({ url: 'https://example.com' });
   const content = await chrome_get_web_content({ textContent: true });
   console.log(content);
   ```

2. Fill a form and submit it:
   ```javascript
   await chrome_fill_or_select({ selector: '#username', value: 'user123' });
   await chrome_fill_or_select({ selector: '#password', value: 'pass456' });
   await chrome_click_element({ selector: '#login-button' });
   ```

3. Take a screenshot of a specific element:
   ```javascript
   const screenshot = await chrome_screenshot({ 
     selector: '#important-section', 
     storeBase64: true 
   });
   ```
