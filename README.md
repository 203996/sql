# sql

SET @OLD_UNIQUE_CHECKS=@@UNIQUE_CHECKS, UNIQUE_CHECKS=0;
SET @OLD_FOREIGN_KEY_CHECKS=@@FOREIGN_KEY_CHECKS, FOREIGN_KEY_CHECKS=0;
SET @OLD_SQL_MODE=@@SQL_MODE, SQL_MODE='ONLY_FULL_GROUP_BY,STRICT_TRANS_TABLES,NO_ZERO_IN_DATE,NO_ZERO_DATE,ERROR_FOR_DIVISION_BY_ZERO,NO_ENGINE_SUBSTITUTION';

-- -----------------------------------------------------
-- Schema mydb
-- -----------------------------------------------------

-- -----------------------------------------------------
-- Schema mydb
-- -----------------------------------------------------
CREATE SCHEMA IF NOT EXISTS `mydb` DEFAULT CHARACTER SET utf8 ;
USE `mydb` ;

-- -----------------------------------------------------
-- Table `Administrador`
-- -----------------------------------------------------
CREATE TABLE IF NOT EXISTS `Administrador` (
  `idAdministrador` INT NOT NULL,
  `IdPermissao` INT NULL,
  `Nome` VARCHAR(255) NULL,
  `Email` VARCHAR(255) NULL,
  `CPF` INT NULL,
  `Login` VARCHAR(255) NULL,
  `Senha` VARCHAR(255) NULL,
  PRIMARY KEY (`idAdministrador`))
ENGINE = InnoDB;


-- -----------------------------------------------------
-- Table `Categoria`
-- -----------------------------------------------------
CREATE TABLE IF NOT EXISTS `Categoria` (
  `idCategoria` INT NULL AUTO_INCREMENT,
  `TipoCategoria` VARCHAR(255) NULL,
  PRIMARY KEY (`idCategoria`))
ENGINE = InnoDB;


-- -----------------------------------------------------
-- Table `Cliente`
-- -----------------------------------------------------
CREATE TABLE IF NOT EXISTS `Cliente` (
  `idCliente` INT NOT NULL,
  `Nome` VARCHAR(255) NULL,
  `Email` VARCHAR(255) NULL,
  `Endereço` NVARCHAR(255) NULL,
  `CPF` INT NULL,
  `Telefone` VARCHAR(255) NULL,
  `Login` VARCHAR(255) NULL,
  `Senha` VARCHAR(255) NULL,
  PRIMARY KEY (`idCliente`))
ENGINE = InnoDB;


-- -----------------------------------------------------
-- Table `Ordem de Serviço`
-- -----------------------------------------------------
CREATE TABLE IF NOT EXISTS `Ordem de Serviço` (
  `idOrdemDeServiço` INT NOT NULL,
  `DataDeAbertura` VARCHAR(255) NULL,
  `DataDeFechamento` VARCHAR(255) NULL,
  `Valor` VARCHAR(255) NULL,
  `Descrição` VARCHAR(255) NULL,
  `AvaliacaoPrestador` VARCHAR(255) NULL,
  `AvaliacaoCliente` VARCHAR(255) NULL,
  `Prestador_idPrestador` INT NOT NULL,
  `Cliente_idCliente` INT NOT NULL,
  PRIMARY KEY (`idOrdemDeServiço`))
ENGINE = InnoDB;

-- -----------------------------------------------------
-- Table `Prestador`
-- -----------------------------------------------------
CREATE TABLE IF NOT EXISTS `Prestador` (
  `idPrestador` INT NOT NULL,
  `Nome` VARCHAR(255) NULL,
  `Email` VARCHAR(255) NULL,
  `Endereço` VARCHAR(255) NULL,
  `CPF` INT NULL,
  `Telefone` VARCHAR(45) NULL,
  `Login` VARCHAR(255) NULL,
  `Senha` VARCHAR(255) NULL,
  `Categoria_idCategoria` INT NOT NULL,
  PRIMARY KEY (`idPrestador`))
ENGINE = InnoDB;


SET SQL_MODE=@OLD_SQL_MODE;
SET FOREIGN_KEY_CHECKS=@OLD_FOREIGN_KEY_CHECKS;
SET UNIQUE_CHECKS=@OLD_UNIQUE_CHECKS;
