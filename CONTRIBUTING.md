# Contributing to Recruitment Agency

Thank you for your interest in contributing! We welcome contributions from everyone.

## Ways to Contribute

- 🐛 Report bugs
- 💡 Suggest features
- 📖 Improve documentation
- 🔧 Submit code improvements
- 🧪 Add tests

## Getting Started

1. **Fork** the repository
2. **Clone** your fork:
   ```bash
   git clone https://github.com/YOUR_USERNAME/Recruitment-Agency.git
   cd Recruitment-Agency
   ```
3. **Create a feature branch:**
   ```bash
   git checkout -b feature/your-feature-name
   ```
4. **Set up development environment:**
   ```bash
   python -m venv venv
   source venv/bin/activate  # or venv\Scripts\activate on Windows
   pip install -r requirements.txt
   pip install -r requirements-dev.txt  # Additional dev dependencies
   ```

## Development Workflow

### Before Making Changes

- Check existing [Issues](https://github.com/MustafaKocamann/Recruitment-Agency/issues) and [PRs](https://github.com/MustafaKocamann/Recruitment-Agency/pulls)
- For major features, open an issue first to discuss

### Code Standards

- Follow [PEP 8](https://pep8.org/) style guide
- Use [Black](https://github.com/psf/black) for code formatting
- Use [isort](https://pycqa.github.io/isort/) for import sorting
- Add type hints with [mypy](http://mypy-lang.org/)

### Formatting & Linting

```bash
# Format code
black app/ tests/

# Sort imports
isort app/ tests/

# Type checking
mypy app/

# Linting
flake8 app/ tests/
```

### Testing

```bash
# Run all tests
pytest

# Run specific test
pytest tests/test_module.py

# Run with coverage
pytest --cov=app tests/
```

## Commit Messages

Follow conventional commits format:

```
<type>(<scope>): <subject>

<body>

<footer>
```

**Types:** `feat`, `fix`, `docs`, `style`, `refactor`, `test`, `chore`

**Examples:**
- `feat(api): add candidate search endpoint`
- `fix(auth): resolve JWT token validation issue`
- `docs(readme): update installation steps`

## Pull Request Process

1. **Push** your branch:
   ```bash
   git push origin feature/your-feature-name
   ```

2. **Open a PR** with:
   - Clear title describing the change
   - Description of what was changed and why
   - Reference to related issue(s)
   - Screenshots/GIFs for UI changes (if applicable)

3. **Address review feedback** gracefully

4. **Ensure CI/CD passes** (all tests, linting, type checks)

5. Once approved, maintainers will merge your PR

## Code Review Criteria

- ✅ Tests included for new functionality
- ✅ Documentation updated
- ✅ Code is clear and maintainable
- ✅ No breaking changes (unless discussed)
- ✅ Performance impact considered

## Questions?

- 💬 Open a [Discussion](https://github.com/MustafaKocamann/Recruitment-Agency/discussions)
- 📧 Email: support@recruitment-agency.dev

---

Thank you for making Recruitment Agency better! 🎉
