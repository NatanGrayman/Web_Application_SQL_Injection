Analyzing and Fixing Security Vulnerabilities in a Web Application

## Project Overview

This project involves analyzing security vulnerabilities in a web application, identifying and fixing these vulnerabilities, and thoroughly testing the application to ensure it is secure. The primary focus was on SQL injection vulnerabilities and improving password storage security. This project highlights my SQL capabilities and my understanding of secure coding practices.

## Assignment Details

### Analyzing Security Vulnerabilities

1. **Database Examination**:
   - Utilized the `sqlite3` tool to examine the application's database.
   - Employed the `.schema` command for a comprehensive overview of the database structure.
   - Executed SQL queries directly at the command prompt to examine the database contents.

2. **Application Execution**:
   - Launched the web application using the command `./gradlew run` (or `gradlew run` for Windows).
   - Interacted with the application via a web browser at `http://localhost:8080`.

3. **SQL Injection Testing**:
   - Tested the application with various SQL injection payloads such as `' OR '1'='1`, `' OR 1=1 --`, and others.
   - Recorded successful SQL injection attempts that resulted in unauthorized access and exposure of confidential patient data.

4. **Vulnerability Analysis**:
   - Identified the use of string concatenation to incorporate user-supplied input into SQL queries, making the application susceptible to SQL injection attacks.
   - Found that passwords were stored as raw strings, posing a significant security risk.

### Fixing Security Vulnerabilities

1. **Implementing Prepared Statements**:
   - Updated the `AppServlet` source file to use prepared statements.
   - Modified `AUTH_QUERY` and `SEARCH_QUERY` variables to use placeholders (`?`) and filled values using the `setString` method.
   - Ensured user-supplied values were treated as data rather than executable SQL code.

2. **Code Modifications**:
   - Updated the `authenticated` method to execute the SQL query using a prepared statement.
   - Updated the `searchResults` method to execute the SQL query using a prepared statement.

3. **Testing and Validation**:
   - Repeated the initial experiment to ensure the application was no longer susceptible to SQL injection attacks.
   - Confirmed that the changes effectively prevented SQL injection vulnerabilities by treating input values as data parameters.

## Deliverables

1. **Modified Application**:
   - The application code was updated to use prepared statements, enhancing security against SQL injection attacks.

2. **Report**:
   - A detailed PDF report (`report.pdf`) describing the analysis, the vulnerabilities identified, the fixes implemented, and the validation results.

3. **Submission**:
   - The `cwk2.zip` file, generated using the `./gradlew submission` command, contains all necessary materials for submission.

## Conclusion

This project demonstrates the importance of secure coding practices, especially in handling user input and storing sensitive data. By implementing prepared statements and properly securing passwords, the application is now robust against SQL injection attacks, ensuring the protection of confidential patient data.

---
