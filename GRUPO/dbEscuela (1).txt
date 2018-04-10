create database EscuelaPaulo
go

use EscuelaPaulo
go 

CREATE TABLE alumnos (
  id_alumno int  NOT NULL ,
  nombre varchar(255) NOT NULL ,
  edad int  NOT NULL ,
  curso_actual int  NOT NULL ,
  PRIMARY KEY  (id_alumno)
) 


INSERT INTO alumnos VALUES (1, 'Luis Perez', 10, 2);
INSERT INTO alumnos VALUES (2, 'Juan Lopez', 11, 3);
INSERT INTO alumnos VALUES (3, 'Ana Gonzalez', 10, 3);
INSERT INTO alumnos VALUES (4, 'Laura Sanchez', 12, 3);
INSERT INTO alumnos VALUES (5, 'Antonio Ruiz', 12, 3);
INSERT INTO alumnos VALUES (6, 'Pedro Jimenez', 10, 2);

-- --------------------------------------------------------

CREATE TABLE asignaturas (
  id_asignatura int  NOT NULL ,
  nombre varchar(255) NOT NULL ,
  id_aula int  NOT NULL ,
  PRIMARY KEY  (id_asignatura)
) 

INSERT INTO asignaturas VALUES (1, 'Historia', 1);
INSERT INTO asignaturas VALUES (2, 'Biología', 1);
INSERT INTO asignaturas VALUES (3, 'Matemáticas', 4);

-- --------------------------------------------------------

CREATE TABLE aulas (
  id_aula int  NOT NULL ,
  nombre varchar(255) NOT NULL ,
  PRIMARY KEY  (id_aula)
) 

INSERT INTO aulas VALUES (1, '1A');
INSERT INTO aulas VALUES (2, '1B');
INSERT INTO aulas VALUES (3, '2A');
INSERT INTO aulas VALUES (4, '2B');

-- --------------------------------------------------------

CREATE TABLE horarios (
  id_horario int  NOT NULL ,
  hora_inicio time NOT NULL ,
  hora_fin time NOT NULL ,
  dia varchar(15) NOT NULL,
  id_asignatura int  NOT NULL ,
  PRIMARY KEY  (id_horario)
) 

INSERT INTO horarios VALUES (1, '08:00:00', '10:00:00', 'lunes', 1);
INSERT INTO horarios VALUES (2, '10:00:00', '12:00:00', 'lunes', 2);
INSERT INTO horarios VALUES (3, '12:00:00', '14:00:00', 'lunes', 3);
INSERT INTO horarios VALUES (4, '08:00:00', '12:00:00', 'martes', 1);
INSERT INTO horarios VALUES (5, '12:00:00', '14:00:00', 'martes', 2);
INSERT INTO horarios VALUES (6, '10:00:00', '12:00:00', 'miercoles', 3);
INSERT INTO horarios VALUES (7, '12:00:00', '14:00:00', 'miercoles', 1);
INSERT INTO horarios VALUES (8, '08:00:00', '10:00:00', 'jueves', 2);
INSERT INTO horarios VALUES (9, '10:00:00', '12:00:00', 'jueves', 3);
INSERT INTO horarios VALUES (10, '12:00:00', '14:00:00', 'jueves', 1);
INSERT INTO horarios VALUES (11, '08:00:00', '12:00:00', 'viernes', 2);

-- --------------------------------------------------------

CREATE TABLE listas (
  id_lista int  NOT NULL ,
  id_profesor int  NOT NULL ,
  id_alumno int  NOT NULL ,
  id_asignatura int  NOT NULL ,
  PRIMARY KEY  (id_lista)
) 

INSERT INTO listas VALUES (1, 1, 1, 1);
INSERT INTO listas VALUES (2, 1, 2, 1);
INSERT INTO listas VALUES (3, 1, 3, 1);
INSERT INTO listas VALUES (4, 1, 1, 2);
INSERT INTO listas VALUES (5, 1, 2, 2);
INSERT INTO listas VALUES (6, 1, 3, 2);
INSERT INTO listas VALUES (7, 2, 4, 3);
INSERT INTO listas VALUES (8, 2, 5, 3);
INSERT INTO listas VALUES (9, 2, 6, 3);

-- --------------------------------------------------------

CREATE TABLE profesores (
  id_profesor int  NOT NULL ,
  nombre varchar(255) NOT NULL ,
  PRIMARY KEY  (id_profesor)
)

INSERT INTO profesores VALUES (1, 'Roberto Juarez');
INSERT INTO profesores VALUES (2, 'Marcela Herrera');