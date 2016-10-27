# This is an online review system for different libraries.
# Project is build using Spring MVC and Security based on 2 user roles: admin and user.
# Please let me know if you have any questions
# Database dump is here. Just copy and run sql commands.
# Enjoy :-)
The db dump is here:
CREATE DATABASE  IF NOT EXISTS `registry` /*!40100 DEFAULT CHARACTER SET utf8 */;
USE `registry`;
-- MySQL dump 10.13  Distrib 5.7.12, for Win64 (x86_64)
--
-- Host: localhost    Database: registry
-- ------------------------------------------------------
-- Server version	5.7.15-log

/*!40101 SET @OLD_CHARACTER_SET_CLIENT=@@CHARACTER_SET_CLIENT */;
/*!40101 SET @OLD_CHARACTER_SET_RESULTS=@@CHARACTER_SET_RESULTS */;
/*!40101 SET @OLD_COLLATION_CONNECTION=@@COLLATION_CONNECTION */;
/*!40101 SET NAMES utf8 */;
/*!40103 SET @OLD_TIME_ZONE=@@TIME_ZONE */;
/*!40103 SET TIME_ZONE='+00:00' */;
/*!40014 SET @OLD_UNIQUE_CHECKS=@@UNIQUE_CHECKS, UNIQUE_CHECKS=0 */;
/*!40014 SET @OLD_FOREIGN_KEY_CHECKS=@@FOREIGN_KEY_CHECKS, FOREIGN_KEY_CHECKS=0 */;
/*!40101 SET @OLD_SQL_MODE=@@SQL_MODE, SQL_MODE='NO_AUTO_VALUE_ON_ZERO' */;
/*!40111 SET @OLD_SQL_NOTES=@@SQL_NOTES, SQL_NOTES=0 */;

--
-- Table structure for table `reviewes`
--

DROP TABLE IF EXISTS `reviewes`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `reviewes` (
  `ID` int(11) NOT NULL AUTO_INCREMENT,
  `ADDED_BY` varchar(45) DEFAULT NULL,
  `PRODUCT_ID` int(11) DEFAULT NULL,
  `REVIEW` varchar(45) DEFAULT NULL,
  PRIMARY KEY (`ID`),
  UNIQUE KEY `ID_UNIQUE` (`ID`)
) ENGINE=InnoDB AUTO_INCREMENT=39 DEFAULT CHARSET=utf8;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Dumping data for table `reviewes`
--

LOCK TABLES `reviewes` WRITE;
/*!40000 ALTER TABLE `reviewes` DISABLE KEYS */;
INSERT INTO `reviewes` VALUES (1,'Ovidiu',1,'Is the best book I ve ever read'),(2,'user',NULL,'test add review'),(3,'user',NULL,'test'),(4,'user',NULL,'test add review'),(5,'user',1,'test add review'),(6,'user',1,'test'),(7,'user',1,'test add review'),(8,'user',1,'test'),(9,'user',1,'test add review'),(10,'user',1,'test add review'),(11,'user',1,'test add review'),(12,'user',1,'test add review'),(13,'user',1,'test add review'),(14,'user',1,'test add review'),(15,'user',1,'test add review'),(16,'user',1,'test add review'),(17,'user',1,'test add review'),(18,'user',2,'test add review'),(19,'user',1,'test add review'),(20,'user',1,'final test add review'),(21,'pitica',1,'final test add review'),(22,'user',7,'test add review for hibernate in action'),(23,'user',7,'sdfdsfdsfdsfdsfs'),(24,'user',7,'sdfsdfdsfsdf'),(25,'admin',2,'test'),(26,'user',3,'test add review'),(27,'user',3,'asasdasdasda'),(28,'user',3,'asdasdadsadsa'),(29,'user',3,'asdadasdsa1111'),(30,'user',3,'test add review'),(31,'user',3,'test add review for hibernate in action11111'),(32,'user',3,'qweqewqewqewqewqeq23232323'),(33,'user',9,'sdasda'),(34,'user',9,'asdada'),(35,'user',9,'sdadada'),(36,'user',9,'final test add review'),(37,'user',3,'sdfsdfdsfsdf'),(38,'user',3,'final test add review');
/*!40000 ALTER TABLE `reviewes` ENABLE KEYS */;
UNLOCK TABLES;

--
-- Table structure for table `store_product`
--

DROP TABLE IF EXISTS `store_product`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `store_product` (
  `PRODUCT_ID` int(11) NOT NULL AUTO_INCREMENT,
  `NAME` varchar(255) DEFAULT NULL,
  `TYPE` varchar(255) DEFAULT NULL,
  `PRICE` int(11) DEFAULT NULL,
  `QUANTITY` int(11) DEFAULT NULL,
  `REVIEW` varchar(45) DEFAULT 'No reviews added',
  PRIMARY KEY (`PRODUCT_ID`)
) ENGINE=InnoDB AUTO_INCREMENT=20 DEFAULT CHARSET=utf8;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Dumping data for table `store_product`
--

LOCK TABLES `store_product` WRITE;
/*!40000 ALTER TABLE `store_product` DISABLE KEYS */;
INSERT INTO `store_product` VALUES (2,'Angular Book','JavaScript',10,111,NULL),(3,'Petre Ovidiu','Java book',12,1,NULL),(4,'Spring MVC Book ','Java book',12,12,NULL),(5,'Spring Security Book','Java book',12,1,NULL),(6,'Spring Batch Book','Java book',123,12,NULL),(7,'Hibernate in action','DB',4,1,NULL),(8,'Hibernate','DB',12,4,NULL),(9,'Spring in action','Java book',123,1,NULL),(10,'DB2 overview','DB books',1234,12,NULL),(12,'Spring Book last edition','Java book',12,11,NULL),(13,'Spring Book last edition 1','Java book',12,11,NULL),(14,'Spring Book last edition 2','Java book',12,11,NULL),(15,'Spring Book last edition 3','Java book',12,11,NULL),(16,'Spring Book','Java book',12,12,NULL),(17,'Spring Book','Java book',1,1,NULL),(18,'Ovidiu','Java book',121,12,NULL),(19,'Spring Book last edition 1--','Java book',12,1,NULL);
/*!40000 ALTER TABLE `store_product` ENABLE KEYS */;
UNLOCK TABLES;

--
-- Table structure for table `store_user`
--

DROP TABLE IF EXISTS `store_user`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `store_user` (
  `USER_ID` float NOT NULL AUTO_INCREMENT,
  `NAME` varchar(50) DEFAULT NULL,
  `PASSWORD` varchar(80) DEFAULT NULL,
  `ID_STATUS` float DEFAULT '1',
  `ID_ROLE` float DEFAULT '2',
  `USERNAME` varchar(20) DEFAULT NULL,
  PRIMARY KEY (`USER_ID`)
) ENGINE=InnoDB AUTO_INCREMENT=19 DEFAULT CHARSET=utf8;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Dumping data for table `store_user`
--

LOCK TABLES `store_user` WRITE;
/*!40000 ALTER TABLE `store_user` DISABLE KEYS */;
INSERT INTO `store_user` VALUES (15,'Petre Ovidiu Eduard','e10adc3949ba59abbe56e057f20f883e',1,1,'admin'),(16,'Ovidiu User Role','c33367701511b4f6020ec61ded352059',1,2,'user'),(17,'Ovidiu Petre','c33367701511b4f6020ec61ded352059',1,2,'userOvi'),(18,'ovi','c33367701511b4f6020ec61ded352059',1,2,'userOvi');
/*!40000 ALTER TABLE `store_user` ENABLE KEYS */;
UNLOCK TABLES;

--
-- Table structure for table `store_user_role`
--

DROP TABLE IF EXISTS `store_user_role`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `store_user_role` (
  `U_ROLE_ID` float DEFAULT NULL,
  `NAME` varchar(20) DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Dumping data for table `store_user_role`
--

LOCK TABLES `store_user_role` WRITE;
/*!40000 ALTER TABLE `store_user_role` DISABLE KEYS */;
INSERT INTO `store_user_role` VALUES (1,'ROLE_ADMIN'),(2,'ROLE_USER');
/*!40000 ALTER TABLE `store_user_role` ENABLE KEYS */;
UNLOCK TABLES;

--
-- Table structure for table `store_user_status`
--

DROP TABLE IF EXISTS `store_user_status`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `store_user_status` (
  `U_STATUS_ID` float DEFAULT NULL,
  `NAME` varchar(20) DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Dumping data for table `store_user_status`
--

LOCK TABLES `store_user_status` WRITE;
/*!40000 ALTER TABLE `store_user_status` DISABLE KEYS */;
INSERT INTO `store_user_status` VALUES (1,'ACTIVE'),(2,'INACTIVE');
/*!40000 ALTER TABLE `store_user_status` ENABLE KEYS */;
UNLOCK TABLES;
/*!40103 SET TIME_ZONE=@OLD_TIME_ZONE */;

/*!40101 SET SQL_MODE=@OLD_SQL_MODE */;
/*!40014 SET FOREIGN_KEY_CHECKS=@OLD_FOREIGN_KEY_CHECKS */;
/*!40014 SET UNIQUE_CHECKS=@OLD_UNIQUE_CHECKS */;
/*!40101 SET CHARACTER_SET_CLIENT=@OLD_CHARACTER_SET_CLIENT */;
/*!40101 SET CHARACTER_SET_RESULTS=@OLD_CHARACTER_SET_RESULTS */;
/*!40101 SET COLLATION_CONNECTION=@OLD_COLLATION_CONNECTION */;
/*!40111 SET SQL_NOTES=@OLD_SQL_NOTES */;

-- Dump completed on 2016-10-17 22:12:02
