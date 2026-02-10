e-Book Edwards A. - Let's Go - Learn to Build Professional Web App 2025.pdf

Continue Page. 377 ต่อ Testing the snippetView handler

password mysql = root


CREATE TABLE sessions (
    token CHAR(43) PRIMARY KEY,
    data BLOB NOT NULL,
    expiry TIMESTAMP(6) NOT NULL
);
CREATE INDEX sessions_expiry_idx ON sessions (expiry);


Page 253 สั่งสร้าง  TLS
mkdir tls
go run "C:\Program Files\Go\src\crypto\tls\generate_cert.go" --rsa-bits=2048 --host=localhost


Page 277
CREATE TABLE users (
id INTEGER NOT NULL PRIMARY KEY AUTO_INCREMENT,
name VARCHAR(255) NOT NULL,
email VARCHAR(255) NOT NULL,
hashed_password CHAR(60) NOT NULL,
created DATETIME NOT NULL
);
ALTER TABLE users ADD CONSTRAINT users_uc_email UNIQUE (email);


คำสั่งสร้าง Exe ไว้ใช้งาน
# 1. Build binary ไปที่ C:\temp
cd C:\temp
go build -o web.exe ..\cmd\web\

# 2. Copy TLS certificates
สร้าง folder tls ไว้ใน folder temp จากนั้น copy cert.pem กับ key.pem มาไว้

# 3. รัน binary
web.exe


########
git rm -r --cached tls/     # untrack ครั้งเดียว
git add .gitignore
git commit -m "Ignore tls"
git push                    # ครั้งเดียว