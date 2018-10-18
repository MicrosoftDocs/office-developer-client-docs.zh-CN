---
<<<<<<< 标头标题： ConnectionTimeout 属性 (ADO) TOCTitle: ConnectionTimeout 属性 (ADO) === 标题： ConnectionTimeout 属性 (ADO) TOCTitle: ConnectionTimeout 属性 (ADO)
>>>>>>> 母版页 ms:assetid: efc39fd8-afce-5ac0-2fff-cbb55c1a444d ms:mtpsurl: https://msdn.microsoft.com/library/JJ250218(v=office.15) ms:contentKeyID: 48548589 ms.date: 09/18/2015 mtps_version: office.15.aspx
---

<<<<<<< 标头
# <a name="connectiontimeout-property-ado"></a>ConnectionTimeout 属性 (ADO)
=======
# <a name="connectiontimeout-property-ado"></a>ConnectionTimeout 属性 (ADO)
>>>>>>> master


**适用于**： Access 2013 |Office 2013

指示在建立连接时要等待多长时间才终止连接尝试并生成错误。

<<<<<<< 标头
## <a name="settings-and-return-values"></a>设置和返回值
=======
## <a name="settings-and-return-values"></a>设置和返回值
>>>>>>> master

设置或返回一个 **Long** 值，该值指示等待连接打开的时间（以秒为单位）。默认值为 15。

## <a name="remarks"></a>备注

如果由于网络通信延迟或服务器负载太大而有必要放弃连接尝试，请使用 **Connection** 对象上的 [ConnectionTimeout](connection-object-ado.md) 属性。如果在打开连接前超过了 **ConnectionTimeout** 属性设置的时间，将发生错误，且 ADO 将取消连接尝试。如果将该属性设置为零，ADO 将无限期等待，直到连接打开为止。请确保您向其中写入代码的提供程序支持 **ConnectionTimeout** 功能。

**ConnectionTimeout** 属性在连接关闭时为可读/写属性，而在连接打开时为只读属性。

