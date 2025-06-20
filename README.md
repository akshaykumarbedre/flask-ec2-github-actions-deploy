# Flask EC2 GitHub Actions Deploy 🚀

A simple and stylish Flask web application deployed to an AWS EC2 instance using a fully automated GitHub Actions CI/CD pipeline.

## 📁 Project Structure

```
.
├── .github/
│   └── workflows/
│       └── deploy.yml        # GitHub Actions deployment workflow
├── templates/
│   └── index.html            # Bootstrap-styled dashboard HTML
├── app.py                    # Flask application
├── requirements.txt          # Python dependencies

```

## 🖥️ Live Dashboard

The landing page displays a dashboard showing:

- Deployment status
- EC2 instance metadata
- CI/CD architecture
- Deployment history

Styled with Bootstrap 5 and AWS-inspired colors.

## 🚀 Deployment Pipeline

Automated deployment using GitHub Actions:

- Push to `main` triggers deployment
- Code is securely copied to EC2
- EC2 installs dependencies and restarts the Flask app using `systemctl`

### Workflow: `.github/workflows/deploy.yml`

- Uses `appleboy/scp-action` to copy files
- Uses `appleboy/ssh-action` to restart the app
- Secrets like `EC2_HOST`, `EC2_SSH_KEY` are configured in the GitHub repo

## 🛠️ Setup Instructions

### Prerequisites

- AWS EC2 instance (Ubuntu recommended)
- SSH key access
- Python 3.8+
- GitHub repo with secrets set:
  - `EC2_HOST`
  - `EC2_USER`
  - `EC2_SSH_KEY` (private SSH key as a secret)

### 1. Clone the Repo

```bash
git clone https://github.com/your-username/flask-ec2-github-actions-deploy.git
cd flask-ec2-github-actions-deploy
```

### 2. Run Locally (for testing)

```bash
pip install -r requirements.txt
python app.py
```

Visit: `http://localhost:5000`

### 3. Deploy via GitHub Actions

* Push your code to the `main` branch.
* GitHub Actions will automatically deploy it to the configured EC2 instance.

## 🔒 GitHub Secrets (required)

| Secret Name   | Description                        |
| ------------- | ---------------------------------- |
| `EC2_HOST`    | Public IP/DNS of your EC2 instance |
| `EC2_USER`    | EC2 username (e.g., ubuntu)        |
| `EC2_SSH_KEY` | Private SSH key for EC2 access     |

## 🧪 Tech Stack

* **Flask** - Python Web Framework
* **Gunicorn** - WSGI Server
* **GitHub Actions** - CI/CD
* **AWS EC2** - Deployment Target
* **Bootstrap 5** - Frontend Styling

## 👨‍💻 Author

**Akshay**
*This project demonstrates automated infrastructure deployment with simplicity and elegance.*
---
##  Screenshort
![image](https://github.com/user-attachments/assets/d28ec224-0673-4565-bc0f-acfbbdbf2c01)

---

## 📄 License

MIT License. See `LICENSE` file for more info.
