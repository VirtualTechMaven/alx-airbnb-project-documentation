# Backend Feature Requirements

---

## 1. User Authentication

### Endpoints:
- POST /users/
- POST /auth/login/
- GET /users/{id}/

### Input:
- Email (required)
- Password (required)
- First Name, Last Name

### Output:
- JSON with auth token and profile info

### Validations:
- Email must be in valid format and unique
- Password must be at least 8 characters

### Performance Criteria:
- Response time: under 500ms
- Token expiry: 24 hours

---

## 2. Property Management

### Endpoints:
- POST /properties/
- GET /properties/
- PUT /properties/{id}/
- DELETE /properties/{id}/

### Input:
- Name, Description, Location, Price per night

### Output:
- Property listing details

### Validations:
- All fields are required except description
- Price must be a valid decimal

### Performance Criteria:
- Fetch all properties in < 800ms
- Image upload optimized using caching/CDN

---

## 3. Booking System

### Endpoints:
- POST /bookings/
- GET /bookings/{id}/
- PUT /bookings/{id}/
- DELETE /bookings/{id}/

### Input:
- Property ID
- User ID
- Start Date, End Date

### Output:
- Booking confirmation and price

### Validations:
- Dates must be valid and not overlap
- Booking only allowed on available properties

### Performance Criteria:
- Prevent double-bookings with locking mechanism
- Confirmations sent in < 1s
