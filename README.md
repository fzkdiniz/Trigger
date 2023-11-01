TRIGGER EXEMPLO 1 

![image](https://github.com/fzkdiniz/Trigger/assets/61026576/b6f126f9-bc8b-4bc6-93a7-eb5dec976f46)

CREATE TABLE Pedidos(
idPedido int auto_increment PRIMARY KEY,
dataPedido DATETIME,
nomeCliente varchar(100)
);

INSERT INTO Pedidos (dataPedido, NomeCliente) VALUES
 (NOW(), 'Cliente1'),
 (NOW(), 'Cliente2');
 (NOW(), 'Cliente3');
 (NOW(), 'Cliente4');
 (NOW(), 'Cliente5');
 
DELIMITER $
CREATE TRIGGER RegistroDataCriacaoPedido
BEFORE INSERT ON Pedidos
FOR EACH ROW
BEGIN
    SET NEW.DataPedido = NOW();
END$$
DELIMITER ;

INSERT INTO Pedidos (nomeCliente) VALUES ('Novo Cliente');

select * from pedidos;
