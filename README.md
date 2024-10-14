# WordPress Docker Starter Project

A streamlined Docker-based development environment for WordPress, featuring MySQL. This setup provides a quick and efficient way to start WordPress projects with minimal configuration.

## Table of Contents

- [Features](#features)
- [Prerequisites](#prerequisites)
- [Quick Start](#quick-start)
- [Project Structure](#project-structure)
- [Configuration](#configuration)
- [Usage](#usage)
- [Database Access](#database-access)
- [Customization](#customization)
- [Troubleshooting](#troubleshooting)
- [Contributing](#contributing)
- [License](#license)

## Features

- Latest WordPress version
- MySQL 8.0
- Custom container names for easy identification
- Environment variable support for flexible configuration
- Persistent data storage for WordPress files and MySQL database
- Easy-to-use Docker Compose setup

## Prerequisites

- Docker
- Docker Compose
- Git (optional, for cloning the repository)

## Quick Start

1. Clone this repository:
2. Create a `.env` file in the project root and add your environment variables:

ex:

APP_NAME=myapp

DB_USER=wordpress

DB_PASSWORD=your_password

DB_ROOT_PASSWORD=your_root_password



3. Start the containers:

docker-compose up -d


4. Access WordPress at `http://localhost:8000`

## Project Structure

wordpress-docker-starter/
├── docker-compose.yml
├── .env
├── .gitignore
├── README.md
├── wordpress/
└── mysql/


- `docker-compose.yml`: Defines the services (WordPress, MySQL)
- `.env`: Contains environment variables for configuration
- `.gitignore`: Specifies intentionally untracked files to ignore
- `wordpress/`: WordPress files (mapped to container)
- `mysql/`: MySQL data files (mapped to container)

## Configuration

The project uses environment variables for configuration. These are defined in the `.env` file:

- `APP_NAME`: The prefix for your container names and database name
- `DB_USER`: MySQL database user for WordPress
- `DB_PASSWORD`: Password for the database user
- `DB_ROOT_PASSWORD`: Root password for MySQL

## Usage

### Starting the Environment

docker-compose up -d

### Stopping the Environment

docker-compose down

### Viewing Logs

docker-compose logs -f


## Database Access

To access the MySQL database via command line:

docker exec -it ${APP_NAME}-mysql mysql -u ${DB_USER} -p${DB_PASSWORD}

Replace `${APP_NAME}`, `${DB_USER}`, and `${DB_PASSWORD}` with your actual values.

Common MySQL commands:
- Show databases: `SHOW DATABASES;`
- Use a database: `USE database_name;`
- Show tables: `SHOW TABLES;`
- Describe table structure: `DESCRIBE table_name;`

## Customization

- Modify `docker-compose.yml` to add or change services
- Update environment variables in `.env` file to change database credentials or application name
- Add custom themes or plugins to the `wordpress/wp-content/` directory


