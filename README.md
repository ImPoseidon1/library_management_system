# Library Management System

## Project Overview
This project aims to build a library management system to add, track, and manage books in a library using Python, SQL, and Flask.

## Functional Requirements

### Phase 1: Core Functionalities
 **User Authentication and Authorization**
   - User Registration
   - User Login
   - Role-Based Access Control (Admin, Librarian, Patron)

 **Catalog Management**
   - Add New Books
   - Update Book Information
   - Delete Books
   - View Book Details

 **Search and Discovery**
   - Basic Search (by title, author, ISBN)
   - Advanced Search (by genre, publication date, etc.)
   - Filter and Sort Results

 **Circulation Management**
   - Borrow Books
   - Return Books
   - Renew Books
   - Track Borrowing History


### Phase 2: Enhanced Functionalities
 **Patron Management**
   - View Patron Details
   - Update Patron Information
   - Manage Patron Accounts

 **Inventory Management**
   - Track Inventory Levels
   - Automated Stock Updates
   - Generate Inventory Reports

 **Notifications and Alerts**
   - Due Date Reminders
   - Overdue Notices
   - Reservation Availability Notifications

 **Reservations and Holds**
   - Place Holds on Books
   - Manage Hold Requests
   - Notify Patrons When Holds are Available


### Phase 3: Advanced Functionalities
 **Reports and Analytics**
   - Generate Usage Reports
   - Track Circulation Statistics
   - Analyze Borrowing Trends
   - Customizable Reporting Tools

 **Acquisitions Management**
  - Manage Purchase Orders
  - Track Supplier Information
  - Budget Management

 **Serials Management**
  - Manage Periodicals and Journals
  - Track Subscription Status
  - Issue and Volume Management


### Phase 4: Additional Functionalities
 **User Reviews and Ratings**
  - Allow Patrons to Rate Books
  - Enable User Reviews and Comments

 **Mobile Application**
  - Develop a Mobile App for Patron Access
  - Implement Mobile-Friendly Features (e.g., barcode scanning for checkouts)


### Phase 5: Innovative Functionalities
 **Voice Search and Commands**
  - Enable Voice-Activated Search
  - Implement Voice Commands for Common Actions

 **Augmented Reality (AR) Integration**
  - Virtual Bookshelf for Book Discovery
  - AR Navigation within the Library

 **Gamification**
  - Introduce Reading Challenges and Rewards
  - Implement Leaderboards and Badges


### Book recommendation
  If time permits we can also add a book recommendation system for the users using a ML model.If a particular book is not available with the library,the patron will be recommended with the top 5 books based of the genre or the writer or any specific keyword which patron has typed.
 

# Business Rules based on the above Functional Requirements
## 1. Core:

### User Auth -> 
- All users must register with valid credentials to access the system.
- Users must log in to their accounts to borrow books or access personalized features(maybe reading recommendations, virtual bookshelves, alerts notifs and due dates similar to the ones mentioned above).
- certain functionalities' access within the system is restricted by user roles: Admin, Librarian, and Patron/User.

### Catalog Management ->
- Only users with Librarian or Admin roles can add, update, or delete book information.(Does deleting a book make sense practically tho? yes is books are torn and are at verge of expiry)
- All books must have a unique identifier (ISBN) to avoid duplicates in the catalog.
- Book details must include title, author, ISBN, genre, and publication date at minimum.

### Search and Discovery ->
- The system provides a basic search functionality, allowing searches by title, author, and ISBN. This is accessible to all the users.

### Circulation ->
- Patrons can borrow, return, and renew books according to library policies (loan periods, renewal limits etc etc.).
- tracking borrowing history of each patron to facilitate smooth renewals and history re-views.
- Overdue books must trigger automatic alerts to the user's account.(Or a simple smtp email sending mechanism)
  we can collect a deposit ammount at the beginning of the renewal of account,and deduct the overdue ammount and return the remaining deposit ammount at end of the period.


## 2. Enhanced:

### Inventory Management ->
- The system automatically updates inventory levels when books are added, borrowed, returned, or removed.

### Alerts -> 
- Patrons receive due date reminders and overdue notices via their preferred contact method(email, SMS).
- Librarians receive alerts when stocks of popular books are low.

### Reservations and Holds -> 
- Patrons can place holds on borrowed books. Holds are managed on a first-come, first-served basis.
- Reservation availability notifs are sent automatically to patrons who have placed holds, when the book is available for pickup.

### Patron Management ->
- Librarians can view patron information, like contact details and borrowing history.

### Search and Discovery (Enhanced) ->
- search by genre/publication date, along with traditional Author, Book Name and ISBN(Typically People don't search using ISBN but just included) are available to enhance search functionality.

## 3. Advanced:

### Purchase Order creation and Approvals ->
- Only users with LIBRARIAN or ADMIN roles can create and approve purchase orders for new books and materials.
- All purchase orders must include details such as book title, author, ISBN, quantity, and total price
- Purchase orders must be approved by Admin before the order is placed with suppliers.

### Supplier Information Tracking ->
- The system must store supplier information, including contact details, product catalogs, and pricing.
- Librarians can add, update, or delete supplier information as needed.

### Budget mgmt ->
- The system must track budget allocations for acquisitions and purchases.
- Prices for each purchase order must be recorded and deducted from total budget.
- Differentiated Budget allocations for different categories of materaial like books, journals etc.

### Subscriptions mgmt ->
- The system must allow Librarians to manage subscriptions for serial publications like journals, magazines, and newspapers.
- Each subscription must include details such as the publication name, ISSN, frequency of publication, and subscription cost.
- track the renewal dates for subscriptions and notify Librarians in advance of upcoming renewals.
- view or cancel subscriptions as and when required
