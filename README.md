# AWS Roboshop Shell Scripting 🚀
Automated provisioning and configuration of Roboshop microservices on AWS using modular Bash scripts.

<details>
  <summary><strong>📑 Table of Contents</strong></summary>

- [AWS Roboshop Shell Scripting 🚀](#aws-roboshop-shell-scripting-)
  - [✨ Features](#-features)
  - [🧭 Quickstart](#-quickstart)
    - [Requirements](#requirements)
    - [Installation](#installation)
    - [Configuration](#configuration)
    - [Usage Example](#usage-example)
  - [🔧 Commands](#-commands)
  - [🧪 Testing \& Linting](#-testing--linting)
  - [🧰 Troubleshooting \& FAQ](#-troubleshooting--faq)
  - [📋 Contributing](#-contributing)
  - [📄 License](#-license)
</details>

---

## ✨ Features

- Automated setup for Roboshop microservices: frontend, MongoDB, catalogue, Redis, user, cart, MySQL, RabbitMQ, shipping, payment.
- Robust logging for all operations to `/var/log/roboshop-logs`.
- Root privilege checks for safe execution.
- Modular validation for each installation/configuration step.
- Downloads and configures service artifacts from S3.
- Service management via systemd.
- Custom Nginx configuration deployment.
- Easy extensibility for new services.

---

## 🧭 Quickstart

### Requirements

- **OS:** Linux (RHEL/CentOS/Amazon Linux recommended)
- **Shell:** Bash 4.x+
- **Tools:** `dnf`, `curl`, `unzip`, `systemctl`
- **Permissions:** Root access required

### Installation

```sh
git clone https://github.com/your-org/AWS-roboshop-ShellScript1.git
cd AWS-roboshop-ShellScript1/repo/AWS-roboshop-ShellScript1
```

### Configuration

- Ensure all required service config files (e.g., `nginx.conf`, `mongo.repo`, `*.service`) are present in the script directory.
- No `.env.example` detected; configuration is handled via script arguments and environment.

### Usage Example

To set up the frontend service:

```sh
sudo ./01-frontend.sh
```

Repeat similarly for other microservices (`02-mongodb.sh`, `03-catalogue.sh`, etc.).

---

## 🔧 Commands

| Script Name         | Purpose                                 | Usage                        | Example                      |
|---------------------|-----------------------------------------|------------------------------|------------------------------|
| `01-frontend.sh`    | Setup and configure Nginx frontend      | `sudo ./01-frontend.sh`      | `sudo ./01-frontend.sh`      |
| `02-mongodb.sh`     | Install and configure MongoDB           | `sudo ./02-mongodb.sh`       | `sudo ./02-mongodb.sh`       |
| `03-catalogue.sh`   | Deploy catalogue microservice           | `sudo ./03-catalogue.sh`     | `sudo ./03-catalogue.sh`     |
| `04-redis.sh`       | Install and configure Redis             | `sudo ./04-redis.sh`         | `sudo ./04-redis.sh`         |
| `05-user.sh`        | Deploy user microservice                | `sudo ./05-user.sh`          | `sudo ./05-user.sh`          |
| `06-cart.sh`        | Deploy cart microservice                | `sudo ./06-cart.sh`          | `sudo ./06-cart.sh`          |
| `07-mysql.sh`       | Install and configure MySQL             | `sudo ./07-mysql.sh`         | `sudo ./07-mysql.sh`         |
| `08-rabbitmq.sh`    | Install and configure RabbitMQ          | `sudo ./08-rabbitmq.sh`      | `sudo ./08-rabbitmq.sh`      |
| `09-shipping.sh`    | Deploy shipping microservice            | `sudo ./09-shipping.sh`      | `sudo ./09-shipping.sh`      |
| `10-payment.sh`     | Deploy payment microservice             | `sudo ./10-payment.sh`       | `sudo ./10-payment.sh`       |

> All scripts require root privileges. Logs are written to `/var/log/roboshop-logs`.

---

## 🧪 Testing & Linting

Run [ShellCheck](https://www.shellcheck.net/) on all scripts:

```sh
shellcheck *.sh
```

Format scripts with [shfmt](https://github.com/mvdan/sh):

```sh
shfmt -w -i 4 *.sh
```

No automated unit/integration tests detected. Manual validation recommended after each deployment.

---

## 🧰 Troubleshooting & FAQ

1. **ERROR:: Please run this script with root access**
   - Solution: Prefix command with `sudo`.
2. **Missing binaries (`dnf`, `curl`, `unzip`)**
   - Solution: Install required packages via your OS package manager.
3. **Service fails to start**
   - Solution: Check logs in `/var/log/roboshop-logs` and systemd status.
4. **Permission denied on log folder**
   - Solution: Ensure `/var/log/roboshop-logs` is writable by root.
5. **Network issues downloading artifacts**
   - Solution: Verify internet connectivity and S3 URL accessibility.

---

## 📋 Contributing

Contributions welcome! Please follow these guidelines:

- Fork the repo and create feature branches.
- Ensure scripts pass `shellcheck` and are POSIX-compliant.
- Submit pull requests with clear descriptions.

---
## 🛠️ Related Repositories & Continuous Learning 📚✨

Ready to advance your shell scripting and automation skills? Explore these curated repositories for a hands-on journey from foundational scripts to cloud-scale automation:

- [AWS-roboshop-ShellScript1](https://github.com/nischiashok/AWS-roboshop-ShellScript1)  
  ☁️ **Roboshop Automation Scripts for AWS** – Dive into practical, cloud-ready scripts powering resilient microservices on AWS! 🚀

- [AWS-roboshop-ShellScript2](https://github.com/nischiashok/AWS-roboshop-ShellScript2)  
  🤖 **Integrated Infrastructure Setup** – Experience seamless Roboshop deployments with unified automation for common folders and services. 🌐⚙️

---

## 🤝 Credits & Connect 💬❤️

Inspired by cloud-native DevOps workflows and automation best practices.  
Created with dedication by [nischitha A](https://github.com/nischiashok) 👩‍💻✨





---
