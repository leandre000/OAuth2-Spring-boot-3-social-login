# 🔒 Spring Boot 3 OAuth 2.0 Social Login

## 🌟 Overview
A lightweight **Spring Boot 3** application that implements **OAuth 2.0 social login** with Google, GitHub, and Facebook using Spring Security. This project provides a secure and seamless authentication experience, allowing users to log in with their social media accounts. Ideal for developers looking to integrate OAuth 2.0 into their Spring Boot applications. 🚀

## ✨ Features
- 🔐 OAuth 2.0 social login (Google, GitHub, Facebook)
- 🛡️ Secure user authentication with Spring Security
- 🌐 RESTful API for user information
- 📱 Simple, customizable frontend (optional)
- 🗄️ Database integration for user persistence

## 🛠️ Prerequisites
- ☕ Java 17 or later
- 📦 Maven
- 🗄️ MySQL (or another relational database)
- 🐳 Docker (optional)
- 🌍 Modern browser for testing

## 🔑 OAuth 2.0 Setup
Register your application with these providers to obtain **Client ID** and **Client Secret**:
- **Google**: [Google Cloud Console](https://console.cloud.google.com/) (Redirect URI: `http://localhost:8080/login/oauth2/code/google`)
- **GitHub**: [GitHub Settings](https://github.com/settings/apps) (Redirect URI: `http://localhost:8080/login/oauth2/code/github`)
- **Facebook**: [Facebook Developers](https://developers.facebook.com/) (Redirect URI: `http://localhost:8080/login/oauth2/code/facebook`)

## 🚀 Installation

### Backend (Spring Boot)
1. **Clone the Repository** 📂
   ```bash
   git clone https://github.com/yourusername/spring-boot-oauth2-social-login.git
   cd spring-boot-oauth2-social-login
   ```

2. **Configure Database & OAuth** 🗄️
   - Edit `src/main/resources/application.properties`:
     ```properties
     # Database Configuration
     spring.datasource.url=jdbc:mysql://localhost:3306/oauth2_db
     spring.datasource.username=your_username
     spring.datasource.password=your_password
     spring.jpa.hibernate.ddl-auto=update

     # OAuth 2.0 Configuration
     spring.security.oauth2.client.registration.google.client-id=your-google-client-id
     spring.security.oauth2.client.registration.google.client-secret=your-google-client-secret
     spring.security.oauth2.client.registration.github.client-id=your-github-client-id
     spring.security.oauth2.client.registration.github.client-secret=your-github-client-secret
     spring.security.oauth2.client.registration.facebook.client-id=your-facebook-client-id
     spring.security.oauth2.client.registration.facebook.client-secret=your-facebook-client-secret
     spring.security.oauth2.client.registration.facebook.scope=email,public_profile
     ```

3. **Build and Run** 🏃
   ```bash
   mvn clean install
   mvn spring-boot:run
   ```
   - The app runs on `http://localhost:8080`.


## 🎮 Usage
1. **Access the App** 🌐
   - Open `http://localhost:8080` in a browser.
   - Click a social login button (Google, GitHub, or Facebook) to authenticate 🔐.

2. **Key API Endpoints** 📡
   - **User Info**: `GET /api/users/me`
     - Returns authenticated user details (e.g., username, provider).
   - **Health Check**: `GET /actuator/health`

## 📂 Project Structure
```
spring-boot-oauth2-social-login/
├── src/
│   ├── main/
│   │   ├── java/com/example/oauth2/
│   │   │   ├── controller/     # REST controllers ⚙️
│   │   │   ├── service/        # Authentication logic 🛠️
│   │   │   ├── model/          # User entities 📋
│   │   │   ├── config/         # OAuth 2.0 & Security config 🔧
│   │   ├── resources/
│   │   │   ├── application.properties  # App configuration ⚙️
│   ├── pom.xml                 # Maven dependencies 📦
├── README.md                   # This file 📄
```

## 🤝 Contributing
Contributions are welcome! To contribute:
1. 🍴 Fork the repository.
2. 🌿 Create a branch: `git checkout -b feature/your-feature`.
3. ✍️ Commit changes: `git commit -m "Add your feature"`.
4. 🚀 Push branch: `git push origin feature/your-feature`.
5. 📬 Open a pull request.


🌍 Securely connect with OAuth 2.0! Happy coding! 🚀
