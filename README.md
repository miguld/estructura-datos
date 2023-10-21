CREATE DATABASE GESTORCINEMA

USE GESTORCINEMA


CREATE TABLE USUARIO (
  ID_USUARIO SERIAL PRIMARY KEY,
  TIPODOCUMENTO VARCHAR(50),
  NUMERODOCUMENTO VARCHAR(50),
  NOMBRES VARCHAR(100),
  APELLIDOS VARCHAR(100),
  CORREOELECTRONICO VARCHAR(255),
  CONTRASEÑA VARCHAR(255)
);

 SELECT * FROM USUARIO;

CREATE TABLE PELICULA (
  ID_PELICULA SERIAL PRIMARY KEY,
  TITULO VARCHAR(100),
  GENERO VARCHAR(50),
  DIRECTOR VARCHAR(100),
  DURACION INT,
  CLASIFICACION VARCHAR(20),
  SINOPSIS TEXT
);
SELECT * FROM PELICULA;

CREATE TABLE RESERVACION (
  ID_RESERVACION SERIAL PRIMARY KEY,
  ID_USUARIO INT,
  ID_PELICULA INT,
  FECHA_RESERVACION TIMESTAMP,
  CANTIDAD_BOLETOS INT,
  SALA VARCHAR(50),
  TOTAL_PAGO NUMERIC(10, 2)
);
SELECT * FROM RESERVACION;

CREATE TABLE CARTELERA (
  ID_CARTELERA SERIAL PRIMARY KEY,
  ID_PELICULA INT,
  HORA_INICIO TIMESTAMP,
  SALA VARCHAR(50),
  FECHA DATE
);
SELECT * FROM CARTELERA;


INSERT INTO USUARIO (TIPODOCUMENTO, NUMERODOCUMENTO, NOMBRES, APELLIDOS, CORREOELECTRONICO, CONTRASEÑA)
VALUES
    ('Cedula', '12345678', 'Juan', 'Pérez', 'juan@email.com', 'password123'),
    ('Cédula', '98765432', 'María', 'Gómez', 'maria@email.com', 'securepwd456'),
    ('Cedula', '54321678', 'Luis', 'Martínez', 'luis@email.com', 'mysecurepwd'),
    ('Cedula', '87654321', 'Andrea', 'López', 'andrea@email.com', '1234abcd'),
    ('Cédula', '45678901', 'David', 'Torres', 'david@email.com', 'securepass'),
    ('Cedula', '98761234', 'Ana', 'Sánchez', 'ana@email.com', 'pwd9876'),
    ('Cedula', '23456789', 'Pedro', 'Rodríguez', 'pedro@email.com', 'passwd123'),
    ('Cédula', '34567890', 'Carla', 'González', 'carla@email.com', 'password456'),
    ('Cedula', '76543210', 'Santiago', 'Hernández', 'santiago@email.com', 'secure123'),
    ('Cedula', '56789012', 'Laura', 'Díaz', 'laura@email.com', 'abcd9876'),
    ('Cédula', '65432109', 'Javier', 'Peralta', 'javier@email.com', 'mypassword'),
    ('Cedula', '89012345', 'Isabella', 'Ramírez', 'isabella@email.com', 'securepwd1'),
    ('Cedula', '43210987', 'Diego', 'Luna', 'diego@email.com', 'd1234567'),
    ('Cédula', '21098765', 'Paula', 'Vargas', 'paula@email.com', 'password789'),
    ('Cedula', '12345678', 'Fernando', 'Martínez', 'fernando@email.com', 'pwd8901');

INSERT INTO PELICULA (TITULO, GENERO, DIRECTOR, DURACION, CLASIFICACION, SINOPSIS)
VALUES
    ('El Misterio de la Isla Perdida', 'Aventura', 'Alicia Johnson', 135, 'PG', 'Un grupo de exploradores se embarca en una emocionante aventura en una isla misteriosa.'),
    ('Locura en Las Vegas', 'Comedia', 'Martin Smith', 95, 'R', 'Dos amigos se despiertan en Las Vegas con resaca y sin recordar lo que sucedió la noche anterior.'),
    ('El Guardian de los Sueños', 'Fantasía', 'Elena Rodriguez', 120, 'PG-13', 'Un joven descubre un mundo de ensueño y magia donde debe salvar a su familia.'),
    ('Intriga en París', 'Suspenso', 'David Brown', 110, 'PG-13', 'Un detective se ve envuelto en una conspiración mortal en las calles de París.'),
    ('Amor en Roma', 'Romance', 'Sophia García', 100, 'PG', 'Dos desconocidos se cruzan en Roma y experimentan un amor inolvidable.');


INSERT INTO RESERVACION (ID_USUARIO, ID_PELICULA, FECHA_RESERVACION, CANTIDAD_BOLETOS, SALA, TOTAL_PAGO)
VALUES
    (1, 1, '2023-10-13 14:00:00', 2, 'Sala 1', 25.50),
    (2, 2, '2023-10-14 16:30:00', 3, 'Sala 2', 45.75),
    (3, 3, '2023-10-15 19:00:00', 1, 'Sala 3', 12.75),
    (4, 4, '2023-10-16 21:30:00', 4, 'Sala 1', 51.00),
    (5, 5, '2023-10-17 14:30:00', 2, 'Sala 2', 30.00),
    (6, 1, '2023-10-18 14:00:00', 2, 'Sala 1', 25.50),
    (7, 2, '2023-10-19 16:30:00', 3, 'Sala 2', 45.75),
    (8, 3, '2023-10-20 19:00:00', 1, 'Sala 3', 12.75),
    (9, 4, '2023-10-21 21:30:00', 4, 'Sala 1', 51.00),
    (10, 5, '2023-10-22 14:30:00', 2, 'Sala 2', 30.00),
    (11, 1, '2023-10-23 14:00:00', 2, 'Sala 1', 25.50),
    (12, 2, '2023-10-24 16:30:00', 3, 'Sala 2', 45.75),
    (13, 3, '2023-10-25 19:00:00', 1, 'Sala 3', 12.75),
    (14, 4, '2023-10-26 21:30:00', 4, 'Sala 1', 51.00),
    (15, 5, '2023-10-27 14:30:00', 2, 'Sala 2', 30.00);


DELETE FROM RESERVACIONES

INSERT INTO CARTELERA (ID_PELICULA, HORA_INICIO, SALA, FECHA)
VALUES
    (1, '2023-10-13 14:00:00', 'Sala 1', '2023-10-13'),
    (2, '2023-10-14 16:30:00', 'Sala 2', '2023-10-14'),
    (3, '2023-10-15 19:00:00', 'Sala 3', '2023-10-15'),
    (4, '2023-10-16 21:30:00', 'Sala 1', '2023-10-16'),
    (5, '2023-10-17 14:30:00', 'Sala 2', '2023-10-17'),
    (1, '2023-10-18 14:00:00', 'Sala 1', '2023-10-18'),
    (2, '2023-10-19 16:30:00', 'Sala 2', '2023-10-19'),
    (3, '2023-10-20 19:00:00', 'Sala 3', '2023-10-20'),
    (4, '2023-10-21 21:30:00', 'Sala 1', '2023-10-21'),
    (5, '2023-10-22 14:30:00', 'Sala 2', '2023-10-22'),
    (1, '2023-10-23 14:00:00', 'Sala 1', '2023-10-23'),
    (2, '2023-10-24 16:30:00', 'Sala 2', '2023-10-24'),
    (3, '2023-10-25 19:00:00', 'Sala 3', '2023-10-25'),
    (4, '2023-10-26 21:30:00', 'Sala 1', '2023-10-26'),
    (5, '2023-10-27 14:30:00', 'Sala 2', '2023-10-27');
