# Bank Statement Analyzer

A Python-based tool for analyzing and processing bank statements to extract meaningful insights and financial data.

## Overview

The Bank Statement Analyzer is designed to help individuals and businesses automatically process bank statements, extract transaction data, categorize expenses, and generate financial insights. This tool can handle various bank statement formats and provides a streamlined approach to financial data analysis.

## Features

- **Multi-format Support**: Process bank statements in various formats (PDF, CSV, Excel)
- **Transaction Extraction**: Automatically extract transaction details including dates, amounts, descriptions, and account information
- **Expense Categorization**: Intelligent categorization of transactions into predefined categories
- **Financial Analytics**: Generate insights such as spending patterns, monthly summaries, and trend analysis
- **Data Export**: Export processed data to various formats (CSV, Excel, JSON)
- **Visualization**: Create charts and graphs to visualize spending patterns and financial trends
- **Security**: Secure handling of sensitive financial data with encryption options

## Installation

### Prerequisites

- Python 3.8 or higher
- pip (Python package installer)

### Setup

1. Clone the repository:
```bash
git clone https://github.com/karthikperneti/BankStatementAnalyzer.git
cd BankStatementAnalyzer
```

2. Create a virtual environment (recommended):
```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

3. Install required dependencies:
```bash
pip install -r requirements.txt
```

## Usage

### Basic Usage

```python
from bank_analyzer import BankStatementAnalyzer

# Initialize the analyzer
analyzer = BankStatementAnalyzer()

# Load a bank statement
analyzer.load_statement("path/to/bank_statement.pdf")

# Process the statement
transactions = analyzer.extract_transactions()

# Categorize transactions
categorized_data = analyzer.categorize_transactions(transactions)

# Generate summary report
summary = analyzer.generate_summary(categorized_data)
print(summary)
```

### Command Line Interface

```bash
# Analyze a single statement
python -m bank_analyzer analyze --input statement.pdf --output report.json

# Process multiple statements
python -m bank_analyzer batch --input-dir statements/ --output-dir reports/

# Generate visualization
python -m bank_analyzer visualize --input report.json --output chart.png
```

## Supported File Formats

- **PDF**: Bank statements in PDF format
- **CSV**: Comma-separated values files
- **Excel**: .xlsx and .xls files
- **Text**: Plain text files with transaction data

## Project Structure

```
BankStatementAnalyzer/
├── src/
│   ├── bank_analyzer/
│   │   ├── __init__.py
│   │   ├── analyzer.py
│   │   ├── extractors/
│   │   ├── categorizers/
│   │   └── visualizers/
│   └── main.py
├── tests/
│   ├── test_analyzer.py
│   └── test_extractors.py
├── docs/
│   └── user_guide.md
├── examples/
│   └── sample_statements/
├── requirements.txt
├── setup.py
├── README.md
└── LICENSE
```

## Configuration

Create a `config.json` file to customize the analyzer behavior:

```json
{
  "categories": {
    "food": ["restaurant", "grocery", "cafe"],
    "transportation": ["gas", "uber", "parking"],
    "utilities": ["electric", "water", "internet"]
  },
  "output_format": "json",
  "visualization": {
    "chart_type": "bar",
    "color_scheme": "default"
  }
}
```

## Contributing

We welcome contributions to the Bank Statement Analyzer! Here's how you can help:

1. **Fork the repository**
2. **Create a feature branch**: `git checkout -b feature/new-feature`
3. **Make your changes**: Implement your feature or bug fix
4. **Add tests**: Ensure your changes are covered by tests
5. **Commit your changes**: `git commit -m "Add new feature"`
6. **Push to the branch**: `git push origin feature/new-feature`
7. **Submit a pull request**

### Development Setup

```bash
# Install development dependencies
pip install -r requirements-dev.txt

# Run tests
python -m pytest tests/

# Run linting
flake8 src/
black src/

# Run type checking
mypy src/
```

## Security and Privacy

- **Data Privacy**: All bank statement data is processed locally by default
- **Encryption**: Sensitive data can be encrypted using provided utilities
- **No Data Collection**: The tool does not send your financial data to external servers
- **Secure Storage**: Processed data is stored securely with appropriate permissions

## Roadmap

- [ ] Machine learning-based transaction categorization
- [ ] Support for additional bank formats
- [ ] Web-based user interface
- [ ] Integration with accounting software
- [ ] Mobile app companion
- [ ] Real-time bank account monitoring (with API integration)

## FAQ

**Q: Is my financial data safe?**
A: Yes, all processing is done locally on your machine. No data is sent to external servers.

**Q: What banks are supported?**
A: The tool is designed to work with standard bank statement formats. We're continuously adding support for more banks.

**Q: Can I customize transaction categories?**
A: Yes, you can customize categories through the configuration file or programmatically.

## License

This project is licensed under the Apache License 2.0 - see the [LICENSE](LICENSE) file for details.

## Contact

- **Author**: Karthik Perneti
- **Email**: karthik.perneti@gmail.com
- **GitHub**: [karthikperneti](https://github.com/karthikperneti)
- **Project Repository**: [BankStatementAnalyzer](https://github.com/karthikperneti/BankStatementAnalyzer)

## Acknowledgments

- Thanks to the open-source community for the libraries and tools that make this project possible
- Special thanks to contributors who help improve the analyzer

---

**Disclaimer**: This tool is for personal and educational use. Always verify the accuracy of extracted data and comply with your bank's terms of service when processing statements.