# challenge.resolvido

--Banco de dados SQL.
-->Olá!!! Estou fazendo do modo em que aprendi
--até o momento.Estou usando Oracle SQL Developer
-->Irei começar do zero

DROP TABLE ATENDENTES CASCADE CONSTRAINTS;
DROP TABLE INCIDENTE  CASCADE CONSTRAINTS;
DROP TABLE CLIENTES   CASCADE CONSTRAINTS;

CREATE TABLE ATENDENTES (
            ID_ATENDENTES    NUMBER(11) NOT NULL,
            NOME             VARCHAR2(64)
            );
            
CREATE TABLE INCIDENTE (
            ID_INCIDENTE     NUMBER(11) NOT NULL,
            ATENDENTE        NUMBER(11) NOT NULL,
            CLIENTE          NUMBER(11) NOT NULL ,
            DESCRIÇÃO        VARCHAR2(512) DEFAULT NULL,
            STATUS           VARCHAR2(16) DEFAULT NULL,
            CREATION_TIME    TIMESTAMP (6)
            );
            

CREATE TABLE CLIENTES (
            ID_CLIENTE      NUMBER(11) NOT NULL,
            NOME           VARCHAR2(64) NOT NULL,
            EMPRESA        VARCHAR2(64) NOT NULL
            );

--CHAVES PRIMARIAS

ALTER TABLE ATENDENTES
ADD CONSTRAINT ID_ATENDENTES_PK
PRIMARY KEY ( ID_ATENDENTES );

ALTER TABLE CLIENTES
ADD CONSTRAINT ID_CLIENTE_PK
PRIMARY KEY ( ID_CLIENTE );

ALTER TABLE INCIDENTE
ADD CONSTRAINT ID_INCIDENTE_PK
PRIMARY KEY ( ID_INCIDENTE );

--CHAVES ESTRANGEIRAS

ALTER TABLE INCIDENTE
ADD CONSTRAINT ATENDENTE_FK
FOREIGN KEY ( ATENDENTE )
REFERENCES ATENDENTES ( ID_ATENDENTES );

ALTER TABLE INCIDENTE
ADD CONSTRAINT CLIENTE_FK
FOREIGN KEY ( CLIENTE )
REFERENCES CLIENTES ( ID_CLIENTE );


--INSERINDO ATENDENTES

INSERT INTO ATENDENTES VALUES
(1,'Anderson');
INSERT INTO ATENDENTES VALUES
(2,'André');
INSERT INTO ATENDENTES VALUES
(3,'Otávio');

--INSERINDO CLIENTES

INSERT INTO CLIENTES VALUES
(1, 'JEFFERSON' , 'PIXELS INC');
INSERT INTO CLIENTES VALUES
(2, 'MÁXIMO' , 'YORK RESEARCH');
INSERT INTO CLIENTES VALUES
(3, 'GABRIELLA' , 'FARADAY CO');

--INSERINDO INCIDENTE

INSERT INTO INCIDENTE VALUES
(1, 4, 2, 'Desc do problema', 'aberto', '19-06-2018 01:12:48');
-----------------------------------------------------------------------------------------------------------------------------------

--Aparte em html e php
--estou em aprendizado ainda
--Não consegui finalizar


<!DOCTYPE html>
<html>
<head>  
               <title> Challenge </title>
               <meta charset = "utf-8">
               <link rel= "stylesheet" " type=text css" href="estilo css">
         </head>

      <body>
                 <?php

                    
<h1>"######incidentes######"</h1>
    
                     
              <h2> "Escolha uma opção" $opção ;</h2>
                     
               
            echo "1 - Abrir incidentes";
            echo "2 - Listar incidentes";
            echo "3 - Encerrar incidentes";

                      switch ( opção ){

                      case 1:
                      echo "Abrir incidentes" ;
                      break;
   
                      case 2:
                      echo "Listar incidentes";
                      break;

                     case 3:
                     echo "Encerrar incidentes";
                     break;

                     default:
                     echo "Opção inválida";
                     break;

                  ?>
      </body>
</html>


