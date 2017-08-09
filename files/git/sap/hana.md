## SAP HANA ##

**SAP HANA** 是硬件和软件组合起来的一个解决方案，客户进行海量数据分析时，以接近实时的方式同步数据。
他集成的一些SAP组件， **IMDB(In-Memory Database)**、**Replication**、**SAP STR(Landscape Transformation Replicator)**


### IMDB 内存数据库 ###

- 支持行存储、列存储、对象存储的数据库技术
- 支持多种数据源

### Replication Technologies 数据复制技术 ###

1. Trigger Based Replication (实时模式)
2. ETL Based Replication
3. Log Based Replication

### SAP HANA 架构 ###

#### IMCE Studio
用于HANA的系统管理，以及信息建模(维度、KPI),客户端工具

#### ERP
数据源，ERP的业务数据

#### BO BI4
BO的BI4.0平台，主要提供ETL核心功能，源系统数据导入，删选、合并、格式化数据，导入目标系统

#### Other Source System
包括Sysbase、DB2、Oracle、SQL-Server等主流数据库，还可以是文本XML、CSV、EXCEL

#### In Memory Computing Engine
IMCE核心组件，用于计算数据

#### Clients
客户端工具



### SAP Sybase ASE
交易型数据库，OLTP数据库

### SAP Sybase IQ
分析型数据库

### SAP Sybase SQL Anywhere
移动和嵌入式数据库

### 统一的实时数据平台 
- Sybase ESP
- Replication Server
- PowerDesigner
- +SAP EIM



