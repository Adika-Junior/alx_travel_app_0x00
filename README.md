# ALX Travel App

A Django-based travel booking application with listings, bookings, and reviews functionality.

## Features

- **Listings**: Property listings with details such as location, price, amenities, and availability
- **Bookings**: Booking management with guest information and booking status
- **Reviews**: User reviews and ratings for listings
- **API Serializers**: Django REST Framework serializers for Listing and Booking models
- **Database Seeding**: Management command to populate the database with sample data

## Project Structure

```
alx_travel_app/
├── alx_travel_app/
│   ├── listings/
│   │   ├── models.py          # Listing, Booking, and Review models
│   │   ├── serializers.py     # DRF serializers for Listing and Booking
│   │   ├── management/
│   │   │   └── commands/
│   │   │       └── seed.py    # Database seeding command
│   │   └── ...
│   └── ...
└── manage.py
```

## Models

### Listing
Represents a property available for booking with fields including:
- Title, description, address, city, state, country
- Price per night, property type, max guests
- Bedrooms, bathrooms, amenities
- Availability status

### Booking
Represents a booking made for a listing with:
- Foreign key relationship to Listing
- Guest information (name, email, phone)
- Check-in and check-out dates
- Number of guests, total price, status
- Special requests

### Review
Represents a review for a listing with:
- Foreign key relationship to Listing
- Reviewer information
- Rating (1-5) and comment

## Setup

### Prerequisites
- Python 3.8+
- MySQL database server
- Virtual environment (recommended)

### Environment Setup

1. **Create and activate a virtual environment:**
```bash
python3 -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

2. **Create a `.env` file** in the project root with the following variables:
```env
# Django Settings
SECRET_KEY=your-secret-key-here
DEBUG=True
ALLOWED_HOSTS=localhost,127.0.0.1

# Database Configuration (MySQL)
DB_NAME=alx_travel_app
DB_USER=root
DB_PASSWORD=your-db-password
DB_HOST=127.0.0.1
DB_PORT=3306

# CORS Settings
CORS_ALLOW_ALL=True
```

3. **Install dependencies:**
```bash
pip install -r alx_travel_app/requirement.txt
```

4. **Create the MySQL database:**
```bash
mysql -u root -p
CREATE DATABASE alx_travel_app CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;
```

5. **Run migrations:**
```bash
python manage.py makemigrations
python manage.py migrate
```

6. **Seed the database with sample data:**
```bash
python manage.py seed
```

To clear existing data before seeding:
```bash
python manage.py seed --clear
```

## API Serializers

### ListingSerializer
Serializes Listing model with all fields for API responses.

### BookingSerializer
Serializes Booking model with:
- Listing information (title and ID)
- Guest details
- Booking dates and pricing
- Validation for check-in/check-out dates and guest limits

## Management Commands

### seed
Populates the database with sample listings, bookings, and reviews.

Usage:
```bash
python manage.py seed
python manage.py seed --clear  # Clear existing data first
```

## Development

This project uses:
- Django 5.2.7
- Django REST Framework
- MySQL database

## License

This project is part of the ALX Software Engineering program.

