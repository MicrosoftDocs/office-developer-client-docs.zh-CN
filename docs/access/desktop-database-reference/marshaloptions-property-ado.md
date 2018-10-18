---
<<<<<<< 标头标题： MarshalOptions 属性 (ADO) TOCTitle: MarshalOptions 属性 (ADO) === 标题： MarshalOptions 属性 (ADO) TOCTitle: MarshalOptions 属性 (ADO)
>>>>>>> 母版页 ms:assetid: dc9c4e94-0725-210d-8251-079054541142 ms:mtpsurl: https://msdn.microsoft.com/library/JJ250118(v=office.15) ms:contentKeyID: 48548143 ms.date: 09/18/2015 mtps_version: office.15.aspx
---

<<<<<<< 标头
# <a name="marshaloptions-property-ado"></a>MarshalOptions 属性 (ADO)
=======
# <a name="marshaloptions-property-ado"></a>MarshalOptions 属性 (ADO)
>>>>>>> master


**适用于**： Access 2013 |Office 2013

指示哪些记录要封送回服务器。

## <a name="settings-and-return-values"></a>设置和返回值

设置或返回一个 [MarshalOptionsEnum](marshaloptionsenum.md) 值。默认值是 **adMarshalAll** 。

## <a name="remarks"></a>备注

<<<<<<< 标头时使用客户端[Recordset](recordset-object-ado.md)，客户端已修改的记录写入回中间层或通过称为封送，打包和发送接口的过程的技术的 Web 服务器跨线程或进程边界方法参数。 当已修改的远程数据通过封送更新回中间层或 Web 服务器时，设置 **MarshalOptions** 属性可提高性能。
=== 时使用的客户端[Recordset](recordset-object-ado.md)，客户端已修改的记录写入回中间层或通过称为封送，打包和发送跨接口方法参数的过程的技术的 web 服务器线程或进程的边界。 已修改的远程数据封送回中间层或 web 服务器更新时，设置**MarshalOptions**属性可以提高性能。
>>>>>>> master

**远程数据服务用法**此属性只能在客户端**Recordset**上使用。

