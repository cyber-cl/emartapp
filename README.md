# EMart - Microservices E-Commerce Application

EMart is a modern e-commerce application built using a microservices architecture. The application demonstrates best practices in developing, deploying, and managing distributed systems using containerization and orchestration technologies.

## Architecture Overview

EMart is composed of the following microservices:

- **Client**: Angular-based frontend application
- **API (Node.js)**: Main backend service for user management and product catalog
- **WebAPI (Java)**: Secondary backend service for book management
- **Nginx**: Web server and reverse proxy
- **MongoDB**: NoSQL database for product and user data
- **MySQL**: Relational database for book data

## Technology Stack

### Frontend
- Angular 12
- Bootstrap 4.6
- Font Awesome
- RxJS

### Backend
- Node.js Express API
- Java Spring Boot API
- MongoDB
- MySQL 8.0

### DevOps & Infrastructure
- Docker & Docker Compose
- Kubernetes
- Helm Charts
- Jenkins CI/CD Pipeline
- Nexus Repository

## Getting Started

### Prerequisites
- Docker and Docker Compose
- Node.js (for local development)
- Java JDK 11+ (for local development)
- Angular CLI (for local development)

### Running with Docker Compose

1. Clone the repository:
   ```
   git clone https://github.com/cyber-cl/emartapp.git
   cd emartapp
   ```

2. Start the application:
   ```
   docker-compose up -d
   ```

3. Access the application:
   - Frontend: http://localhost:4200
   - Node.js API: http://localhost:5000
   - Java API: http://localhost:9000
   - Nginx: http://localhost:80

### Development Setup

#### Frontend (Angular)
```
cd client
npm install
npm start
```

#### Node.js API
```
cd nodeapi
npm install
npm start
```

#### Java API
```
cd javaapi
./mvnw spring-boot:run
```

## CI/CD Pipeline

The project includes a Jenkins pipeline configuration that:

1. Builds Docker images for each microservice
2. Pushes images to a Nexus repository
3. Deploys to Kubernetes using Helm charts
4. Implements change-based deployment (only rebuilds services with changes)

## Kubernetes Deployment

The application can be deployed to Kubernetes using the provided Helm charts in the `kkartchart` directory.

```
helm upgrade kubekart kkartchart --install --namespace kart
```

## Project Structure

```
emartapp/
├── client/                # Angular frontend
├── nodeapi/               # Node.js API
│   ├── config/            # Configuration files
│   ├── models/            # MongoDB models
│   ├── routes/            # API routes
│   └── validation/        # Input validation
├── javaapi/               # Java Spring Boot API
│   └── src/               # Java source code
├── nginx/                 # Nginx configuration
├── kkartchart/            # Helm charts for Kubernetes
├── docker-compose.yaml    # Docker Compose configuration
└── Jenkinsfile            # Jenkins CI/CD pipeline
```

## Contributing

1. Fork the repository
2. Create a feature branch: `git checkout -b feature/your-feature-name`
3. Commit your changes: `git commit -am 'Add some feature'`
4. Push to the branch: `git push origin feature/your-feature-name`
5. Submit a pull request

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Acknowledgments

- Thanks to all contributors who have helped with the development of this project
- Special thanks to the open-source community for the tools and libraries used in this project