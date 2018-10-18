---
<<<<<<< 标头标题： 排序属性 (ADO) TOCTitle： 排序属性 (ADO) === 标题： 排序属性 (ADO) TOCTitle： 排序属性 (ADO)
>>>>>>> 母版页 ms:assetid: f2a39b7f-8b96-cd1a-8248-71f8b867454a ms:mtpsurl: https://msdn.microsoft.com/library/JJ250230(v=office.15) ms:contentKeyID: 48548652 ms.date: 09/18/2015 mtps_version: office.15.aspx
---

<<<<<<< 标头
# <a name="sort-property-ado"></a>Sort 属性 (ADO)
=======
# <a name="sort-property-ado"></a>Sort 属性 (ADO)
>>>>>>> master


**适用于**： Access 2013 |Office 2013

指示一个或多个作为 [Recordset](recordset-object-ado.md) 的排序依据的字段名称，并指定是按升序还是降序对字段进行排序。

<<<<<<< 标头
## <a name="settings-and-return-values"></a>设置和返回值
=======
## <a name="settings-and-return-values"></a>设置和返回值
>>>>>>> master

设置或返回一个 **String** 值，指示作为 **Recordset** 的排序依据的字段名称。每个名称由逗号分隔，可以选择后跟空格和关键字 **ASC** （以升序对字段进行排序）或 **DESC** （以降序对字段进行排序）。默认情况下，如果未指定关键字，则以升序对字段进行排序。

## <a name="remarks"></a>备注

此属性要求 [CursorLocation](cursorlocation-property-ado.md) 属性设置为 **adUseClient** 。如果索引尚不存在，则将为 **Sort** 属性中指定的每个字段创建一个临时索引。

实际上数据并没有重新排列，只是简单地按索引指定的顺序进行访问，因此排序操作效率较高。

如果将 **Sort** 属性设置为一个空字符串，则会将行重置为其初始顺序并删除临时索引。现有的索引不会被删除。

假设**记录集**包含三个名称分别为*firstName*、 *middleInitial*和*lastName*的字段。 将**Sort**属性设置为字符串，"lastName DESC，firstName ASC"，其中将顺序**Recordset** ，按降序排序，最后一个名称，然后按升序排序的第一个名称。 忽略中间名首字母。

由于与关键字 **ASC** 和 **DESC** 发生冲突，字段无法命名为 "ASC" 或 "DESC"。请通过在返回 **Recordset** 的查询中使用 **AS** 关键字，来为名称有冲突的字段提供别名。

