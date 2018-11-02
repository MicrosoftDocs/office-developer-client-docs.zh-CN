---
title: Connection 对象 (ADO)
TOCTitle: Connection object (ADO)
ms:assetid: c16023aa-0321-2513-ee71-255d6ffba03d
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249940(v=office.15)
ms:contentKeyID: 48547528
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- ado210.chm1231105
f1_categories:
- Office.Version=v15
ms.openlocfilehash: d7f35c2f76ec8cf2fd671f5ef9eefb42f8555237
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25931384"
---
# <a name="connection-object-ado"></a><span data-ttu-id="b5eb4-102">Connection 对象 (ADO)</span><span class="sxs-lookup"><span data-stu-id="b5eb4-102">Connection object (ADO)</span></span>

<span data-ttu-id="b5eb4-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="b5eb4-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="b5eb4-104">表示指向数据源的打开的连接。</span><span class="sxs-lookup"><span data-stu-id="b5eb4-104">Represents an open connection to a data source.</span></span>

## <a name="remarks"></a><span data-ttu-id="b5eb4-105">说明</span><span class="sxs-lookup"><span data-stu-id="b5eb4-105">Remarks</span></span>

<span data-ttu-id="b5eb4-p101">**Connection** 对象表示与数据源的唯一会话。对于客户端/服务器数据库系统，该对象可能等效于与服务器的实际网络连接。取决于提供程序所支持的功能， **Connection** 对象的某些集合、方法或属性可能不可用。</span><span class="sxs-lookup"><span data-stu-id="b5eb4-p101">A **Connection** object represents a unique session with a data source. In the case of a client/server database system, it may be equivalent to an actual network connection to the server. Depending on the functionality supported by the provider, some collections, methods, or properties of a **Connection** object may not be available.</span></span>

<span data-ttu-id="b5eb4-109">使用 **Connection** 对象的集合、方法和属性，可以执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="b5eb4-109">With the collections, methods, and properties of a **Connection** object, you can do the following:</span></span>

  - <span data-ttu-id="b5eb4-p102">在打开连接之前，使用 [ConnectionString](connectionstring-property-ado.md)、[ConnectionTimeout](connectiontimeout-property-ado.md) 和 [Mode](mode-property-ado.md) 属性配置连接。 **ConnectionString** 是 **Connection** 对象的默认属性。</span><span class="sxs-lookup"><span data-stu-id="b5eb4-p102">Configure the connection before opening it with the [ConnectionString](connectionstring-property-ado.md), [ConnectionTimeout](connectiontimeout-property-ado.md), and [Mode](mode-property-ado.md) properties. **ConnectionString** is the default property of the **Connection** object.</span></span>

  - <span data-ttu-id="b5eb4-112">设置客户端的 [CursorLocation](cursorlocation-property-ado.md) 属性，以调用 [Microsoft Cursor Service for OLE DB](microsoft-cursor-service-for-ole-db-ado-service-component.md)，该服务支持批更新。</span><span class="sxs-lookup"><span data-stu-id="b5eb4-112">Set the [CursorLocation](cursorlocation-property-ado.md) property to client to invoke the [Microsoft Cursor Service for OLE DB](microsoft-cursor-service-for-ole-db-ado-service-component.md), which supports batch updates.</span></span>

  - <span data-ttu-id="b5eb4-113">使用 [DefaultDatabase](defaultdatabase-property-ado.md) 属性设置连接的默认数据库。</span><span class="sxs-lookup"><span data-stu-id="b5eb4-113">Set the default database for the connection with the [DefaultDatabase](defaultdatabase-property-ado.md) property.</span></span>

  - <span data-ttu-id="b5eb4-114">使用 [IsolationLevel](isolationlevel-property-ado.md) 属性设置连接上打开的事务的隔离级别。</span><span class="sxs-lookup"><span data-stu-id="b5eb4-114">Set the level of isolation for the transactions opened on the connection with the [IsolationLevel](isolationlevel-property-ado.md) property.</span></span>

  - <span data-ttu-id="b5eb4-115">使用 [Provider](provider-property-ado.md) 属性指定 OLE DB 提供程序。</span><span class="sxs-lookup"><span data-stu-id="b5eb4-115">Specify an OLE DB provider with the [Provider](provider-property-ado.md) property.</span></span>

  - <span data-ttu-id="b5eb4-116">使用 [Open](open-method-ado-connection.md) 和 [Close](close-method-ado.md) 方法建立与数据源的物理连接，然后断开连接。</span><span class="sxs-lookup"><span data-stu-id="b5eb4-116">Establish, and later break, the physical connection to the data source with the [Open](open-method-ado-connection.md) and [Close](close-method-ado.md) methods.</span></span>

  - <span data-ttu-id="b5eb4-117">使用 [Execute](https://msdn.microsoft.com/library/jj249832\(v=office.15\)) 方法在连接上执行命令，并使用 [CommandTimeout](commandtimeout-property-ado.md) 属性配置执行。</span><span class="sxs-lookup"><span data-stu-id="b5eb4-117">Execute a command on the connection with the [Execute](https://msdn.microsoft.com/library/jj249832\(v=office.15\)) method and configure the execution with the [CommandTimeout](commandtimeout-property-ado.md) property.</span></span>
    

    > [!NOTE]
    > <span data-ttu-id="b5eb4-p103">[!注释] 若要在不使用 Command 对象的情况下执行查询，可将查询字符串传递给 **Connection** 对象的 **Execute** 方法。但是，如果要持久保留命令文本并重新执行它，或使用查询参数，则需要 [Command](command-object-ado.md) 对象。</span><span class="sxs-lookup"><span data-stu-id="b5eb4-p103">To execute a query without using a Command object, pass a query string to the **Execute** method of a **Connection** object. However, a [Command](command-object-ado.md) object is required when you want to persist the command text and re-execute it, or use query parameters.</span></span>

  - <span data-ttu-id="b5eb4-120">使用 [BeginTrans](begintrans-committrans-and-rollbacktrans-methods-ado.md)、[CommitTrans](begintrans-committrans-and-rollbacktrans-methods-ado.md) 和 [RollbackTrans](begintrans-committrans-and-rollbacktrans-methods-ado.md) 方法以及 [Attributes](attributes-property-ado.md) 属性管理打开连接上的事务（如果提供程序支持嵌套事务，则包括嵌套事务）。</span><span class="sxs-lookup"><span data-stu-id="b5eb4-120">Manage transactions on the open connection, including nested transactions if the provider supports them, with the [BeginTrans](begintrans-committrans-and-rollbacktrans-methods-ado.md), [CommitTrans](begintrans-committrans-and-rollbacktrans-methods-ado.md), and [RollbackTrans](begintrans-committrans-and-rollbacktrans-methods-ado.md) methods and the [Attributes](attributes-property-ado.md) property.</span></span>

  - <span data-ttu-id="b5eb4-121">使用 [Errors](errors-collection-ado.md) 集合检查数据源返回的错误。</span><span class="sxs-lookup"><span data-stu-id="b5eb4-121">Examine errors returned from the data source with the [Errors](errors-collection-ado.md) collection.</span></span>

  - <span data-ttu-id="b5eb4-122">使用 [Version](version-property-ado.md) 属性从所用的 ADO 实现中读取版本。</span><span class="sxs-lookup"><span data-stu-id="b5eb4-122">Read the version from the ADO implementation used with the [Version](version-property-ado.md) property.</span></span>

  - <span data-ttu-id="b5eb4-123">使用 [OpenSchema](openschema-method-ado.md) 方法获取有关数据库的架构信息。</span><span class="sxs-lookup"><span data-stu-id="b5eb4-123">Obtain schema information about your database with the [OpenSchema](openschema-method-ado.md) method.</span></span>

<span data-ttu-id="b5eb4-124">可以独立于任何其他以前定义的对象创建 **Connection** 对象。</span><span class="sxs-lookup"><span data-stu-id="b5eb4-124">You can create **Connection** objects independently of any other previously defined object.</span></span>

<span data-ttu-id="b5eb4-125">可以将命令或存储过程作为 **Connection** 对象的本地方法来执行，如下所述。</span><span class="sxs-lookup"><span data-stu-id="b5eb4-125">You can execute commands or stored procedures as if they were native methods on the **Connection** object, as illustrated below.</span></span>

### <a name="execute-a-command-as-a-native-method-of-a-connection-object"></a><span data-ttu-id="b5eb4-126">将命令作为 Connection 对象的本地方法执行</span><span class="sxs-lookup"><span data-stu-id="b5eb4-126">Execute a command as a native method of a Connection object</span></span>

<span data-ttu-id="b5eb4-p104">若要执行某个命令，请使用 **Command** 对象的 [Name](name-property-ado.md) 属性给命令命名。将 **Command** 对象的 **ActiveConnection** 属性设置为该连接。然后将使用该命令名的语句作为 **Connection** 对象的方法发出，后跟任何参数，如果返回了任何行，则后面再跟随 **Recordset** 对象。设置 **Recordset** 属性以便自定义生成的 **Recordset** 。例如：</span><span class="sxs-lookup"><span data-stu-id="b5eb4-p104">To execute a command, give the command a name using the **Command** object [Name](name-property-ado.md) property. Set the **Command** object's **ActiveConnection** property to the connection. Then issue a statement where the command name is used as if it were a method on the **Connection** object, followed by any parameters, then followed by a **Recordset** object if any rows are returned. Set the **Recordset** properties to customize the resulting **Recordset**. For example:</span></span>

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

### <a name="execute-a-stored-procedure-as-a-native-method-of-a-connection-object"></a><span data-ttu-id="b5eb4-132">将存储过程作为 Connection 对象的本地方法执行</span><span class="sxs-lookup"><span data-stu-id="b5eb4-132">Execute a stored procedure as a native method of a Connection object</span></span>

<span data-ttu-id="b5eb4-p105">若要执行某个存储过程，请将使用该存储过程的语句作为 **Connection** 对象的方法发出，后跟任何参数。ADO 将"尽量推测"参数的类型。例如：</span><span class="sxs-lookup"><span data-stu-id="b5eb4-p105">To execute a stored procedure, issue a statement where the stored procedure name is used as if it were a method on the **Connection** object, followed by any parameters. ADO will make a "best guess" of parameter types. For example:</span></span>

```vb
    Dim cnn As New ADODB.Connection
    ...
    'Your stored procedure name and any parameters.
    cnn.sp_yourStoredProcedureName "parameter"
```
