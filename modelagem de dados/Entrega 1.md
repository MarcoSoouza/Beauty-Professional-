CREATE DATABASE CursoBeleza;
USE CursoBeleza;

CREATE TABLE Alunos (
    aluno_id INT PRIMARY KEY AUTO_INCREMENT,
    nome VARCHAR(100),
    data_nascimento DATE,
    endereco VARCHAR(255),
    telefone VARCHAR(15)
);

CREATE TABLE Instrutores (
    instrutor_id INT PRIMARY KEY AUTO_INCREMENT,
    nome VARCHAR(100),
    especialidade VARCHAR(100),
    telefone VARCHAR(15)
);

CREATE TABLE Cursos (
    curso_id INT PRIMARY KEY AUTO_INCREMENT,
    nome VARCHAR(100),
    duracao INT,
    preco DECIMAL(10, 2),
    instrutor_id INT,
    FOREIGN KEY (instrutor_id) REFERENCES Instrutores(instrutor_id)
);

CREATE TABLE Matriculas (
    matricula_id INT PRIMARY KEY AUTO_INCREMENT,
    aluno_id INT,
    curso_id INT,
    data_matricula DATE,
    status VARCHAR(50),
    FOREIGN KEY (aluno_id) REFERENCES Alunos(aluno_id),
    FOREIGN KEY (curso_id) REFERENCES Cursos(curso_id)
);
