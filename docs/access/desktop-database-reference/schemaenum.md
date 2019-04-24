---
title: SchemaEnum (Access desktop database reference)
TOCTitle: SchemaEnum
ms:assetid: 6147b682-3c4f-ea91-fff6-ac73107d206d
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249359(v=office.15)
ms:contentKeyID: 48545208
ms.date: 10/18/2018
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: aa70f275de164716b5b3975b56588e9dc4aec1a5
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32308861"
---
# <a name="schemaenum"></a>SchemaEnum

**适用于**：Access 2013、Office 2013

指定 **OpenSchema** 方法所检索的架构 [Recordset](openschema-method-ado.md) 的类型。

## <a name="remarks"></a>注解

有关此函数以及为每个 ADO 常量返回的列的附加信息，请参阅 *《OLE DB 程序员参考》* 附录 B 中的主题。 下表的 "说明" 部分的圆括号中列出了每个主题的名称。

有关此函数以及为每个 ADO MD 常量返回的列的附加信息，请参阅 *《OLE DB for OLAP》* 文档第 23 章中的主题。 下表的 "说明" 列中列出了每个主题的名称\*并在括号中标记了星号 ()。

通过引用 ADO [DataTypeEnum](datatypeenum.md) 主题的“说明”列，将 OLE DB 文档中的列的数据类型转换为 ADO 数据类型。 例如, **\_DBTYPE WSTR**的 OLE DB 数据类型等效于 ADO 数据类型为**adWChar**。

对于常量 **adSchemaDBInfoKeywords** 和 **adSchemaDBInfoLiterals**，ADO 生成类似架构的结果。 ADO 创建一个**记录集**, 然后使用**IDBInfo:: GetKeywords**和**IDBInfo:: GetLiteralInfo**方法分别返回的值填充每个行。 有关这些方法的其他信息, 请参阅《 *OLE DB 程序员参考*》的 IDBInfo 部分。

<br/>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p>常量</p></th>
<th><p>值</p></th>
<th><p>说明</p></th>
<th><p>约束列</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>adSchemaAsserts</strong></p></td>
<td><p>0</p></td>
<td><p>返回在目录中定义的、由指定用户拥有的声明。 （ASSERTIONS 行集）</p></td>
<td><p>CONSTRAINT_CATALOG<br />
CONSTRAINT_SCHEMA<br />
CONSTRAINT_NAME</p></td>
</tr>
<tr class="even">
<td><p><strong>adSchemaCatalogs</strong></p></td>
<td><p>1</p></td>
<td><p>返回与目录关联的、可从 DBMS 访问的物理属性。 （CATALOGS 行集）</p></td>
<td><p>CATALOG_NAME</p></td>
</tr>
<tr class="odd">
<td><p><strong>adSchemaCharacterSets</strong></p></td>
<td><p>双面</p></td>
<td><p>访问在目录中定义的、可供指定用户访问的字符集。 （CHARACTER_SETS 行集）</p></td>
<td><p>CHARACTER_SET_CATALOG<br />
CHARACTER_SET_SCHEMA<br />
CHARACTER_SET_NAME</p></td>
</tr>
<tr class="even">
<td><p><strong>adSchemaCheckConstraints</strong></p></td>
<td><p>5</p></td>
<td><p>返回在目录中定义的、由指定用户拥有的检查约束。 （CHECK_CONSTRAINTS 行集）</p></td>
<td><p>CONSTRAINT_CATALOG<br />
CONSTRAINT_SCHEMA<br />
CONSTRAINT_NAME</p></td>
</tr>
<tr class="odd">
<td><p><strong>adSchemaCollations</strong></p></td>
<td><p>第三章</p></td>
<td><p>访问在目录中定义的、可供指定用户访问的字符排序规则。 （COLLATIONS 行集）</p></td>
<td><p>COLLATION_CATALOG<br />
COLLATION_SCHEMA<br />
COLLATION_NAME</p></td>
</tr>
<tr class="even">
<td><p><strong>adSchemaColumnPrivileges</strong></p></td>
<td><p>13</p></td>
<td><p>返回在目录中定义的、可用于指定用户或由指定用户授权的表列上的权限。 （COLUMN_PRIVILEGES 行集）</p></td>
<td><p>TABLE_CATALOG<br />
TABLE_SCHEMA<br />
TABLE_NAME<br />
COLUMN_NAME<br />
方<br />
授权</p></td>
</tr>
<tr class="odd">
<td><p><strong>adSchemaColumns</strong></p></td>
<td><p>4</p></td>
<td><p>访问在目录中定义的、可供指定用户访问的表列（包括视图）。 （COLUMNS 行集）</p></td>
<td><p>TABLE_CATALOG<br />
TABLE_SCHEMA<br />
TABLE_NAME<br />
COLUMN_NAME</p></td>
</tr>
<tr class="even">
<td><p><strong>adSchemaColumnsDomainUsage</strong></p></td>
<td><p>11x17</p></td>
<td><p>返回在目录中定义的、依赖在目录中定义的域且由指定用户拥有的列。 （COLUMN_DOMAIN_USAGE 行集）</p></td>
<td><p>DOMAIN_CATALOG<br />
DOMAIN_SCHEMA<br />
DOMAIN_NAME<br />
COLUMN_NAME</p></td>
</tr>
<tr class="odd">
<td><p><strong>adSchemaConstraintColumnUsage</strong></p></td>
<td><p>型</p></td>
<td><p>返回由在目录中定义的且由指定用户拥有的引用约束、唯一约束、检查约束和声明所使用的列。 （CONSTRAINT_COLUMN_USAGE 行集）</p></td>
<td><p>TABLE_CATALOG<br />
TABLE_SCHEMA<br />
TABLE_NAME<br />
COLUMN_NAME</p></td>
</tr>
<tr class="even">
<td><p><strong>adSchemaConstraintTableUsage</strong></p></td>
<td><p>步</p></td>
<td><p>返回由在目录中定义的且由指定用户拥有的引用约束、唯一约束、检查约束和声明所使用的表。 （CONSTRAINT_TABLE_USAGE 行集）</p></td>
<td><p>TABLE_CATALOG<br />
TABLE_SCHEMA<br />
TABLE_NAME</p></td>
</tr>
<tr class="odd">
<td><p><strong>adSchemaCubes</strong></p></td>
<td><p>32</p></td>
<td><p>返回有关架构（或目录，如果提供程序不支持架构）中的可用多维数据集的信息。 （CUBES 行集*）</p></td>
<td><p>CATALOG_NAME<br />
SCHEMA_NAME<br />
CUBE_NAME</p></td>
</tr>
<tr class="even">
<td><p><strong>adSchemaDBInfoKeywords</strong></p></td>
<td><p>30</p></td>
<td><p>返回提供程序特定的关键字列表。 (IDBInfo:: GetKeywords *)</p></td>
<td><p>&lt;无&gt;</p></td>
</tr>
<tr class="odd">
<td><p><strong>adSchemaDBInfoLiterals</strong></p></td>
<td><p>31</p></td>
<td><p>返回文本命令中使用的提供程序特定的文字列表。 (IDBInfo:: GetLiteralInfo *)</p></td>
<td><p>&lt;无&gt;</p></td>
</tr>
<tr class="even">
<td><p><strong>adSchemaDimensions</strong></p></td>
<td><p>33</p></td>
<td><p>返回有关指定多维数据集中的维的信息。 对于每个维都包含一行。 （DIMENSIONS 行集*）</p></td>
<td><p>CATALOG_NAME<br />
SCHEMA_NAME<br />
CUBE_NAME<br />
DIMENSION_NAME<br />
DIMENSION_UNIQUE_NAME</p></td>
</tr>
<tr class="odd">
<td><p><strong>adSchemaForeignKeys</strong></p></td>
<td><p>27</p></td>
<td><p>返回由指定用户在目录中定义的外键列。 （FOREIGN_KEYS 行集）</p></td>
<td><p>PK_TABLE_CATALOG<br />
PK_TABLE_SCHEMA<br />
PK_TABLE_NAME<br />
FK_TABLE_CATALOG<br />
FK_TABLE_SCHEMA<br />
FK_TABLE_NAME</p></td>
</tr>
<tr class="even">
<td><p><strong>adSchemaHierarchies</strong></p></td>
<td><p>34</p></td>
<td><p>返回有关维中可用的层次结构的信息。 （HIERARCHIES 行集*）</p></td>
<td><p>CATALOG_NAME<br />
SCHEMA_NAME<br />
CUBE_NAME<br />
DIMENSION_UNIQUE_NAME<br />
HIERARCHY_NAME<br />
HIERARCHY_UNIQUE_NAME</p></td>
</tr>
<tr class="odd">
<td><p><strong>adSchemaIndexes</strong></p></td>
<td><p>12</p></td>
<td><p>返回在目录中定义的由指定用户拥有的索引。 （INDEXES 行集）</p></td>
<td><p>TABLE_CATALOG<br />
TABLE_SCHEMA<br />
INDEX_NAME<br />
类型<br />
TABLE_NAME</p></td>
</tr>
<tr class="even">
<td><p><strong>adSchemaKeyColumnUsage</strong></p></td>
<td><p>utf-8</p></td>
<td><p>返回在目录中定义的、由指定用户约束为键的列。 （KEY_COLUMN_USAGE Rowset 行集）</p></td>
<td><p>CONSTRAINT_CATALOG<br />
CONSTRAINT_SCHEMA<br />
CONSTRAINT_NAME<br />
TABLE_CATALOG<br />
TABLE_SCHEMA<br />
TABLE_NAME<br />
COLUMN_NAME</p></td>
</tr>
<tr class="odd">
<td><p><strong>adSchemaLevels</strong></p></td>
<td><p>35</p></td>
<td><p>返回有关维中可用的级别的信息。 （LEVELS 行集*）</p></td>
<td><p>CATALOG_NAME<br />
SCHEMA_NAME<br />
CUBE_NAME<br />
DIMENSION_UNIQUE_NAME<br />
HIERARCHY_UNIQUE_NAME<br />
LEVEL_NAME<br />
LEVEL_UNIQUE_NAME</p></td>
</tr>
<tr class="even">
<td><p><strong>adSchemaMeasures</strong></p></td>
<td><p>36</p></td>
<td><p>返回有关可用度量的信息。 （MEASURES 行集*）</p></td>
<td><p>CATALOG_NAME<br />
SCHEMA_NAME<br />
CUBE_NAME<br />
MEASURE_NAME<br />
MEASURE_UNIQUE_NAME</p></td>
</tr>
<tr class="odd">
<td><p><strong>adSchemaMembers</strong></p></td>
<td><p>38</p></td>
<td><p>返回有关可用成员的信息。 （MEMBERS 行集*）</p></td>
<td><p>CATALOG_NAME<br />
SCHEMA_NAME<br />
CUBE_NAME<br />
DIMENSION_UNIQUE_NAME<br />
HIERARCHY_UNIQUE_NAME<br />
LEVEL_UNIQUE_NAME<br />
LEVEL_NUMBER<br />
MEMBER_NAME<br />
MEMBER_UNIQUE_NAME<br />
MEMBER_CAPTION<br />
MEMBER_TYPE<br />
Tree 运算符 (有关详细信息, 请参阅 OLE DB For OLAP 文档。)</p></td>
</tr>
<tr class="even">
<td><p><strong>adSchemaPrimaryKeys</strong></p></td>
<td><p>28</p></td>
<td><p>返回由指定用户在目录中定义的主键列。 （PRIMARY_KEYS 行集）</p></td>
<td><p>PK_TABLE_CATALOG<br />
PK_TABLE_SCHEMA<br />
PK_TABLE_NAME</p></td>
</tr>
<tr class="odd">
<td><p><strong>adSchemaProcedureColumns</strong></p></td>
<td><p>29</p></td>
<td><p>返回由过程返回的行集的列的信息。 （PROCEDURE_COLUMNS 行集）</p></td>
<td><p>PROCEDURE_CATALOG<br />
PROCEDURE_SCHEMA<br />
PROCEDURE_NAME<br />
COLUMN_NAME</p></td>
</tr>
<tr class="even">
<td><p><strong>adSchemaProcedureParameters</strong></p></td>
<td><p>26</p></td>
<td><p>返回有关过程的参数和返回代码的信息。 （PROCEDURE_PARAMETERS 行集）</p></td>
<td><p>PROCEDURE_CATALOG<br />
PROCEDURE_SCHEMA<br />
PROCEDURE_NAME<br />
PARAMETER_NAME</p></td>
</tr>
<tr class="odd">
<td><p><strong>adSchemaProcedures</strong></p></td>
<td><p>位</p></td>
<td><p>返回在目录中定义的、由指定用户拥有的过程。 （PROCEDURES 行集）</p></td>
<td><p>PROCEDURE_CATALOG<br />
PROCEDURE_SCHEMA<br />
PROCEDURE_NAME<br />
PROCEDURE_TYPE</p></td>
</tr>
<tr class="even">
<td><p><strong>adSchemaProperties</strong></p></td>
<td><p>37</p></td>
<td><p>返回有关维的每个级别的可用属性的信息。 （PROPERTIES 行集*）</p></td>
<td><p>CATALOG_NAME<br />
SCHEMA_NAME<br />
CUBE_NAME<br />
DIMENSION_UNIQUE_NAME<br />
HIERARCHY_UNIQUE_NAME<br />
LEVEL_UNIQUE_NAME<br />
MEMBER_UNIQUE_NAME<br />
PROPERTY_TYPE<br />
PROPERTY_NAME</p></td>
</tr>
<tr class="odd">
<td><p><strong>adSchemaProviderSpecific</strong></p></td>
<td><p>-1</p></td>
<td><p>当提供程序定义其自己的非标准架构查询时使用。</p></td>
<td><p>&lt;提供程序特定&gt;</p></td>
</tr>
<tr class="even">
<td><p><strong>adSchemaProviderTypes</strong></p></td>
<td><p>22</p></td>
<td><p>返回数据提供程序支持的（基础）数据类型。 （PROVIDER_TYPES 行集）</p></td>
<td><p>DATA_TYPE<br />
BEST_MATCH</p></td>
</tr>
<tr class="odd">
<td><p><strong>AdSchemaReferentialConstraints</strong></p></td>
<td><p>第</p></td>
<td><p>返回在目录中定义的、由指定用户拥有的引用约束。 （REFERENTIAL_CONSTRAINTS 行集）</p></td>
<td><p>CONSTRAINT_CATALOG<br />
CONSTRAINT_SCHEMA<br />
CONSTRAINT_NAME</p></td>
</tr>
<tr class="even">
<td><p><strong>adSchemaSchemata</strong></p></td>
<td><p>×</p></td>
<td><p>返回由指定用户拥有的架构（数据库对象）。 （SCHEMATA 行集）</p></td>
<td><p>CATALOG_NAME<br />
SCHEMA_NAME<br />
SCHEMA_OWNER</p></td>
</tr>
<tr class="odd">
<td><p><strong>adSchemaSQLLanguages</strong></p></td>
<td><p>18</p></td>
<td><p>返回由目录中定义的 SQL 实现处理数据支持的一致性级别、选项和语句编写。 （SQL_LANGUAGES 行集）</p></td>
<td><p>&lt;无&gt;</p></td>
</tr>
<tr class="even">
<td><p><strong>adSchemaStatistics</strong></p></td>
<td><p>合</p></td>
<td><p>返回在目录中定义的、由指定用户拥有的统计信息。 （STATISTICS 行集）</p></td>
<td><p>TABLE_CATALOG<br />
TABLE_SCHEMA<br />
TABLE_NAME</p></td>
</tr>
<tr class="odd">
<td><p><strong>adSchemaTableConstraints</strong></p></td>
<td><p>10</p></td>
<td><p>返回在目录中定义的、由指定用户拥有的表约束。 （TABLE_CONSTRAINTS 行集）</p></td>
<td><p>CONSTRAINT_CATALOG<br />
CONSTRAINT_SCHEMA<br />
CONSTRAINT_NAME<br />
TABLE_CATALOG<br />
TABLE_SCHEMA<br />
TABLE_NAME<br />
CONSTRAINT_TYPE</p></td>
</tr>
<tr class="even">
<td><p><strong>adSchemaTablePrivileges</strong></p></td>
<td><p>日</p></td>
<td><p>返回在目录中定义的、可用于指定用户或由指定用户授权的表上的权限。 （TABLE_PRIVILEGES 行集）</p></td>
<td><p>TABLE_CATALOG<br />
TABLE_SCHEMA<br />
TABLE_NAME<br />
方<br />
授权</p></td>
</tr>
<tr class="odd">
<td><p><strong>adSchemaTables</strong></p></td>
<td><p>20</p></td>
<td><p>返回在目录中定义的、可供指定用户访问的表（包括视图）。 （TABLES 行集）</p></td>
<td><p>TABLE_CATALOG<br />
TABLE_SCHEMA<br />
TABLE_NAME<br />
TABLE_TYPE</p></td>
</tr>
<tr class="even">
<td><p><strong>adSchemaTranslations</strong></p></td>
<td><p>不足</p></td>
<td><p>返回在目录中定义的、可供指定用户访问的字符转换。 （TRANSLATIONS 行集）</p></td>
<td><p>TRANSLATION_CATALOG<br />
TRANSLATION_SCHEMA<br />
TRANSLATION_NAME</p></td>
</tr>
<tr class="odd">
<td><p><strong>adSchemaTrustees</strong></p></td>
<td><p>39</p></td>
<td><p>保留以备将来使用。</p></td>
<td><p><br />
</p></td>
</tr>
<tr class="even">
<td><p><strong>adSchemaUsagePrivileges</strong></p></td>
<td><p>个</p></td>
<td><p>返回在目录中定义的、可用于指定用户或由指定用户授权的对象上的 USAGE 权限。 （USAGE_PRIVILEGES 行集）</p></td>
<td><p>OBJECT_CATALOG<br />
OBJECT_SCHEMA<br />
OBJECT_NAME<br />
OBJECT_TYPE<br />
方<br />
授权</p></td>
</tr>
<tr class="odd">
<td><p><strong>adSchemaViewColumnUsage</strong></p></td>
<td><p>24</p></td>
<td><p>返回在目录中定义的、由指定用户拥有的被查看表所依赖的列。 （VIEW_COLUMN_USAGE 行集）</p></td>
<td><p>VIEW_CATALOG<br />
VIEW_SCHEMA<br />
VIEW_NAME</p></td>
</tr>
<tr class="even">
<td><p><strong>adSchemaViews</strong></p></td>
<td><p>上午</p></td>
<td><p>访问在目录中定义的、可供指定用户访问的视图。 （VIEWS 行集）</p></td>
<td><p>TABLE_CATALOG<br />
TABLE_SCHEMA<br />
TABLE_NAME</p></td>
</tr>
<tr class="odd">
<td><p><strong>adSchemaViewTableUsage</strong></p></td>
<td><p>word</p></td>
<td><p>返回在目录中定义的、由指定用户拥有的被查看表所依赖的表。 （VIEW_TABLE_USAGE 行集）</p></td>
<td><p>VIEW_CATALOG<br />
VIEW_SCHEMA<br />
VIEW_NAME</p></td>
</tr>
</tbody>
</table>


### <a name="adowfc-equivalent"></a>ADO/WFC 等效项

包：**com.ms.wfc.data**

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p>常量</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>AdoEnums</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums CHARACTERSETS</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums CHECKCONSTRAINTS</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums 排序规则</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums COLUMNPRIVILEGES</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums COLUMNSDOMAINUSAGE</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums CONSTRAINTCOLUMNUSAGE</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums CONSTRAINTTABLEUSAGE</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums DBINFOKEYWORDS</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums DBINFOLITERALS</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums FOREIGNKEYS</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums KEYCOLUMNUSAGE</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums 成员</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums PRIMARYKEYS</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums PROCEDURECOLUMNS</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums PROCEDUREPARAMETERS</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums 过程</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums PROVIDERSPECIFIC</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums PROVIDERTYPES</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums REFERENTIALCONTRAINTS</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums SQLLANGUAGES</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums 统计信息</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums TABLECONSTRAINTS</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums TABLEPRIVILEGES</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums USAGEPRIVILEGES</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums VIEWCOLUMNUSAGE</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums VIEWTABLEUSAGE</p></td>
</tr>
</tbody>
</table>

