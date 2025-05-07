BASE EN MYSQL 


-- Crear la base de datos
CREATE DATABASE CentroMedicoDB;
USE CentroMedicoDB;

-- Tabla de centros médicos
CREATE TABLE CentrosMedicos (
    CentroID INT PRIMARY KEY AUTO_INCREMENT,
    Nombre VARCHAR(100) NOT NULL,
    Ciudad VARCHAR(100) NOT NULL,
    Direccion VARCHAR(200),
    Telefono VARCHAR(20)
);

-- Tabla de especialidades
CREATE TABLE Especialidades (
    EspecialidadID INT PRIMARY KEY AUTO_INCREMENT,
    Nombre VARCHAR(100) NOT NULL,
    Descripcion VARCHAR(255)
);

-- Tabla de médicos (debe ir antes por las claves foráneas)
CREATE TABLE Medicos (
    MedicoID INT PRIMARY KEY AUTO_INCREMENT,
    Nombre VARCHAR(100) NOT NULL,
    Apellido VARCHAR(100) NOT NULL,
    EspecialidadID INT NOT NULL,
    CentroID INT NOT NULL,
    Email VARCHAR(100),
    Telefono VARCHAR(20),
    FOREIGN KEY (EspecialidadID) REFERENCES Especialidades(EspecialidadID),
    FOREIGN KEY (CentroID) REFERENCES CentrosMedicos(CentroID)
);

-- Tabla de asignación de especialidades
CREATE TABLE AsignacionEspecialidades (
    AsignacionID INT PRIMARY KEY AUTO_INCREMENT,
    MedicoID INT NOT NULL,
    EspecialidadID INT NOT NULL,
    FOREIGN KEY (MedicoID) REFERENCES Medicos(MedicoID),
    FOREIGN KEY (EspecialidadID) REFERENCES Especialidades(EspecialidadID)
);

-- Tabla de empleados
CREATE TABLE Empleados (
    EmpleadoID INT PRIMARY KEY AUTO_INCREMENT,
    Nombre VARCHAR(100) NOT NULL,
    Apellido VARCHAR(100) NOT NULL,
    Cargo VARCHAR(100),
    Email VARCHAR(100),
    Telefono VARCHAR(20)
);

-- Tabla de clientes
CREATE TABLE Clientes (
    ClienteID INT PRIMARY KEY AUTO_INCREMENT,
    Nombre VARCHAR(100) NOT NULL,
    Apellido VARCHAR(100) NOT NULL,
    Correo VARCHAR(100),
    Telefono VARCHAR(20)
);

-- Tabla de consultas
CREATE TABLE Consultas (
    ConsultaID INT PRIMARY KEY AUTO_INCREMENT,
    MedicoID INT NOT NULL,
    ClienteID INT NOT NULL,
    FechaConsulta DATETIME NOT NULL,
    Diagnostico VARCHAR(255),
    Tratamiento VARCHAR(255),
    FOREIGN KEY (MedicoID) REFERENCES Medicos(MedicoID),
    FOREIGN KEY (ClienteID) REFERENCES Clientes(ClienteID)
);






BASE EN MYSQL 


-- Crear la base de datos
CREATE DATABASE CentroMedicoDB;
USE CentroMedicoDB;

-- Tabla de centros médicos
CREATE TABLE CentrosMedicos (
    CentroID INT PRIMARY KEY AUTO_INCREMENT,
    Nombre VARCHAR(100) NOT NULL,
    Ciudad VARCHAR(100) NOT NULL,
    Direccion VARCHAR(200),
    Telefono VARCHAR(20)
);

-- Tabla de especialidades
CREATE TABLE Especialidades (
    EspecialidadID INT PRIMARY KEY AUTO_INCREMENT,
    Nombre VARCHAR(100) NOT NULL,
    Descripcion VARCHAR(255)
);

-- Tabla de médicos (debe ir antes por las claves foráneas)
CREATE TABLE Medicos (
    MedicoID INT PRIMARY KEY AUTO_INCREMENT,
    Nombre VARCHAR(100) NOT NULL,
    Apellido VARCHAR(100) NOT NULL,
    EspecialidadID INT NOT NULL,
    CentroID INT NOT NULL,
    Email VARCHAR(100),
    Telefono VARCHAR(20),
    FOREIGN KEY (EspecialidadID) REFERENCES Especialidades(EspecialidadID),
    FOREIGN KEY (CentroID) REFERENCES CentrosMedicos(CentroID)
);

-- Tabla de asignación de especialidades
CREATE TABLE AsignacionEspecialidades (
    AsignacionID INT PRIMARY KEY AUTO_INCREMENT,
    MedicoID INT NOT NULL,
    EspecialidadID INT NOT NULL,
    FOREIGN KEY (MedicoID) REFERENCES Medicos(MedicoID),
    FOREIGN KEY (EspecialidadID) REFERENCES Especialidades(EspecialidadID)
);

-- Tabla de empleados
CREATE TABLE Empleados (
    EmpleadoID INT PRIMARY KEY AUTO_INCREMENT,
    Nombre VARCHAR(100) NOT NULL,
    Apellido VARCHAR(100) NOT NULL,
    Cargo VARCHAR(100),
    Email VARCHAR(100),
    Telefono VARCHAR(20)
);

-- Tabla de clientes
CREATE TABLE Clientes (
    ClienteID INT PRIMARY KEY AUTO_INCREMENT,
    Nombre VARCHAR(100) NOT NULL,
    Apellido VARCHAR(100) NOT NULL,
    Correo VARCHAR(100),
    Telefono VARCHAR(20)
);

-- Tabla de consultas
CREATE TABLE Consultas (
    ConsultaID INT PRIMARY KEY AUTO_INCREMENT,
    MedicoID INT NOT NULL,
    ClienteID INT NOT NULL,
    FechaConsulta DATETIME NOT NULL,
    Diagnostico VARCHAR(255),
    Tratamiento VARCHAR(255),
    FOREIGN KEY (MedicoID) REFERENCES Medicos(MedicoID),
    FOREIGN KEY (ClienteID) REFERENCES Clientes(ClienteID)
);






