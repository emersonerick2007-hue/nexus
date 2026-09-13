# 🌐 Nexus - Proxy Log Bug Report Scanner

A powerful and intelligent bug report scanner designed to analyze proxy logs, detect anomalies, and generate comprehensive bug reports automatically.

## ✨ Features

- **Proxy Log Analysis**: Parse and analyze various proxy log formats (Nginx, Apache, HAProxy, Squid)
- **Anomaly Detection**: Identify suspicious patterns, errors, and performance issues
- **Automated Bug Reports**: Generate structured bug reports with severity levels
- **Real-time Monitoring**: Monitor proxy logs in real-time
- **Pattern Recognition**: ML-based detection of recurring issues
- **Export Reports**: Generate reports in JSON, CSV, and HTML formats
- **Configurable Rules**: Define custom detection rules
- **Performance Metrics**: Track response times, error rates, and traffic patterns

## 🚀 Quick Start

### Prerequisites
- Python 3.8+
- pip or conda

### Installation

```bash
git clone https://github.com/emersonerick2007-hue/nexus.git
cd nexus
pip install -r requirements.txt
```

### Basic Usage

```bash
# Analyze a proxy log file
python nexus.py analyze /path/to/proxy.log

# Monitor logs in real-time
python nexus.py monitor /var/log/nginx/access.log

# Generate report
python nexus.py report --input logs/ --output report.html

# Run with custom configuration
python nexus.py analyze --config config.yaml /path/to/logs/
```

## 📋 Configuration

Create a `config.yaml` file:

```yaml
scanner:
  log_format: "nginx"  # nginx, apache, haproxy, squid
  timezone: "UTC"
  
detection:
  enable_ml: true
  severity_threshold: "warning"
  
patterns:
  - name: "high_error_rate"
    threshold: 10
    window: 60  # seconds
  - name: "slow_response"
    threshold: 5000  # ms
    
output:
  format: "json"  # json, csv, html
  directory: "./reports"
```

## 📊 Supported Log Formats

| Format | Status | Support |
|--------|--------|---------|
| Nginx | ✅ | Full |
| Apache | ✅ | Full |
| HAProxy | ✅ | Full |
| Squid | ✅ | Full |
| Custom | ⚙️ | Configurable |

## 🔍 Detection Rules

Nexus automatically detects:
- HTTP error codes (4xx, 5xx)
- Timeout errors
- Connection refused
- SSL/TLS issues
- DDoS patterns
- Abnormal traffic spikes
- Slow response times
- DNS resolution failures
- Backend failures

## 📈 Output Example

```json
{
  "scan_timestamp": "2024-09-13T10:30:00Z",
  "total_requests": 150000,
  "errors_detected": 342,
  "severity_breakdown": {
    "critical": 5,
    "high": 28,
    "medium": 89,
    "low": 220
  },
  "top_issues": [
    {
      "id": "ERR_001",
      "type": "High Error Rate",
      "severity": "high",
      "count": 156,
      "percentage": 45.6,
      "recommendation": "Check backend health"
    }
  ],
  "performance_metrics": {
    "avg_response_time": "245ms",
    "p95_response_time": "1240ms",
    "p99_response_time": "2100ms"
  }
}
```

## 🛠️ Development

```bash
# Install development dependencies
pip install -r requirements-dev.txt

# Run tests
pytest tests/

# Run linter
flake8 nexus/

# Generate coverage report
pytest --cov=nexus tests/
```

## 📚 Documentation

- [Installation Guide](docs/installation.md)
- [Configuration Guide](docs/configuration.md)
- [API Reference](docs/api.md)
- [Custom Rules](docs/custom_rules.md)
- [Troubleshooting](docs/troubleshooting.md)

## 🤝 Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🆘 Support

- 📧 Email: support@nexus-scanner.dev
- 🐛 [Issue Tracker](https://github.com/emersonerick2007-hue/nexus/issues)
- 💬 [Discussions](https://github.com/emersonerick2007-hue/nexus/discussions)

## 🎯 Roadmap

- [ ] GraphQL API
- [ ] Docker containerization
- [ ] Kubernetes integration
- [ ] Machine learning improvements
- [ ] Web dashboard
- [ ] Slack/Teams notifications
- [ ] Database backends (PostgreSQL, MongoDB)

---

**Made with ❤️ by Emerson Erick**
