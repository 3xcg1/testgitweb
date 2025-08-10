# GitHub Code Review & Preview Interface

A comprehensive web-based interface for reviewing, previewing, and managing code with full GitHub integration and Looker SDK support.

## Features

### 🔍 Code Review & Preview
- **Real-time code preview** with syntax highlighting
- **Side-by-side diff view** for change comparison
- **Interactive file tree** navigation
- **Multi-language support** (Python, JavaScript, JSON, Markdown, etc.)

### 🐙 GitHub Integration
- **Git Fetch**: Pull latest changes from remote repository
- **Git Push**: Commit and push changes to GitHub
- **Branch Management**: Switch between different branches
- **Pull & Run**: Download and execute code directly from GitHub

### 📊 Looker SDK Integration
- **Full Looker SDK support** for data analytics
- **Dashboard management** and export capabilities
- **SQL query execution** with pandas integration
- **User activity tracking** and reporting
- **Look creation** and management

## Setup Instructions

### Prerequisites
- Python 3.9 or higher
- GitHub account with repository access
- Looker instance with API credentials

### Installation

1. **Clone the repository**
   \`\`\`bash
   git clone https://github.com/your-username/github-code-reviewer.git
   cd github-code-reviewer
   \`\`\`

2. **Install dependencies**
   \`\`\`bash
   pip install -r requirements.txt
   \`\`\`

3. **Environment Configuration**
   Create a \`.env\` file:
   \`\`\`env
   # GitHub Configuration
   GITHUB_TOKEN=your_github_token_here
   GITHUB_REPO_URL=https://github.com/user/repo.git

   # Looker Configuration
   LOOKER_BASE_URL=https://your-instance.looker.com
   LOOKER_CLIENT_ID=your_client_id
   LOOKER_CLIENT_SECRET=your_client_secret
   \`\`\`

### Usage

1. **Open the interface**
   - Open \`index.html\` in your web browser
   - Or serve it using a local web server

2. **Configure GitHub**
   - Enter your repository URL
   - Add your GitHub personal access token
   - Select the target branch

3. **Configure Looker**
   - Enter your Looker instance details
   - Test the connection
   - Start using Looker SDK features

## Features in Detail

### Code Preview Panel
- **Syntax Highlighting**: Powered by Prism.js
- **File Navigation**: Click files in the sidebar to view
- **Live Updates**: Changes reflect immediately

### Git Operations
- **Fetch**: \`git fetch origin\`
- **Push**: \`git add . && git commit -m "message" && git push\`
- **Pull & Run**: \`git pull && python app.py\`

### Looker SDK Capabilities
- Dashboard listing and management
- PDF export functionality
- SQL query execution
- User activity monitoring
- Look creation and sharing

## API Reference

### LookerManager Class
\`\`\`python
from looker_integration import AdvancedLookerManager

# Initialize
looker = AdvancedLookerManager()

# Get all dashboards
dashboards = looker.get_all_dashboards()

# Export dashboard
looker.export_dashboard_to_pdf('123', 'output.pdf')

# Run SQL query
df = looker.run_sql_query('SELECT * FROM users', 'my_connection')
\`\`\`

## Security Considerations

- **Never commit sensitive credentials** to version control
- **Use environment variables** for all API keys and tokens
- **Implement proper access controls** in production
- **Regularly rotate API keys** and tokens

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request

## License

MIT License - see LICENSE file for details

## Support

For issues and questions:
- Create an issue on GitHub
- Check the documentation
- Review the example code

---

**Built with ❤️ for modern development workflows**`