# spring-boot-oath2-github-basic

A minimal Spring Boot application demonstrating **GitHub OAuth2 login** using:

- **Spring Web** – REST/MVC web layer
- **Spring Security OAuth2 Client** – GitHub social login
- **Thymeleaf** – server-side HTML templates with Spring Security dialect (`sec:authorize`)

## Getting Started

### 1. Register a GitHub OAuth App

Go to **GitHub → Settings → Developer settings → OAuth Apps → New OAuth App** and fill in:

| Field | Value |
|---|---|
| Homepage URL | `http://localhost:8080` |
| Authorization callback URL | `http://localhost:8080/login/oauth2/code/github` |

Copy the **Client ID** and **Client Secret**.

### 2. Configure credentials

Set the credentials as environment variables before running:

```bash
export GITHUB_CLIENT_ID=<your-client-id>
export GITHUB_CLIENT_SECRET=<your-client-secret>
```

Or edit `src/main/resources/application.yml` directly.

### 3. Run

```bash
./mvnw spring-boot:run
```

Open [http://localhost:8080](http://localhost:8080) in your browser.

## Project Structure

```
src/
├── main/
│   ├── java/com/example/oauth2github/
│   │   ├── Oauth2GithubApplication.java   # Spring Boot entry point
│   │   ├── SecurityConfig.java            # OAuth2 / Security configuration
│   │   └── HomeController.java            # Routes: / and /user
│   └── resources/
│       ├── application.yml                # App configuration
│       └── templates/
│           ├── index.html                 # Public home page
│           └── user.html                  # Authenticated user profile
└── test/
    └── java/com/example/oauth2github/
        └── Oauth2GithubApplicationTests.java
```
