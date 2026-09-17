# EC2-UserData
#!/bin/bash

dnf update -y
dnf install -y httpd

systemctl enable httpd
systemctl start httpd

cat > /var/www/html/index.html <<EOF
<!DOCTYPE html>
<html>
<head>
    <title>AWS EC2 User Data</title>
</head>
<body>
    <h1>Welcome to My AWS Web Server</h1>
    <h2>Apache Installed Using EC2 User Data</h2>
    <p>User Data automatically installed and started Apache.</p>
</body>
</html>
EOF
