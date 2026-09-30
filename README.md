# 🏦 Banking Application

A simple banking web app built with **Spring Boot**, **Spring Security**, **Thymeleaf** and **MySQL**. Users can register, log in, deposit, withdraw, transfer money to other users, and view their transaction history.

## ✨ Features

- Registration and login (BCrypt-encrypted passwords)
- Dashboard with current balance
- Deposit, withdraw (with insufficient-funds check) and transfer to another user
- Transaction history

## 🛠️ Tech Stack

Java 17 · Spring Boot 3.3.3 · Spring Security · Spring Data JPA · Thymeleaf · MySQL 8 · Maven

## ✅ Prerequisites

- JDK 17+
- MySQL 8+
- Git
- IntelliJ IDEA (Community or Ultimate)

## 🚀 Setup

**1. Clone the repo**

```bash
git clone https://github.com/<your-username>/<your-repo-name>.git
```

**2. Create the database**

```sql
CREATE DATABASE bankappdb;
```

Tables are created automatically on the first run.

**3. Open the project in IntelliJ IDEA**

- Go to **File → Open** and select the cloned project folder.
- Wait for IntelliJ to import the Maven dependencies (progress is shown at the bottom right).
- Make sure the project SDK is set to **JDK 17** (**File → Project Structure → Project → SDK**).

**4. Configure credentials**

Edit `src/main/resources/application.properties`:

```properties
spring.datasource.url=jdbc:mysql://localhost:3306/bankappdb
spring.datasource.username=root
spring.datasource.password=YOUR_MYSQL_PASSWORD
```

> ⚠️ Never commit your real password to GitHub.

**5. Run the app**

- Open `src/main/java/com/example/bankapp/BankappApplication.java`.
- Click the green ▶ **Run** icon next to the `main` method (or press `Shift + F10`).

**6. Open in browser**

```
http://localhost:8080
```

## 📖 Usage

1. Register at `/register` (starting balance is 0).
2. Log in at `/login`.
3. Use the dashboard to deposit, withdraw or transfer money.
4. Open `/transactions` to see your history.

> To test transfers, register two users (e.g. one normal and one incognito window).

## 🩺 Troubleshooting

| Problem | Fix |
| ------- | --- |
| `Access denied for user` | Check MySQL username/password in `application.properties` |
| `Unknown database 'bankappdb'` | Run `CREATE DATABASE bankappdb;` |
| `Communications link failure` | Start MySQL (port 3306) |
| `Port 8080 already in use` | Add `server.port=9090` to `application.properties` |
| Red/unresolved imports in IntelliJ | Right-click `pom.xml` → **Maven → Reload project** |

## ⚠️ Note

This is a learning project, not production-ready (CSRF disabled, no `@Transactional`, no amount validation).
