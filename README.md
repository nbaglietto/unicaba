PowerBI– Bonds

Requerimiento
Crear un DashBoard en PowerBi donde el usuario pueda visibilizar la cantidad facturas cargadas en el sistema RIC (Risk Intelligence Central) 
y compararlas con el total cargado en Inbroker (Sistema Core)
El dashboard deberá mostrar
•	Total de facturas cargadas en cada sistema
•	Total pendientes de carga
•	Diferencia de facturas por cargar
•	Cantidad de aseguradoras con envió automático de facturas
•	Permitir filtrar por fechas
•	Mostrar en gráficos el detalle en porcentaje (%) para saber cuánto se cargó por mes
•	Control por número de factura, vigencia y número de póliza/endoso
•	Que la información se pueda exportar a un archivo Excel o similar 

Situación Actual
RIC es una plataforma global que permite subir y compartir (mediante usuarios acreditados) documentación de Caución entre la Empresa, las Aseguradoras y los Clientes.
La carga de archivos y el completar los formularios asociados es un proceso completamente manual.
•	En el Módulo de Finanzas sólo se cargan documentos (Xls o Pdf) en base al excel suministrado
o	Reporte de deuda
o	Pólizas vigentes
o	Facturas
o	Refacturaciones 

Objetivo Esperado
Crear un DashBoard en PowerBi donde el usuario pueda visibilizar la cantidad facturas cargadas en el sistema RIC (Risk Intelligence Central) y compararlas con el total cargado en Inbroker (Sistema Core)
Análisis
Campos Facturación:
 
Los campos con asterisco (*) son campos obligatorios.
Ejemplo (datos ficticios)

Los doc compartidos estan en https://drive.google.com/drive/folders/14UT8AcW9X9uMyuhj0AOjV4bo3v-mbbI9?usp=sharing

Tablas utilizadas:
o	WillisBonds.dbo.Stg_BillingDet
o	WillisBonds.dbo.Stg_BillingHead

Querys para el créate de las tablas:
CREATE TABLE WillisBonds.dbo.Stg_BillingDet (
  TaskName varchar(255) COLLATE Latin1_General_CI_AS NULL,
  StartDate date NULL,
  DueDate date NULL,
  AssignedTo varchar(255) COLLATE Latin1_General_CI_AS NULL,
  TaskStatus varchar(255) COLLATE Latin1_General_CI_AS NULL,
  Motive varchar(255) COLLATE Latin1_General_CI_AS NULL,
  Description varchar(255) COLLATE Latin1_General_CI_AS NULL,
  Client varchar(255) COLLATE Latin1_General_CI_AS NULL,
  LineOfBusiness varchar(255) COLLATE Latin1_General_CI_AS NULL,
  PolicyCode varchar(255) COLLATE Latin1_General_CI_AS NULL,
  EndorsementCode varchar(255) COLLATE Latin1_General_CI_AS NULL,
  Currency varchar(255) COLLATE Latin1_General_CI_AS NULL,
  GrossPremium numeric(18,2) NULL,
  BondCompany varchar(255) COLLATE Latin1_General_CI_AS NULL,
  PolicyStartDate date NULL,
  PolicyEndDate date NULL,
  PolicyDesc varchar(255) COLLATE Latin1_General_CI_AS NULL,
  CustomBroker varchar(255) COLLATE Latin1_General_CI_AS NULL,
  RiskType varchar(255) COLLATE Latin1_General_CI_AS NULL,
  Broker varchar(255) COLLATE Latin1_General_CI_AS NULL,
  FullFileName varchar(255) COLLATE Latin1_General_CI_AS NULL,
  Id numeric(14,0) IDENTITY(1,1) NOT NULL,
  StackTrace varchar(255) COLLATE Latin1_General_CI_AS NULL,
  ProcessingError varchar(255) COLLATE Latin1_General_CI_AS NULL,
  Status varchar(255) COLLATE Latin1_General_CI_AS NULL,
  Carrier varchar(255) COLLATE Latin1_General_CI_AS NULL,
  PivotFileName varchar(255) COLLATE Latin1_General_CI_AS NULL
);
 
CREATE TABLE WillisBonds.dbo.Stg_BillingHead (
  EntryDate date NULL,
  ProcessingDate date NULL,
  ModificationDate date NULL,
  CancellationDate date NULL,
  ProcessingError varchar(255) COLLATE Latin1_General_CI_AS NULL,
  StackTrace varchar(255) COLLATE Latin1_General_CI_AS NULL,
  PivotFileName varchar(255) COLLATE Latin1_General_CI_AS NULL,
  TaskName varchar(255) COLLATE Latin1_General_CI_AS NULL,
  Client varchar(255) COLLATE Latin1_General_CI_AS NULL,
  LineOfBusiness varchar(255) COLLATE Latin1_General_CI_AS NULL,
  Carrier varchar(255) COLLATE Latin1_General_CI_AS NULL,
  DueDate date NULL,
  Broker varchar(255) COLLATE Latin1_General_CI_AS NULL,
  Id numeric(14,0) IDENTITY(1,1) NOT NULL
);
 Querys para el Insert de datosen las tablas

Querypara el total de facturas cargadas

Querypara total de pendientes

QueryDiferencia de facturas por cargar
QueryCantidad de aseguradoras con envió automático de facturas
