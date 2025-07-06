# Spring Boot Online Banking Rest API

This project is a Java Spring Boot Rest API project. MySql is used as the database. JWT, sessions, and interceptors are employed for authentication and authorization. Tests have been conducted using Postman. Users can register and log in to the system. They can open new bank accounts, deposit and withdraw money, transfer money between accounts, and make payments. The project is developed in compliance with code refactoring, design patterns, and SOLID principles

## Features

- It includes Authentication and Authorization mechanisms.
- Email control and verification mechanisms are also available.
- Rest API
- It adheres to SOLID principles and design patterns.
- Tüm platformlara destek

## API Usage

#### Dashboard Get Accounts

```http
  GET /app/dashboard
```

| Headers         | Tip                       | Açıklama                     |
| :-------------- | :------------------------ | :--------------------------- |
| `Authorization` | `Bearer:{{access_token}}` | **Required** . Your API key. |

#### Get Payment History

```http
  GET /app/payment_history
```

| Headers         | Tip                       | Açıklama                     |
| :-------------- | :------------------------ | :--------------------------- |
| `Authorization` | `Bearer:{{access_token}}` | **Required** . Your API key. |

#### Get Transaction History

```http
  GET /app/transaction_history
```

| Headers         | Tip                       | Açıklama                     |
| :-------------- | :------------------------ | :--------------------------- |
| `Authorization` | `Bearer:{{access_token}}` | **Required** . Your API key. |

#### Post Create Account

```http
  POST /account/create_account
```

| Body           | Type     | Description  |
| :------------- | :------- | :----------- |
| `account_name` | `string` | **Required** |
| `account_type` | `string` | **Required** |

| Headers         | Type           | Description                  |
| :-------------- | :------------- | :--------------------------- |
| `Authorization` | `access_token` | **Required** . Your API key. |

#### Post Deposit Transaction

```http
  POST /transact/deposit
```

| Body             | Type     | Description  |
| :--------------- | :------- | :----------- |
| `deposit_amount` | `string` | **Required** |
| `account_id`     | `int`    | **Required** |

| Headers         | Type           | Description                  |
| :-------------- | :------------- | :--------------------------- |
| `Authorization` | `access_token` | **Required** . Your API key. |

#### POST Transfer Transaction

```http
  POST /transact/transfer
```

| Body            | Type     | Description  |
| :-------------- | :------- | :----------- |
| `sourceAccount` | `string` | **Required** |
| `targetAccount` | `string` | **Required** |
| `amount`        | `string` | **Required** |

| Headers         | Type           | Description                  |
| :-------------- | :------------- | :--------------------------- |
| `Authorization` | `access_token` | **Required** . Your API key. |

#### Post Withdraw Transaction

```http
  POST /transact/withdraw
```

| Headers         | Type           | Description                  |
| :-------------- | :------------- | :--------------------------- |
| `Authorization` | `access_token` | **Required** . Your API key. |

| Body                | Type     | Description  |
| :------------------ | :------- | :----------- |
| `withdrawal_amount` | `string` | **Required** |
| `account_id`        | `string` | **Required** |

#### Post Payment Transaction

```http
  POST /transact/payment
```

| Headers         | Type           | Description                  |
| :-------------- | :------------- | :--------------------------- |
| `Authorization` | `access_token` | **Required**. Your API key.. |

| Body             | Type     | Description  |
| :--------------- | :------- | :----------- |
| `beneficiary`    | `string` | **Required** |
| `account_number` | `string` | **Required** |
| `account_id`     | `string` | **Required** |
| `reference`      | `string` | **Required** |
| `payment_amount` | `string` | **Required** |

#### Get Verify Account

```http
  GET /verify?token={token}&code={code}
```

| Query Params | Value   | Description                          |
| :----------- | :------ | :----------------------------------- |
| `token`      | `token` | **Required** . Token from your email |
| `code`       | `code`  | **Required** . Code from your email  |

#### Post Register User

```http
  POST register?confirm_password=1234
```

| Body         | Type     | Description                  |
| :----------- | :------- | :--------------------------- |
| `first_name` | `string` | **Required**. User email.    |
| `last_name`  | `string` | **Required**. User email.    |
| `email`      | `string` | **Required**. User email.    |
| `password`   | `string` | **Required**. User password. |

#### Post Register Login

```http
  POST /login
```

| Body       | Type     | Description                   |
| :--------- | :------- | :---------------------------- |
| `email`    | `string` | **Required** . User email.    |
| `password` | `string` | **Required** . User password. |

#### Get Transaction History

```http
  GET /logout
```

| Headers         | Type           | Description                 |
| :-------------- | :------------- | :-------------------------- |
| `Authorization` | `access_token` | **Required**. Your API key. |

## Email Configurations

I used ThunderBird for email configurations. I created email addresses on Local Host through Hmail Server.

## Database Structure

![Uygulama Ekran Görüntüsü](images/databasestructure.png)

## Distribution

1- Clone the project to your local machine.
2- Build and run the application using your preferred Java Development environment.

Start for Project

```bash
  maven build
```

```bash
  maven run
```

## application.properties

To run the project, update the following information in your application.properties file.

`spring.datasource.url`

`spring.datasource.username`

`spring.datasource.password`

## Tests

Postman

![Uygulama Ekran Görüntüsü](images/Screenshot_1.png)

## Technologies

**Framework:** Spring Boot

**Technologies:** MySql, Javax Servlet, Tomcat, Spring Security Crypto, Json Web Token, Interceptors

## Extracted Lessons

Java Spring usage, Enterprise architecture, Database architecture, Session architecture, JWT architecture, Interceptor usage, Exception Handling mechanism, Project configuration, and more.

---

# Online Banking Full Stack Project Frontend

This is a full-stack project. At this point, we will focus on the frontend.

The application Frontend project prepared for the Online Banking Rest API. React and Redux are used in the frontend of the application. The project is a single-page application, and I have fully leveraged the benefits provided by Redux. Every component you will see in the project is connected to the Redux Store. When the state of one component changes, all components that need to update their state automatically do so, providing users with real-time information.

Users can register, log in, view their account history, open new accounts, make transfers between accounts, deposit money, withdraw money, and make payments. Additionally, a self-updating chart has been prepared for users to view their account flows. In short, the components are constantly in communication with the backend, ensuring seamless interaction.

## Features

- React and Redux
- Single Page Application
- Material UI

## Distribution

1- Clone the project to your local machine.
2- Build and run the application using your preferred Java Script environment.

Start for Project

```terminal
  npm install
```

```bash
  npm run start
```

## Technologies

**Language:** Java Script

**Technologies:** - React, Redux, Router Dom

- Redux Thunk

## Extracted Lessons

React, Redux, Thunk usage. JavaScript experiences. Communication with backend. CORS Policy Setting. MUI usage. Frontend web development. JWT and cookies.
