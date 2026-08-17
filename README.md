# 🐔 Control de Ventilación de Granja

## 📌 Descripción

**Control de Ventilación de Granja** es una aplicación de escritorio desarrollada en **Java Swing** con conexión a una base de datos **MySQL**.

El sistema fue creado para llevar un control de las diferentes áreas o secciones destinadas a la crianza de pollos y registrar las temperaturas obtenidas mediante un termómetro industrial.

A partir de la temperatura ingresada, el programa determina automáticamente el estado de la temperatura y recomienda el nivel de apertura de la ventilación.

---

## 🎯 Objetivo

Desarrollar una aplicación que permita registrar y administrar las áreas de una granja, controlar las temperaturas registradas y facilitar la toma de decisiones sobre la ventilación de cada sección.

El sistema utiliza operaciones CRUD y almacena la información permanentemente en una base de datos MySQL.

---

## ⚙️ Funcionalidades

### 🔐 Inicio de sesión

El sistema cuenta con una pantalla de Login que solicita:

- Usuario
- Contraseña

Las credenciales son verificadas utilizando los usuarios almacenados en la base de datos.

Una vez que las credenciales son correctas, el usuario puede acceder al menú principal.

---

## 🏠 Menú Principal

Desde el menú principal se puede acceder a:

- Gestión de Áreas
- Control de Temperaturas
- Acerca de
- Salir

---

## 🏢 Gestión de Áreas

Permite administrar las diferentes secciones utilizadas para la crianza de los pollos.

Cada área contiene:

- ID
- Nombre de la sección
- Descripción
- Capacidad

El módulo permite realizar las siguientes operaciones:

- Guardar una nueva área
- Listar las áreas registradas
- Buscar áreas
- Editar áreas
- Actualizar información
- Eliminar áreas

Ejemplo:

| ID | Sección | Descripción | Capacidad |
|---|---|---|---:|
| 2 | Seccion A | 1 a 5 Dias | 2000 |
| 3 | Seccion B | 6 a 15 Dias | 4000 |
| 4 | Seccion C | 16 a 40 Dias | 15000 |
| 5 | Seccion D | Listo para venta | 30000 |

---

## 🌡️ Control de Temperaturas

Este módulo permite seleccionar una de las áreas registradas e ingresar la temperatura obtenida mediante un termómetro.

El programa procesa la temperatura y determina automáticamente:

- Estado de la temperatura
- Nivel recomendado de ventilación

Por ejemplo:

Temperatura ingresada:

`32 °C`

Resultado:

- Estado: `Caliente`
- Ventilación: `Abrir 75%`

Los resultados son almacenados en la base de datos junto con el área correspondiente y la fecha.

El sistema está diseñado para mantener la temperatura actual correspondiente a cada área.

---

## 📅 Fecha automática

La fecha del registro se genera automáticamente utilizando la fecha actual del sistema.

Por esta razón, el usuario no necesita introducir manualmente la fecha de cada medición.

---

## 🔎 Búsqueda

Los módulos de mantenimiento cuentan con una función de búsqueda para localizar registros almacenados en la base de datos.

---

## 🗄️ Base de Datos

El proyecto utiliza **MySQL** como sistema gestor de base de datos.

Nombre de la base de datos:

`control_ventilacion_granja`

La base de datos contiene las siguientes tablas principales:

### usuarios

Almacena las credenciales utilizadas para iniciar sesión.

### areas

Almacena las diferentes secciones de la granja.

### temperaturas

Almacena las temperaturas, estados y niveles de ventilación correspondientes a las áreas.

La relación principal es:

areas → temperaturas

Cada registro de temperatura pertenece a un área registrada.

---

## 📄 Script de Base de Datos

El proyecto incluye el archivo:

database.sql

Este archivo contiene las instrucciones SQL necesarias para crear la base de datos y sus tablas.

Esto facilita la instalación del proyecto en otra computadora.

---

## 💻 Tecnologías utilizadas

- Java
- Java Swing
- JDBC
- MySQL
- MySQL Connector/J
- NetBeans IDE
- Laragon
- HeidiSQL
- Git
- GitHub

---

## 🏗️ Estructura del Proyecto

El proyecto utiliza una estructura basada en Modelo, Vista y Controlador (MVC), junto con clases DAO para acceder a la base de datos.

text
ControlVentilacionGranja
│
├── controlador
│   ├── ControladorArea.java
│   ├── ControladorLogin.java
│   ├── ControladorMenu.java
│   └── ControladorTemperatura.java
│
├── modelo
│   ├── Area.java
│   ├── AreaDAO.java
│   ├── Conexion.java
│   ├── Login.java
│   ├── LoginDAO.java
│   ├── Temperatura.java
│   └── TemperaturaDAO.java
│
├── vista
│   ├── AcercaDe.java
│   ├── LoginV.java
│   ├── MenuPrincipal.java
│   ├── VistaArea.java
│   └── VistaTemperatura.java
│
├── controlventilaciongranja
│   └── ControlVentilacionGranja.java
│
├── lib
│   └── mysql-connector-j-8.3.0.jar
│
├── database.sql
└── README.md
