# Step-by-Step-guide-to-Installing-MySQL-on-Ubuntu-20.04
Here's a step-by-step guide to installing MySQL on Ubuntu 20.04:


Sure! Here's a step-by-step guide to installing MySQL on Ubuntu 20.04:

### Step 1: Update Package Lists

Before installing any new packages, it's a good idea to update the package lists to ensure you're getting the latest versions.

```bash
sudo apt update
```

### Step 2: Install MySQL Server

You can install the MySQL server package directly from the Ubuntu repositories using the following command:

```bash
sudo apt install mysql-server
```

During the installation, you'll be prompted to set a root password for the MySQL server. Enter a strong password and then confirm it.

### Step 3: Configure MySQL Security

MySQL provides a script to secure the installation. Run the following command and follow the prompts to secure your MySQL installation:

```bash
sudo mysql_secure_installation
```

This script will prompt you to:

- Enter the MySQL root password you set earlier.
- Choose whether to enforce password policy validation (strong password).
- Remove anonymous users.
- Disallow root login remotely.
- Remove the test database.
- Reload privilege tables to apply the changes.

### Step 4: Verify MySQL Installation

After the installation is complete, you can verify that MySQL is running correctly by checking its status:

```bash
sudo systemctl status mysql
```

If MySQL is running properly, you should see output indicating that the service is active and running.

### Step 5: Access MySQL

To access the MySQL shell as the root user, you can use the following command:

```bash
sudo mysql -u root -p
```

Enter the root password you set during installation when prompted.

### Step 6: Create Additional MySQL Users (Optional)

While you're logged into MySQL, you might want to create additional users for specific databases or applications. Here's a basic example of how to create a new user and grant them privileges:

```sql
CREATE USER 'username'@'localhost' IDENTIFIED BY 'password';
GRANT ALL PRIVILEGES ON *.* TO 'username'@'localhost' WITH GRANT OPTION;
FLUSH PRIVILEGES;
```

Replace `'username'` and `'password'` with your desired username and password.

### Step 7: Exit MySQL

Once you're done working in the MySQL shell, you can exit by typing:

```sql
exit;
```

### Conclusion

You've now installed MySQL on your Ubuntu 20.04 server and secured it using best practices. MySQL is ready to use for your databases and applications.
