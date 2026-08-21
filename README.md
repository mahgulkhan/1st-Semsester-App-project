# Color Spectrum

A console-based art store management system that provides user and admin functionalities for managing art supplies, stock, and customer services.

## Features

### User Functions
- Apply for membership card
- View available art stock with quantities and prices
- Order paintings
- Buy art supplies
- Rate the service (1-5 stars)

### Admin Functions
- Add new stock items
- View all stock with quantities and prices
- Remove specific stock items
- Trace any item in stock
- Update stock quantities and prices

### Authentication System
- Separate admin and user login
- New user registration with username/password creation
- Input validation for usernames (alphabetic only, no spaces) and passwords (5 digits only)
- Credentials stored in text files

## Tech Stack

- C++ with Windows-specific libraries
- Console-based interface with colored output
- File-based data persistence

## Project Structure

```
Color-Spectrum/
├── color_spectrum.cpp       # Complete source code
├── admin.txt                # Admin credentials storage
├── credentials.txt          # User credentials storage
└── README.md
```

## Compilation

### MinGW (g++)

```bash
g++ color_spectrum.cpp -o color_spectrum.exe
```

### Visual Studio (cl)

```bash
cl color_spectrum.cpp
```

## Authentication

### Admin Login
- Default admin credentials stored in `admin.txt`
- Format: `username,password`

### User Login
- Credentials stored in `credentials.txt`
- New users can register with:
  - Username: alphabetic characters only, no spaces
  - Password: exactly 5 digits (e.g., 12345)

## Menu Structure

### Main Menu
```
1. Admin Login
2. User Login
```

### User Menu
```
1. Apply for Membership Card
2. View Available Art Stock
3. Order Painting
4. Buy Art Supplies
5. Rate Our Service
6. Exit
```

### Admin Menu
```
1. Add Stock
2. View Added Art Stock
3. Remove Particular Stock
4. Trace Any Item from Stock
5. Update Stock
6. Exit
```

## Stock Management

Default stock items:

| Item | Quantity | Price (per item) |
|------|----------|------------------|
| Canvas | 10 | 200 |
| Brushes | 12 | 50 |
| Base | 3 | 350 |
| Paints | 34 | 80 |
| Crayons | 23 | 75 |
| Resin | 4 | 110 |
| Easel | 10 | 500 |
| Pencils | 19 | 30 |
| Artbook | 20 | 75 |
| Colors | 40 | 30 |

## Data Storage

- **admin.txt**: Stores admin credentials
- **credentials.txt**: Stores user credentials
- Data stored in CSV format: `username,password`
- Stock data initialized in arrays (not persistent between sessions)

## Key Functions

| Function | Purpose |
|----------|---------|
| `loginscr()` | Display login screen |
| `acredentials()` | Admin authentication |
| `ucredentials()` | User authentication/registration |
| `validusername()` | Validate username format |
| `validpass()` | Validate password format (5 digits) |
| `storedata()` | Save new user credentials |
| `selectedopt()` | User menu interface |
| `uselectedopt()` | Admin menu interface |
| `getfield()` | Parse CSV fields from files |

## Controls

- Console-based menu navigation with numeric input
- Windows-specific functions for colored output
- Keyboard input with `getch()`

## Limitations

- Windows-only (uses `windows.h` and `conio.h`)
- Stock data resets when application restarts
- No data persistence for orders or membership applications
- Maximum 100 items/stored users
- Passwords stored in plain text (not hashed)

## Troubleshooting

### File Not Found Errors
Ensure `admin.txt` and `credentials.txt` exist in the same directory as the executable.

### Compilation Errors
- Link against Windows libraries
- Ensure using C++11 or higher

### Login Issues
- Check file permissions for reading/writing
- Verify credentials format in text files
