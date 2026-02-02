e-Book Edwards A. - Let's Go - Learn to Build Professional Web App 2025.pdf

Continue Page. 247

password mysql = root


CREATE TABLE sessions (
    token CHAR(43) PRIMARY KEY,
    data BLOB NOT NULL,
    expiry TIMESTAMP(6) NOT NULL
);
CREATE INDEX sessions_expiry_idx ON sessions (expiry);