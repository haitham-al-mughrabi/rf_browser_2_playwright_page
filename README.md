# 🤖 Robot Framework Browser Library → 🎭 Playwright Python Migration Guide

A comprehensive, interactive reference guide for migrating from Robot Framework Browser Library to Playwright Python. This tool provides side-by-side comparisons, complete argument documentation, and practical examples for over 160 keywords across 24 categories.

## 🎯 Purpose

This migration guide solves a critical challenge for QA automation engineers transitioning from Robot Framework's Browser Library to native Playwright Python implementations. It provides:

- **Complete keyword mapping** between Browser Library and Playwright Python
- **Comprehensive argument documentation** for all Playwright methods
- **Real-world code examples** with proper syntax
- **Category-based organization** for easy navigation
- **Interactive search and filtering** for quick reference

## 🚀 Features

### Core Features
- **160+ Keyword Mappings**: Complete coverage of Browser Library keywords to Playwright equivalents
- **24 Categories**: Organized by functionality (Browser Management, Element Interaction, Assertions, etc.)
- **Full Argument Documentation**: Every Playwright method includes all available arguments with defaults
- **Syntax Comparison**: Side-by-side Robot Framework vs Playwright Python syntax
- **Interactive Search**: Real-time keyword search across all categories
- **Category Filtering**: Filter by specific categories (Navigation, Assertions, Screenshots, etc.)
- **Expand/Collapse All**: Quick view controls for browsing
- **Dark Mode UI**: Eye-friendly interface for extended use
- **Zero Dependencies**: Runs entirely in the browser using Tailwind CSS CDN

### Categories Covered
1. **Browser Management** - Launch, close, switch browsers
2. **Context Management** - Isolated browser contexts
3. **Navigation** - Page navigation and URL handling
4. **Element Interaction** - Click, fill, type, select, check
5. **Element State & Properties** - Get text, attributes, values
6. **Assertions & Waiting** - Wait conditions and checks
7. **Playwright Assertions** - expect() API for robust testing
8. **Screenshots & Recording** - Visual testing and debugging
9. **JavaScript Execution** - Execute custom JS in page context
10. **Frames & Iframes** - Handle nested frames
11. **Dialogs & Popups** - Alert, confirm, prompt handling
12. **Cookies & Storage** - Manage browser storage
13. **Network & API** - Request interception and mocking
14. **Mouse Actions** - Advanced mouse operations
15. **Selectors** - CSS, XPath, text, role-based selectors
16. **Timeouts & Configuration** - Timeout management
17. **Tracing & Debugging** - Debug tools and traces
18. **PDF & Printing** - PDF generation
19. **Device & Geolocation** - Mobile emulation
20. **Advanced Element Interaction** - Drag and drop, hover
21. **Assertions & Retry** - Retry mechanisms
22. And more...

## 📋 Prerequisites

- **Modern web browser** (Chrome, Firefox, Safari, Edge)
- **Basic understanding** of Robot Framework and Playwright
- **Python environment** (for implementing Playwright code)
- **VS Code** (recommended for development)

## 🛠️ Installation & Usage

### Option 1: Local Usage
1. Download the HTML file
2. Open it directly in your web browser
3. No server or dependencies required!

```bash
# Simply open the file
open Browser-Library-to-Playwright-Migration-Guide.html

# Or double-click the file in your file explorer
```

### Option 2: Serve Locally (Optional)
```bash
# Using Python's built-in server
python -m http.server 8000

# Navigate to: http://localhost:8000
```

### Option 3: Host on GitHub Pages
1. Push the HTML file to a GitHub repository
2. Enable GitHub Pages in repository settings
3. Access via: `https://yourusername.github.io/repo-name/`

## 💡 How to Use

### Quick Search
1. Type keywords in the search box (e.g., "click", "screenshot", "wait")
2. Results filter in real-time
3. Matched text is highlighted in yellow

### Category Filtering
1. Click category buttons to filter by specific functionality
2. Click "All" to reset filters
3. Multiple categories can be viewed by toggling

### Expand/Collapse
- **Expand All**: View all keyword details at once (useful for Ctrl+F search)
- **Collapse All**: Compact view for browsing categories
- **Individual Toggle**: Click any keyword card to expand/collapse

### Reading Keyword Cards
Each keyword card contains:
- **Browser Library Syntax**: Original Robot Framework code
- **Playwright Method**: Python method equivalent
- **Playwright Syntax**: Complete Python implementation example
- **Description**: What the keyword does
- **Notes**: Important details, gotchas, and tips
- **Arguments**: (When expanded) Full argument documentation

## 📖 Example Usage Scenarios

### Scenario 1: Migrating a Click Action
**Robot Framework:**
```robot
Click    css=#submit-button
```

**Find in Guide:**
- Search: "click"
- Category: "Element Interaction"
- Result: 
```python
page.click("#submit-button", timeout=30000, force=False)
```

### Scenario 2: Taking Screenshots
**Robot Framework:**
```robot
Take Screenshot    fullpage=True
```

**Find in Guide:**
- Search: "screenshot"
- Category: "Screenshots & Recording"
- Result:
```python
page.screenshot(path='screenshot.png', full_page=True, type='png')
```

### Scenario 3: Waiting for Elements
**Robot Framework:**
```robot
Wait For Elements State    css=.loading    hidden
```

**Find in Guide:**
- Search: "wait"
- Category: "Assertions & Waiting"
- Result:
```python
page.wait_for_selector('.loading', state='hidden', timeout=30000)
```

## 🎓 Learning Path

### For Robot Framework Users
1. **Start with Browser Management**: Understand browser launch and context creation
2. **Learn Navigation**: Page navigation and URL handling
3. **Master Element Interaction**: Core actions (click, fill, type)
4. **Explore Assertions**: Migrate from RF assertions to Playwright expect()
5. **Advanced Features**: Network mocking, tracing, video recording

### Key Differences to Understand

| Concept | Robot Framework | Playwright Python |
|---------|-----------------|-------------------|
| **Async/Await** | Not required | Required for async API |
| **Context** | Implicit | Explicit management |
| **Selectors** | Various syntaxes | CSS, XPath, text, role |
| **Assertions** | Built-in keywords | expect() with auto-retry |
| **Timeout** | Global settings | Per-action configuration |

## 🔧 Technical Details

### File Structure
```
Browser-Library-to-Playwright-Migration-Guide.html
├── HTML Structure
├── Tailwind CSS (CDN)
├── JavaScript
│   ├── keywordsData[] - All keyword mappings
│   ├── Search functionality
│   ├── Filter logic
│   └── Expand/Collapse controls
└── Styling (Embedded)
```

### Browser Compatibility
- ✅ Chrome 90+
- ✅ Firefox 88+
- ✅ Safari 14+
- ✅ Edge 90+

### Performance
- **Load Time**: < 1 second
- **Search Response**: Real-time (< 50ms)
- **Memory Usage**: ~10MB
- **File Size**: ~97KB

## 📝 Playwright Argument Documentation

This guide includes complete argument documentation for all Playwright methods:

### Common Arguments Across Methods
- `timeout` - Maximum time in milliseconds (default: 30000)
- `force` - Bypass actionability checks (default: False)
- `no_wait_after` - Don't wait for navigation (default: False)
- `strict` - Require selector to resolve to single element (default: False)

### Browser Launch Arguments
```python
playwright.chromium.launch(
    headless=True,           # Run headless
    slow_mo=0,               # Slow down by ms
    args=[],                 # Browser arguments
    downloads_path=None,     # Download directory
    executable_path=None,    # Custom browser path
    proxy={},                # Proxy settings
    timeout=30000,           # Launch timeout
    channel=None,            # Browser channel
    devtools=False           # Auto-open DevTools
)
```

### Context Creation Arguments
```python
browser.new_context(
    viewport={'width': 1920, 'height': 1080},
    user_agent=None,
    locale='en-US',
    timezone_id=None,
    geolocation=None,
    permissions=[],
    color_scheme='light',    # 'light', 'dark', 'no-preference'
    accept_downloads=True,
    ignore_https_errors=False,
    storage_state=None,      # Restore auth state
    record_video_dir=None,
    record_har_path=None
)
```

### Action Arguments
```python
page.click(selector,
    timeout=30000,
    force=False,
    no_wait_after=False,
    position={'x': 0, 'y': 0},
    modifiers=[],            # ['Alt', 'Control', 'Meta', 'Shift']
    button='left',           # 'left', 'right', 'middle'
    click_count=1,
    delay=0                  # Between mousedown and mouseup
)
```

## 🤝 Contributing

This is a living document that evolves with Playwright updates. Contributions are welcome!

### How to Contribute
1. **Report Issues**: Missing keywords, incorrect syntax, outdated arguments
2. **Submit Updates**: New Playwright features, better examples
3. **Improve Documentation**: Clearer descriptions, additional notes
4. **Add Examples**: Real-world use cases and patterns

### Contribution Guidelines
- Ensure Playwright syntax is tested and working
- Include all available arguments with correct defaults
- Provide clear, practical examples
- Add helpful notes and gotchas
- Maintain consistent formatting

## 📚 Additional Resources

### Official Documentation
- [Playwright Python Docs](https://playwright.dev/python/)
- [Robot Framework Browser Library](https://robotframework-browser.org/)
- [Playwright API Reference](https://playwright.dev/python/docs/api/class-playwright)

### Recommended Learning
- [Playwright Testing Best Practices](https://playwright.dev/python/docs/best-practices)
- [Migrating from Selenium to Playwright](https://playwright.dev/python/docs/selenium-to-playwright)
- [Playwright Locators Guide](https://playwright.dev/python/docs/locators)
- [Auto-waiting in Playwright](https://playwright.dev/python/docs/actionability)

### Community
- [Playwright Discord](https://discord.com/invite/playwright-807756831384403968)
- [Robot Framework Slack](https://robotframework.slack.com/)
- [Stack Overflow - Playwright Tag](https://stackoverflow.com/questions/tagged/playwright)

## 🎯 Use Cases

### QA Automation Engineers
- Migrate existing Robot Framework test suites to Python
- Learn Playwright Python API quickly
- Reference during test development
- Train team members on Playwright

### Development Teams
- Standardize on Playwright Python for E2E testing
- Quick reference for common actions
- Understand argument options and defaults
- Implement robust test automation

### DevOps Engineers
- Integrate Playwright into CI/CD pipelines
- Configure browser contexts for different environments
- Optimize test execution with proper arguments
- Debug test failures with tracing and screenshots

## 🔒 Security & Privacy

- **No Data Collection**: Runs entirely client-side
- **No External Calls**: Except Tailwind CSS CDN
- **No Analytics**: No tracking or monitoring
- **Offline Capable**: Download and use offline (except CSS CDN)

## 📄 License

This guide is provided as-is for educational and reference purposes. Feel free to use, modify, and distribute as needed.

## ✨ Credits

Created for QA automation engineers transitioning from Robot Framework to Playwright Python.

Built with:
- Vanilla JavaScript (no frameworks)
- Tailwind CSS for styling
- Love for automation testing ❤️

## 📞 Support

For questions, issues, or suggestions:
- Open an issue in the repository
- Reach out via email
- Join the Playwright community on Discord

---

**Last Updated**: January 2026  
**Playwright Version**: Compatible with Playwright Python 1.40+  
**Browser Library Version**: Based on Browser Library 17.x

**Happy Testing! 🚀**
