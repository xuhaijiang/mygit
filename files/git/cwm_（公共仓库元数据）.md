
##  公共仓库元模型 CWM （common warehouse metamodel）
### OMG 和 CWM
OMG：国际知名的标准化组织，提出了以OMA、DMA、CORBA、UML、MOF、XMI、和CWM为代表的一批为软件厂商采用的行业标准。

### CWM 技术标准
CWM使用模型驱动方法，主要基于下面的三个技术标准
1. UML（unified modeling language）统一建模语言，建模标准
2. MOF（meta object facility）一种规范，定义公共抽象语言，元模型和元数据的存储标准，存储形式可以是CORBA对象
3. XMI（XML metadata interchange）XML元数据交换，元数据交换标准

### CWM 和 关系型数据库

SQL99标准，例如关系数据库的表、列、触发器、过程

### CWM元素关系理解
1. 数据层（M0）：学生记录（Record）的实例，即具体的某个学生
2. 模型层（M1）：描述学生这个记录类型的内容，它有一个名字（“Student”）和两个字段（Field）,每个字段都有一个名字和类型，比如第一个字段的名字的“name”，字段类型是String
3. 元模型层（M2）：对Record这种类型进行定义，Record是元类metaClass的一个实例，一个Record拥有两个元属性metaAttribute，第一个name定义它的名字，是String类型，第二个fields定义它包含的字段集，字段集中的成员是Field类型。类似的，元类field应该也包含两个元属性：名字name和类型type
4. 元元模型层（M3）：结构基本固定，它将所有概念抽象为组件：元类meta-Class、元属性meta-Attribute、元关联meta-Association,并定义了元类之间的关系，包括：包含（Contains），继承（Generalizes），类型引用（IsOfType）和依赖（DenpendsOn）

### 基于模型的元数据集成体系组件集
1. **能以共享的、与平台无关的模型方式定义元数据的形式化语言**
2. **一个定义问题领域的公共元模型**
3. **用于交换共享元数据的公共元模型**
4. **用于访问元数据的一个公共程序接口**
5. **用于扩展模型的标准机制**
6. **用于扩展元模型的标准机制**
7. 用于产品元数据导入、导出的软件适配器
8. 一个中央元数据存储库
9. 全面的元数据管理策略
10. 全面的元数据技术体系结构

*案例：微软的 meta data sservice 、Sybase的WCC*

### 元数据管理策略
1. 一个元数据的全局安全策略
2. 对所有元数据源和数据目标的确认机制，即定义什么组件在什么时候承担什么角色，并定义与其他组件的协作
3. 对所有元数据元素的确认机制，即用某种唯一的标识符进行标识
4. 对每个元数据元素语义的一致理解
5. 每个元数据元素的所有权
6. 共享和修改元数据的规则
7. 重新发布元数据元素的规则
8. 元数据元素的版本控制
9. 元数据元素的重用目标
10. 手工过程标出机制
11. 冗余元数据的消除机制


### 元数据分类
1. 技术元数据
    关于数据仓库系统技术细节、用于开发和管理数据仓库使用的数据，包含：   
    1. 数据的逻辑模型和物理模型
    2. 数据仓库中的表名、字段名等属性
    3. 数据仓库数据与数据源之间的对应关系和转换规则
    4. 在线分析处理（OLAP）所用到的维和汇总数据
    5. 用户及安全管理
    
2. 业务元数据
    用于捕捉关于业务规则、业务名称和业务术语等的语义，是为了保证用户能够正确、方便地使用数据仓库系统，主要用来提供系统与最终用户之间的语义层，包括：
    1. 最终用户的业务术语所表达的数据模型、对象名和属性名
    2. 访问数据的原则和数据的来源
    3. 面向主题的分析模型、方法、公式
    4. 报表信息
   
    
### 注意 JMI 技术
sun -> [JMI](https://jcp.org/aboutJava/communityprocess/final/jsr040/index.html)（java metadata interface）元数据访问和管理的J2EE平台下的标准API

### JDBC 元数据支持
JDBC 元数据提取相关，不支持触发器的提取

	Connection conn = getConnection();

**DatabaseMetaData** 数据库的整理综合信息

获得方式 :

	//返回所连接的数据库的元数据 
	DatabaseMetaData dmd = conn.getMetaData();
	//获取可在给定类别中使用的表的描述
	ResultSet rs = dmd.getTables(...);

**ResultSetMetadata** 获取关于 ResultSet 对象中列的类型和属性信息的对象

获得方式 :

	//获取此 ResultSet 对象的列的编号、类型和属性
	ResultSetMetadata rsmd = rs.getMetaData();
	//返回此 ResultSet 对象中的列数
	int numberOfColumns = rsmd.getColumnCount();
	


