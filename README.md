
# ALX Travel App

## Overview
This Travel App is a Django REST Framework based backend project designed to manage listings and bookings for travel accommodations. It includes user roles (Guest, Host, Admin), booking management, and reviews. The API allows authenticated users to create and manage listings and bookings.

---

## Features
- User registration and authentication (email-based).
- Hosts can create, update, and delete listings.
- Guests can view listings and create bookings.
- Bookings include check-in/out dates, guest count, and total price.
- Booking status management: Pending, Confirmed, Cancelled.
- Reviews linked to bookings.
- Role-based permissions to restrict access.

---

## API Endpoints

### Authentication
- `POST /api/token/` - Obtain auth token (email & password)
- `POST /api/token/refresh/` - Refresh auth token

### Users
- `GET /api/users/` - List users (Admin access recommended)
- `POST /api/users/` - Register new user
- `GET /api/users/{user_id}/` - Retrieve user info

### Listings (Hosts only)
- `GET /api/listings/` - List your listings
- `POST /api/listings/` - Create new listing
- `GET /api/listings/{listing_id}/` - Retrieve a listing
- `PUT /api/listings/{listing_id}/` - Update a listing
- `DELETE /api/listings/{listing_id}/` - Delete a listing

### Bookings (Guests only)
- `GET /api/bookings/` - List your bookings
- `POST /api/bookings/` - Create a booking
- `GET /api/bookings/{booking_id}/` - Retrieve a booking
- `PUT /api/bookings/{booking_id}/` - Full update of a booking
- `PATCH /api/bookings/{booking_id}/` - Partial update of a booking
- `DELETE /api/bookings/{booking_id}/` - Cancel/delete a booking

### Reviews (Guests only)
- `GET /api/reviews/` - List your reviews
- `POST /api/reviews/` - Create a review for a booking
- `GET /api/reviews/{review_id}/` - Retrieve a review
- `PUT /api/reviews/{review_id}/` - Update a review
- `DELETE /api/reviews/{review_id}/` - Delete a review

---

## Data Format Examples

### Create Booking Example JSON
```json
{
  "listing": "f399d2e8-1002-4300-b4bf-44aa3a72408f",
  "check_in_date": "2025-08-03",
  "check_out_date": "2025-08-06",
  "num_guests": 2,
  "total_price": "3600.00"
}
```

---

## Setup Instructions

1. Clone the repo
2. Create and activate virtual environment
3. Install requirements via `pip install -r requirements.txt`
4. Run migrations: `python manage.py migrate`
5. Create superuser: `python manage.py createsuperuser`
6. Run server: `python manage.py runserver`

---

## Notes
- Permissions are role-based: Only Hosts can manage listings; only Guests can create bookings and reviews.
- Booking status is managed internally and defaults to `pending` on creation.
- The `booking_status` field is read-only through the API to prevent unauthorized changes.

---

Feel free to contribute or raise issues!

---

**Author:** Ikaelelo Motlhako  
**Date:** 2025 