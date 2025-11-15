# ALX Travel App - Django Application

This is the main Django application package for the ALX Travel App project.

## Application Structure

```
alx_travel_app/
├── listings/          # Listings app with models, serializers, and views
├── settings.py        # Django project settings
├── urls.py            # Main URL configuration
├── wsgi.py            # WSGI configuration
└── asgi.py            # ASGI configuration
```

## Listings App

The `listings` app contains the core functionality for the travel booking system:

- **Models**: Listing, Booking, and Review models
- **Serializers**: Django REST Framework serializers for API endpoints
- **Management Commands**: Database seeding utilities

## Configuration

The application uses Django 5.2.7 with MySQL database support. Configuration is managed through `settings.py`.

## API Endpoints

The application provides RESTful API endpoints for:
- Listing management
- Booking operations
- Review submissions

## Development

This application is part of the ALX Software Engineering program travel booking project.

