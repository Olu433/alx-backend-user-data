# Personal Data Backend

This project focuses on implementing secure and efficient methods to handle Personally Identifiable Information (PII) in a backend system. The tasks cover logging, filtering sensitive data, encrypting passwords, and connecting to a secure database.

## Features

1. **PII Filtering**:
   - Use regex to obfuscate PII fields in log messages.
   - Obfuscated fields are replaced with a customizable redaction string.

2. **Custom Log Formatter**:
   - Implements a `RedactingFormatter` class to sanitize log messages.
   - Filters sensitive fields from log records.

3. **Logger Setup**:
   - Creates a logger (`user_data`) with a `StreamHandler` using the `RedactingFormatter`.
   - Logs only up to `INFO` level and does not propagate messages to other loggers.

4. **Secure Database Connection**:
   - Connects to a database using credentials stored in environment variables.
   - Uses `mysql-connector-python` for database connectivity.

5. **Data Retrieval and Filtering**:
   - Retrieves rows from a database table and logs filtered output.
   - Ensures sensitive fields are sanitized in logs.

6. **Password Encryption and Validation**:
   - Hashes passwords securely using the `bcrypt` library.
   - Validates plaintext passwords against hashed passwords.

## Requirements

- **Environment**: 
  - Ubuntu 18.04 LTS
  - Python 3.7
- **Packages**: 
  - `bcrypt`
  - `mysql-connector-python`

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/Olu433/alx-backend-user-data.git
   cd alx-backend-user-data/0x00-personal_data
   ```

2. Install dependencies:
   ```bash
   pip3 install bcrypt mysql-connector-python
   ```

3. Set up environment variables:
   ```bash
   export PERSONAL_DATA_DB_USERNAME="root"
   export PERSONAL_DATA_DB_PASSWORD=""
   export PERSONAL_DATA_DB_HOST="localhost"
   export PERSONAL_DATA_DB_NAME="my_db"
   ```

4. Prepare the database:
   ```bash
   mysql -uroot -p < main.sql
   ```

## Usage

### Running the Program

1. **Obfuscating Logs**:
   ```bash
   ./main.py
   ```

2. **Database Connection**:
   - Ensure your database server is running.
   - Use the provided `get_db()` function to connect and fetch data.

3. **Password Operations**:
   - Hash passwords using the `hash_password` function.
   - Validate passwords with the `is_valid` function.

### Example Commands
- Hash a password:
  ```python
  from encrypt_password import hash_password
  print(hash_password("MySecurePassword"))
  ```
- Validate a password:
  ```python
  from encrypt_password import is_valid
  print(is_valid(hashed_password, "MySecurePassword"))
  ```

## Project Structure

```plaintext
.
├── README.md
├── filtered_logger.py  # PII filtering, logging, and database functions
├── encrypt_password.py # Password hashing and validation
├── main.py             # Example usages and test cases
├── main.sql            # SQL file for database setup
└── user_data.csv       # Sample data (if applicable)
```

## Learning Objectives

By completing this project, you will:
- Understand PII, non-PII, and personal data.
- Implement secure logging with PII filtering.
- Use environment variables for secure database authentication.
- Securely hash and validate passwords.

## Author

**Your Name**  
*Aspiring Backend Developer*  
GitHub: [your-github-profile](https://github.com/Olu433)

## License

This project is for educational purposes and follows no specific licensing terms.
```

