# Expense Tracker

## Overview
Expense Tracker is a full-stack web application designed to help individuals and organizations efficiently manage, track, and analyze their financial expenses. Built with modern technologies and enterprise-grade best practices, it provides a secure, scalable, and user-friendly platform for expense management.

## Key Features

- **Secure Authentication**: Industry-standard encryption with bcrypt and Argon2 password hashing
- **User Account Management**: Comprehensive user registration and profile management
- **Expense Logging**: Intuitive interface for recording and categorizing expenses
- **Real-time Analytics**: Dashboard with expense summaries and visual reports
- **Data Validation**: Enterprise-grade input validation using Pydantic and email-validator
- **Responsive Design**: Mobile-friendly interface built with React
- **PostgreSQL Integration**: Reliable data persistence with SQLAlchemy ORM
- **RESTful API**: Well-structured backend API with Python

## Technology Stack

### Backend
- **Python**: Core backend language
- **SQLAlchemy**: ORM for database operations
- **PostgreSQL**: Primary data store (via psycopg-binary)
- **Pydantic**: Data validation and serialization
- **Authentication**: bcrypt, passlib with Argon2 support
- **Environment Management**: python-dotenv for configuration

### Frontend
- **React 18**: Modern UI framework with hooks support
- **React Router DOM**: Client-side routing and navigation
- **Vite**: Next-generation build tool for fast development
- **ESLint**: Code quality and consistency

### DevOps & Tools
- **Node.js/npm**: Frontend package management
- **pip**: Python package management

## Architecture

```
expense_tracker/
├── app/                    # Backend application
│   ├── core/              # Core business logic
│   ├── models/            # Database models
│   ├── schemas/           # Pydantic schemas
│   ├── routes/            # API endpoints
│   └── utils/             # Utility functions
├── frontend/              # React frontend
│   ├── src/
│   │   ├── components/    # React components
│   │   ├── pages/         # Page components
│   │   ├── hooks/         # Custom React hooks
│   │   └── utils/         # Frontend utilities
│   └── public/            # Static assets
├── requirements.txt       # Python dependencies
└── README.md             # Project documentation
```

## Getting Started

### Prerequisites
- Python 3.8+
- Node.js 16+
- PostgreSQL 12+
- npm or yarn

### Backend Setup

1. **Clone the repository**
   ```bash
   git clone https://github.com/Rashi3108agrawal/expense_tracker.git
   cd expense_tracker
   ```

2. **Create virtual environment**
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

4. **Configure environment variables**
   ```bash
   cp .env.example .env
   # Edit .env with your database credentials and settings
   ```

5. **Initialize database**
   ```bash
   python -m app.core.database init
   ```

6. **Start backend server**
   ```bash
   python -m uvicorn app.main:app --reload
   ```

### Frontend Setup

1. **Navigate to frontend directory**
   ```bash
   cd frontend
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Configure API endpoint**
   ```bash
   # Create .env.local file
   VITE_API_URL=http://localhost:8000
   ```

4. **Start development server**
   ```bash
   npm run dev
   ```

5. **Build for production**
   ```bash
   npm run build
   ```

## API Documentation

### Authentication Endpoints
- `POST /api/auth/register` - Register new user
- `POST /api/auth/login` - User login
- `POST /api/auth/logout` - User logout

### Expense Endpoints
- `GET /api/expenses` - List all expenses
- `POST /api/expenses` - Create new expense
- `GET /api/expenses/{id}` - Get expense details
- `PUT /api/expenses/{id}` - Update expense
- `DELETE /api/expenses/{id}` - Delete expense

### Analytics Endpoints
- `GET /api/analytics/summary` - Get expense summary
- `GET /api/analytics/trends` - Get spending trends

## Security Best Practices

- **Password Security**: Dual-layer hashing with bcrypt and Argon2
- **Data Validation**: Comprehensive input validation with Pydantic
- **Email Verification**: Email validation for user registration
- **Environment Variables**: Sensitive data managed via environment variables
- **Database Security**: SQL injection prevention through ORM usage
- **CORS**: Configured for secure cross-origin requests

## Configuration

### Environment Variables

Create a `.env` file in the project root:

```
DATABASE_URL=postgresql://user:password@localhost:5432/expense_tracker
SECRET_KEY=your-secret-key-here
DEBUG=False
ENVIRONMENT=production
```

## Development Workflow

### Running Tests
```bash
# Backend tests
pytest app/tests/ -v

# Frontend tests
npm run test
```

### Code Quality
```bash
# Lint frontend code
npm run lint

# Format code
black app/
```

### Database Migrations
```bash
alembic init migrations
alembic revision --autogenerate -m "migration description"
alembic upgrade head
```

## Performance Considerations

- Database connection pooling with SQLAlchemy
- Frontend optimization with Vite's tree-shaking
- React's built-in optimization with memoization
- Lazy loading for large datasets
- Caching strategies for frequently accessed data

## Monitoring & Logging

- Centralized logging configuration
- Error tracking and reporting
- Performance metrics collection
- User activity audit logs

## Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

### Code Style
- Backend: Follow PEP 8 guidelines
- Frontend: Follow ESLint configuration
- Commit messages: Use conventional commits

## Deployment

### Backend Deployment
- Supports deployment on Heroku, AWS, DigitalOcean, or self-hosted servers
- Uses Gunicorn for production WSGI server
- Database migrations handled via Alembic

### Frontend Deployment
- Build artifacts optimized for production
- Can be deployed to Vercel, Netlify, GitHub Pages, or static hosting
- Environment variables configured for different deployment stages

## Troubleshooting

### Common Issues

**Database Connection Error**
- Verify PostgreSQL is running
- Check DATABASE_URL in .env file
- Ensure database user has proper permissions

**Frontend Build Errors**
- Clear node_modules: `rm -rf node_modules && npm install`
- Clear Vite cache: `rm -rf node_modules/.vite`

**Port Already in Use**
- Change port in configuration or kill existing process

## License

This project is licensed under the MIT License - see LICENSE file for details.

## Support & Contact

For support, issues, or questions:
- Open an issue on GitHub
- Contact: Rashi3108agrawal
- Documentation: [Project Wiki](https://github.com/Rashi3108agrawal/expense_tracker/wiki)

## Roadmap

- [ ] Mobile application (React Native)
- [ ] Advanced reporting and export features
- [ ] Multi-currency support
- [ ] Budget planning and alerts
- [ ] Team collaboration features
- [ ] Integration with banking APIs
- [ ] Machine learning-based expense categorization

## Changelog

### Version 1.0.0 (Initial Release)
- Core expense tracking functionality
- User authentication system
- Dashboard and analytics
- Responsive UI design

---

**Last Updated**: 2026-04-15 03:09:22
**Maintainer**: Rashi3108agrawal
**Status**: Active Development