---
<<<<<<< 标头标题： CommandType 属性 (ADO) TOCTitle: CommandType 属性 (ADO) === 标题： CommandType 属性 (ADO) TOCTitle: CommandType 属性 (ADO)
>>>>>>> 母版页 ms:assetid: c8d4fc1c-502b-11f3-af9d-605a03b6f056 ms:mtpsurl: https://msdn.microsoft.com/library/JJ249976(v=office.15) ms:contentKeyID: 48547663 ms.date: 09/18/2015 mtps_version: office.15.aspx f1_keywords:
- ado210.chm1231125 f1_categories:
- Office.Version=v15
---

<<<<<<< 头
# <a name="commandtype-property-ado"></a>CommandType 属性 (ADO)
=======
# <a name="commandtype-property-ado"></a>CommandType 属性 (ADO)
>>>>>>> 母版


**适用于**： Access 2013 |Office 2013

指示 [Command](command-object-ado.md) 对象的类型。

<<<<<<< 头
## <a name="settings-and-return-values"></a>设置和返回值
=======
## <a name="settings-and-return-values"></a>设置和返回值
>>>>>>> 母版

设置或返回一个或多个 [CommandTypeEnum](commandtypeenum.md) 值。

> [!NOTE]
> [!注释] 不要将 **adCmdFile** 或 **adCmdTableDirect** 的 **CommandTypeEnum** 值与 **CommandType** 一起使用。这些值仅可作为 [Recordset](open-method-ado-recordset.md) 的 [Open](requery-method-ado.md) 和 [Requery](recordset-object-ado.md) 方法的选项使用。


## <a name="remarks"></a>备注

使用 **CommandType** 属性可以优化 [CommandText](commandtext-property-ado.md) 属性的求值过程。

<<<<<<< 标头如果**CommandType**属性值等于**adCmdUnknown** （默认值），因为 ADO 必须进行到提供程序的调用，以确定是否满足以下条件，您可能会遇到性能降低的**CommandText**属性是 SQL 语句、 存储的过程或表名。 如果知道所使用的命令类型，通过设置 **CommandType** 属性，可以指示 ADO 直接转到相关代码。 如果 **CommandType** 属性与 **CommandText** 属性中的命令类型不匹配，调用 [Execute](https://msdn.microsoft.com/library/jj248785\(v=office.15\)) 方法时将发生错误。
=== ADO 必须进行到提供程序的调用，以确定**CommandText**属性是一个 SQL 语句，因为如果**CommandType**属性值等于**adCmdUnknown** （默认值），您可能会遇到性能降低存储的过程或表名。 如果知道所使用的命令类型，通过设置 **CommandType** 属性，可以指示 ADO 直接转到相关代码。 如果 **CommandType** 属性与 **CommandText** 属性中的命令类型不匹配，调用 [Execute](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/execute-method-ado-command) 方法时将发生错误。
>>>>>>> 母版

