# SenacBancodeDadosReview

-- CRIANDO O BANCO DE DADOS;
CREATE DATABASE gravadora;

-- ATIVAR O BANCO DE DADOS;
USE gravadora;

-- CRIANDO TABELA CANTOR (ENTIDADE FORTE);
CREATE TABLE cantor (
id_cantor   INT PRIMARY KEY ,
nome_cantor VARCHAR(100),
biografia   VARCHAR(500)
);

-- CRIANDO TABELA CD (ENTIDADE FORTE);
CREATE TABLE cd (
id_cd 		INT PRIMARY KEY,
nome 		VARCHAR(50),
gravadora   VARCHAR(100)
);

-- CRIANDO TABELA MUSICA;
CREATE TABLE musica (
id_musica INT PRIMARY KEY,
id_cantor INT,
id_cd     INT,
titulo    VARCHAR(50) NOT NULL,
tempo     INT NOT NULL,
genero    VARCHAR(50) NOT NULL,

-- CONSTRAINT (RESTRIÇÕES);
foreign key (id_cantor) references cantor (id_cantor),
foreign key (id_cd) references cd (id_cd)
);

-- INSERINDO DADOS NA TABELA CANTOR
INSERT INTO cantor (id_cantor, nome_cantor, biografia) VALUES
(1, 'Ebony', 'Cantora brasileira de rap e R&B, conhecida por letras fortes e representatividade.'),
(2, 'Amy Winehouse', 'Cantora e compositora britânica, ícone do soul e jazz contemporâneo.'),
(3, 'Djavan', 'Cantor e compositor brasileiro, referência da MPB.');

-- INSERINDO DADOS NA TABELA CD
INSERT INTO cd (id_cd, nome, gravadora) VALUES
(1, 'Terapia', 'Independente'),
(2, 'Back to Black', 'Island Records'),
(3, 'Luz', 'Sony Music');

-- INSERINDO DADOS NA TABELA MUSICA
INSERT INTO musica (id_musica, id_cantor, id_cd, titulo, tempo, genero) VALUES
(1, 1, 1, 'Pensamentos Intrusivos', 185, 'Rap'),
(2, 2, 2, 'Back to Black', 240, 'Soul'),
(3, 3, 3, 'Samurai', 210, 'MPB');

-- CONSULTA SIMPLES
SELECT * FROM cantor;



