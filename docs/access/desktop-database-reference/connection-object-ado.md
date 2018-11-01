---
title: Connection 对象 (ADO)
TOCTitle: Connection Object (ADO)
ms:assetid: c16023aa-0321-2513-ee71-255d6ffba03d
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249940(v=office.15)
ms:contentKeyID: 48547528
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- ado210.chm1231105
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 0f2c629a24bf6327be8a9848e719b40bfa88ea17
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25873318"
---
# <a name="connection-object-ado"></a>Connection 对象 (ADO)

**适用于**： Access 2013、 Office 2013

表示指向数据源的打开的连接。

## <a name="remarks"></a>说明

**Connection** 对象表示与数据源的唯一会话。对于客户端/服务器数据库系统，该对象可能等效于与服务器的实际网络连接。取决于提供程序所支持的功能， **Connection** 对象的某些集合、方法或属性可能不可用。

使用 **Connection** 对象的集合、方法和属性，可以执行下列操作：

  - 在打开连接之前，使用 [ConnectionString](connectionstring-property-ado.md)、[ConnectionTimeout](connectiontimeout-property-ado.md) 和 [Mode](mode-property-ado.md) 属性配置连接。 **ConnectionString** 是 **Connection** 对象的默认属性。

  - 设置客户端的 [CursorLocation](cursorlocation-property-ado.md) 属性，以调用 [Microsoft Cursor Service for OLE DB](microsoft-cursor-service-for-ole-db-ado-service-component.md)，该服务支持批更新。

  - 使用 [DefaultDatabase](defaultdatabase-property-ado.md) 属性设置连接的默认数据库。

  - 使用 [IsolationLevel](isolationlevel-property-ado.md) 属性设置连接上打开的事务的隔离级别。

  - 使用 [Provider](provider-property-ado.md) 属性指定 OLE DB 提供程序。

  - 使用 [Open](open-method-ado-connection.md) 和 [Close](close-method-ado.md) 方法建立与数据源的物理连接，然后断开连接。

  - 使用 [Execute](https://msdn.microsoft.com/library/jj249832\(v=office.15\)) 方法在连接上执行命令，并使用 [CommandTimeout](commandtimeout-property-ado.md) 属性配置执行。
    

    > [!NOTE]
    > [!注释] 若要在不使用 Command 对象的情况下执行查询，可将查询字符串传递给 **Connection** 对象的 **Execute** 方法。但是，如果要持久保留命令文本并重新执行它，或使用查询参数，则需要 [Command](command-object-ado.md) 对象。

  - 使用 [BeginTrans](begintrans-committrans-and-rollbacktrans-methods-ado.md)、[CommitTrans](begintrans-committrans-and-rollbacktrans-methods-ado.md) 和 [RollbackTrans](begintrans-committrans-and-rollbacktrans-methods-ado.md) 方法以及 [Attributes](attributes-property-ado.md) 属性管理打开连接上的事务（如果提供程序支持嵌套事务，则包括嵌套事务）。

  - 使用 [Errors](errors-collection-ado.md) 集合检查数据源返回的错误。

  - 使用 [Version](version-property-ado.md) 属性从所用的 ADO 实现中读取版本。

  - 使用 [OpenSchema](openschema-method-ado.md) 方法获取有关数据库的架构信息。

可以独立于任何其他以前定义的对象创建 **Connection** 对象。

可以将命令或存储过程作为 **Connection** 对象的本地方法来执行，如下所述。

### <a name="execute-a-command-as-a-native-method-of-a-connection-object"></a>将命令作为 Connection 对象的本地方法执行

若要执行某个命令，请使用 **Command** 对象的 [Name](name-property-ado.md) 属性给命令命名。将 **Command** 对象的 **ActiveConnection** 属性设置为该连接。然后将使用该命令名的语句作为 **Connection** 对象的方法发出，后跟任何参数，如果返回了任何行，则后面再跟随 **Recordset** 对象。设置 **Recordset** 属性以便自定义生成的 **Recordset** 。例如：

```vb
    Dim cnn As New ADODB.Connection
    Dim cmd As New ADODB.Command
    Dim rst As New ADODB.Recordset
    ...
    cnn.Open "..."
    cmd.Name = "yourCommandName"
    cmd.ActiveConnection = cnn
    ...
    'Your command name, any parameters, and an optional Recordset.
    cnn.yourCommandName "parameter", rst
```

### <a name="execute-a-stored-procedure-as-a-native-method-of-a-connection-object"></a>将存储过程作为 Connection 对象的本地方法执行

若要执行某个存储过程，请将使用该存储过程的语句作为 **Connection** 对象的方法发出，后跟任何参数。ADO 将"尽量推测"参数的类型。例如：

```vb
    Dim cnn As New ADODB.Connection
    ...
    'Your stored procedure name and any parameters.
    cnn.sp_yourStoredProcedureName "parameter"
```
