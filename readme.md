# CityConnect

A civic engagement platform for citizens and city administrators to collaboratively report, verify, and resolve local issues with gamified rewards and transparent tracking.

## Overview

CityConnect bridges the gap between citizens and municipal departments by providing a structured system for reporting civic issues like potholes, waste management, and infrastructure problems. The platform combines AI-powered verification, department-specific workflows, and a reward system to encourage community participation.

Built during a hackathon and refined for production readiness.

## Key Features

**For Citizens:**
- Report issues with photos, location, and descriptions
- Complete eco-friendly tasks to earn rewards
- Track issue resolution status in real-time
- Redeem eco-coins for vouchers and event tickets
- Compete on community leaderboard

**For Administrators:**
- Department-specific dashboards for issue management
- AI-assisted image verification (OpenAI/Hugging Face)
- Post city news and announcements
- Track department performance metrics
- Approve or reject submitted reports

**Platform Capabilities:**
- Role-based access control (citizen/admin)
- Automated image verification system
- Geolocation-based issue tracking
- Gamification with badges and leaderboard
- Mobile-responsive design

## Tech Stack

- **Backend:** Django (Python)
- **Frontend:** Django Templates, HTML5, CSS3, JavaScript
- **Database:** SQLite (PostgreSQL-ready)
- **AI Integration:** OpenAI API, Hugging Face Inference API
- **Image Processing:** Pillow
- **Geolocation:** Geopy

## Project Structure
```
city-connect-main/
├── admin_panel/      # Department admin dashboards
├── cityconnect/      # Project settings and root URLs
├── core/             # User, news, badges, main views
├── issues/           # Issue/task reporting, AI verification
├── store/            # Store offers, redemptions
├── static/           # Static files (CSS, JS, images)
├── styles/           # Global styles
├── templates/        # HTML templates (per app)
├── requirements.txt  # Python dependencies
├── manage.py         # Django management script
└── ...
```

## Setup

**Prerequisites:**
- Python 3.8+
- pip
- Virtual environment (recommended)

**Installation:**

```bash
# Clone repository
git clone https://github.com/VishalGhuge111/city-connect.git
cd city-connect

# Create virtual environment
python -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt

# Configure environment
cp .env.example .env
# Edit .env with your settings

# Setup database
python manage.py migrate
python manage.py createsuperuser

# Run development server
python manage.py runserver
```

**Environment Variables:**

```env
SECRET_KEY=your-secret-key
DEBUG=True
OPENAI_API_KEY=your-key  # Optional
HF_API_KEY=your-key      # Optional
```

## Usage

**Access Points:**
- Main application: `http://localhost:8000/`
- Admin panel: `http://localhost:8000/admin/`
- Department dashboard: `http://localhost:8000/admin_panel/`

**User Flows:**
1. Citizens register and submit issue reports with images
2. AI verification system processes submitted images
3. Department admins review and manage issues
4. Citizens earn eco-coins for verified actions
5. Rewards redeemed through integrated store

## Core Components

### Issues System
Handles civic issue reporting, categorization, and tracking through resolution. Includes automated AI verification for submitted images.

### Admin Panel
Department-specific dashboards for managing assigned issues, posting announcements, and tracking resolution metrics.

### Rewards Store
Eco-coin economy where citizens redeem earned points for vouchers, discounts, and event access.

### User Profiles
Role-based access with citizen and admin views, activity tracking, and leaderboard integration.

## AI Verification

The platform includes optional AI-powered image verification:
- Validates submitted images match reported issue types
- Uses OpenAI or Hugging Face APIs
- Provides confidence scores for admin review
- Designed for MVP/demo; requires hardening for production

## Development

**Create demo data:**
```bash
python manage.py create_demo_issues
```

**Run tests:**
```bash
python manage.py test
```

## Deployment Considerations

- Configure production database (PostgreSQL recommended)
- Set up media file storage (S3, Cloudinary, etc.)
- Secure API keys in environment variables
- Enable HTTPS for production
- Configure allowed hosts and CORS
- Set DEBUG=False in production

## Contributing

Contributions welcome. Please open an issue before submitting major changes.

## License

MIT License - see LICENSE file for details.

---

**Status:** Active development • Originally built for hackathon • Documented for production use
