# Airbnb Clone – Backend Requirement Specifications

## 1. User Authentication

- **Endpoint**: `POST /api/auth/register`
- **Input**: { email, password, role }
- **Output**: JWT token + user info
- **Validation**:
  - Email must be unique
  - Password minimum 8 chars
- **Performance**: Response within 500ms

## 2. Property Management

- **Endpoint**: `POST /api/properties`
- **Input**: { title, description, price, location, images }
- **Constraints**: Only authenticated hosts can access
- **Validation**: No empty fields, price > 0

## 3. Booking System

- **Endpoint**: `POST /api/bookings`
- **Input**: { propertyId, startDate, endDate }
- **Validation**:
  - Prevent overlapping bookings
  - Must be a guest user
- **Booking Status**: pending → confirmed → completed/canceled
