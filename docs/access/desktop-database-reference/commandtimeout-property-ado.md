---
<<<<<<< 标头标题： CommandTimeout 属性 (ADO) TOCTitle: CommandTimeout 属性 (ADO) === 标题： CommandTimeout 属性 (ADO) TOCTitle: CommandTimeout 属性 (ADO)
>>>>>>> 母版页 ms:assetid: a0b6209c-9feb-08ae-002a-15d1d20734a8 ms:mtpsurl: https://msdn.microsoft.com/library/JJ249739(v=office.15) ms:contentKeyID: 48546714 ms.date: 09/18/2015 mtps_version: office.15.aspx f1_keywords:
- ado210.chm1231124 f1_categories:
- Office.Version=v15
---

<<<<<<< 标头
# <a name="commandtimeout-property-ado"></a>CommandTimeout 属性 (ADO)
=======
# <a name="commandtimeout-property-ado"></a>CommandTimeout 属性 (ADO)
>>>>>>> master


**适用于**： Access 2013 |Office 2013

指示在执行命令时要等待多长时间才终止操作尝试并生成错误。

<<<<<<< 标头
## <a name="settings-and-return-values"></a>设置和返回值
=======
## <a name="settings-and-return-values"></a>设置和返回值
>>>>>>> master

设置或返回一个 **Long** 值，该值指示等待命令执行的时间（以秒为单位）。默认值为 30。

## <a name="remarks"></a>备注

<<<<<<< 标头[Connection](connection-object-ado.md)对象或[Command](command-object-ado.md)对象上使用**CommandTimeout**属性允许取消的[Execute](https://msdn.microsoft.com/library/jj248785\(v=office.15\))方法调用，由于从网络流量或大量服务器使用的延迟。 如果在完成执行命令前超过了 **CommandTimeout** 属性中设置的间隔时间，则将发生错误，且 ADO 将取消该命令。 如果将该属性设置为零，ADO 将无限期等待，直到完成执行为止。 请确保向其中写入代码的提供程序和数据源支持 **CommandTimeout** 功能。
=== 使用**CommandTimeout**属性在[Connection](connection-object-ado.md)对象或[Command](command-object-ado.md)对象上允许取消的[Execute](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/execute-method-ado-command)方法调用，由于从网络流量或大量服务器使用的延迟。 如果在完成执行命令前超过了 **CommandTimeout** 属性中设置的间隔时间，则将发生错误，且 ADO 将取消该命令。 如果将该属性设置为零，ADO 将无限期等待，直到完成执行为止。 请确保向其中写入代码的提供程序和数据源支持 **CommandTimeout** 功能。
>>>>>>> master

**Connection** 对象上的 **CommandTimeout** 设置对同一个 **Connection** 中的 **Command** 对象的 **CommandTimeout** 设置没有影响；即， **Command** 对象的 **CommandTimeout** 属性并不会继承 **Connection** 对象的 **CommandTimeout** 值。

在 **Connection** 对象上， **CommandTimeout** 属性会在该 **Connection** 打开后保持可读/写状态。

