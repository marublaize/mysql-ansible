# MySQL Ansible Playbook

This Ansible project automates the deployment and configuration of MySQL on an Ubuntu server. It also includes the creation of a test database for verification.

## Table of Contents

- [MySQL Ansible Playbook](#mysql-ansible-playbook)
  - [Table of Contents](#table-of-contents)
  - [Project Structure](#project-structure)
  - [Prerequisites](#prerequisites)
  - [Usage](#usage)
  - [Customization](#customization)
    - [MySQL Configuration](#mysql-configuration)
  - [Contributing](#contributing)
  - [License](#license)

## Project Structure

The project has the following structure:

```bash
mysql-ansible/
│
├── ansible.cfg
├── inventory.ini
├── playbook.yml
├── roles/
│   ├── common/
│   │   ├── tasks/
│   │   │   └── main.yml
│   │   └── templates/
│   │       └── my.cnf.j2
│   ├── mysql/
│   │   ├── handlers/
│   │   │   └── main.yml
│   │   └── tasks/
│   │       └── main.yml
│   ├── test_db/
│   │   ├── handlers/
│   │   │   └── main.yml
│   │   ├── tasks/
│   │   │   └── main.yml
│   │   └── templates/
│   │       └── test_db.sql.j2
└── README.md
```

## Prerequisites

Before using this playbook, ensure that you have the following prerequisites:

1. An Ubuntu server to provision.
2. Ansible installed on your local machine.

## Usage

1. Clone this repository to your local machine:

   ```bash
   git clone https://github.com/marublaize/mysql-ansible.git
   ```

2. Modify the `inventory.ini` file to specify your target server(s).

3. Set the following environment variables with your desired configurations:

    - `MYSQL_ROOT_PASSWORD`: The root password for MySQL.
    - `MYSQL_USER`: The MySQL user for the test database.
    - `MYSQL_PASSWORD`: The password for the MySQL user.
    - `TEST_DB_NAME`: The name of the test database.

4. Run the playbook using the following command:

   ```bash
   ansible-playbook playbook.yml -i inventory.ini
   ```

## Customization

### MySQL Configuration

You can customize MySQL configuration by editing the `roles/common/templates/my.cnf.j2` template file. Adjust MySQL settings to fit your requirements.

## Contributing

Feel free to contribute to this project by opening issues or submitting pull requests. Your contributions are greatly appreciated.

## License

This project is licensed under the [MIT License](LICENSE).
