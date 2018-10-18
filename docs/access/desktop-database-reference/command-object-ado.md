---
title: Command 对象 (ADO)
TOCTitle: Command Object (ADO)
ms:assetid: 64f4ef03-f858-c004-b891-0c96d13a5e6e
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249389(v=office.15)
ms:contentKeyID: 48545303
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- ado210.chm1231106
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 5199037f44e75bddf697197bca992a95b8432420
ms.sourcegitcommit: a49b77f4c8cec69f90656a86f0872cf34c35968e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2018
ms.locfileid: "25605742"
---
# <a name="command-object-ado"></a><span data-ttu-id="1da2c-102">Command 对象 (ADO)</span><span class="sxs-lookup"><span data-stu-id="1da2c-102">Command Object (ADO)</span></span>


<span data-ttu-id="1da2c-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="1da2c-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="1da2c-104">定义要对数据源执行的特定命令。</span><span class="sxs-lookup"><span data-stu-id="1da2c-104">Defines a specific command that you intend to execute against a data source.</span></span>

## <a name="remarks"></a><span data-ttu-id="1da2c-105">说明</span><span class="sxs-lookup"><span data-stu-id="1da2c-105">Remarks</span></span>

<span data-ttu-id="1da2c-p101">使用 **Command** 对象可查询数据库并通过 [Recordset](recordset-object-ado.md) 对象返回记录，执行批量操作或处理数据库的结构。根据提供程序功能的不同，引用某些 **Command** 集合、方法或属性时，可能生成错误。</span><span class="sxs-lookup"><span data-stu-id="1da2c-p101">Use a **Command** object to query a database and return records in a [Recordset](recordset-object-ado.md) object, to execute a bulk operation, or to manipulate the structure of a database. Depending on the functionality of the provider, some **Command** collections, methods, or properties may generate an error when referenced.</span></span>

<span data-ttu-id="1da2c-108">使用 **Command** 对象的集合、方法和属性，可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="1da2c-108">With the collections, methods, and properties of a **Command** object, you can do the following:</span></span>

  - <span data-ttu-id="1da2c-109">使用 [CommandText](commandtext-property-ado.md) 属性可定义命令的可执行文本（如一条 SQL 语句）。</span><span class="sxs-lookup"><span data-stu-id="1da2c-109">Define the executable text of the command (for example, an SQL statement) with the [CommandText](commandtext-property-ado.md) property.</span></span>

  - <span data-ttu-id="1da2c-110">使用 [Parameter](parameter-object-ado.md) 对象和 [Parameters](parameters-collection-ado.md) 集合可定义参数化查询或存储过程参数。</span><span class="sxs-lookup"><span data-stu-id="1da2c-110">Define parameterized queries or stored-procedure arguments with [Parameter](parameter-object-ado.md) objects and the [Parameters](parameters-collection-ado.md) collection.</span></span>

<span data-ttu-id="1da2c-111"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="1da2c-111"><<<<<<< HEAD</span></span>
  - <span data-ttu-id="1da2c-112">使用 **Execute** 方法可执行命令并返回 [Recordset](https://msdn.microsoft.com/library/jj248785\(v=office.15\)) 对象（如果适用）。</span><span class="sxs-lookup"><span data-stu-id="1da2c-112">Execute a command and return a **Recordset** object if appropriate with the [Execute](https://msdn.microsoft.com/library/jj248785\(v=office.15\)) method.</span></span>
=======
  - <span data-ttu-id="1da2c-113">使用 **Execute** 方法可执行命令并返回 [Recordset](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/execute-method-ado-command) 对象（如果适用）。</span><span class="sxs-lookup"><span data-stu-id="1da2c-113">Execute a command and return a **Recordset** object if appropriate with the [Execute](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/execute-method-ado-command) method.</span></span>
>>>>>>> <span data-ttu-id="1da2c-114">master</span><span class="sxs-lookup"><span data-stu-id="1da2c-114">master</span></span>

  - <span data-ttu-id="1da2c-115">在执行命令之前，使用 [CommandType](commandtype-property-ado.md) 属性指定命令的类型可优化性能。</span><span class="sxs-lookup"><span data-stu-id="1da2c-115">Specify the type of command with the [CommandType](commandtype-property-ado.md) property prior to execution to optimize performance.</span></span>

  - <span data-ttu-id="1da2c-116">使用 [Prepared](prepared-property-ado.md) 属性可控制提供程序是否在执行命令之前保存命令的预备（或已编译）版本。</span><span class="sxs-lookup"><span data-stu-id="1da2c-116">Control whether the provider saves a prepared (or compiled) version of the command prior to execution with the [Prepared](prepared-property-ado.md) property.</span></span>

  - <span data-ttu-id="1da2c-117">使用 [CommandTimeout](commandtimeout-property-ado.md) 属性可设置提供程序等待命令执行的秒数。</span><span class="sxs-lookup"><span data-stu-id="1da2c-117">Set the number of seconds that a provider will wait for a command to execute with the [CommandTimeout](commandtimeout-property-ado.md) property.</span></span>

  - <span data-ttu-id="1da2c-118">通过设置 **Command** 对象的 [ActiveConnection](activeconnection-property-ado.md) 属性，可将打开的连接与该对象关联。</span><span class="sxs-lookup"><span data-stu-id="1da2c-118">Associate an open connection with a **Command** object by setting its [ActiveConnection](activeconnection-property-ado.md) property.</span></span>

  - <span data-ttu-id="1da2c-119">设置 [Name](name-property-ado.md) 属性将 **Command** 对象标识为相关联的 [Connection](connection-object-ado.md) 对象的方法。</span><span class="sxs-lookup"><span data-stu-id="1da2c-119">Set the [Name](name-property-ado.md) property to identify the **Command** object as a method on the associated [Connection](connection-object-ado.md) object.</span></span>

  - <span data-ttu-id="1da2c-120">将 **Command** 对象传递给 [Recordset](source-property-ado-recordset.md) 对象的 **Source** 属性可获取数据。</span><span class="sxs-lookup"><span data-stu-id="1da2c-120">Pass a **Command** object to the [Source](source-property-ado-recordset.md) property of a **Recordset** in order to obtain data.</span></span>

  - <span data-ttu-id="1da2c-121">使用 [Properties](properties-collection-ado.md) 集合可访问特定于提供程序的属性。</span><span class="sxs-lookup"><span data-stu-id="1da2c-121">Access provider-specific attributes with the [Properties](properties-collection-ado.md) collection.</span></span>


> [!NOTE]
> <P><span data-ttu-id="1da2c-p102">[!注释] 若要在不使用 <STRONG>Command</STRONG> 对象的情况下执行查询，可将查询字符串传递给 <A href="https://msdn.microsoft.com/library/jj249832(v=office.15)">Connection</A> 对象的 <STRONG>Execute</STRONG> 方法或 <A href="open-method-ado-recordset.md">Recordset</A> 对象的 <STRONG>Open</STRONG> 方法。但是，如果要持久保留命令文本并重新执行它，或使用查询参数，则需要 <STRONG>Command</STRONG> 对象。</span><span class="sxs-lookup"><span data-stu-id="1da2c-p102">To execute a query without using a <STRONG>Command</STRONG> object, pass a query string to the <A href="https://msdn.microsoft.com/library/jj249832(v=office.15)">Execute</A> method of a <STRONG>Connection</STRONG> object or to the <A href="open-method-ado-recordset.md">Open</A> method of a <STRONG>Recordset</STRONG> object. However, a <STRONG>Command</STRONG> object is required when you want to persist the command text and re-execute it, or use query parameters.</span></span></P>



<span data-ttu-id="1da2c-p103">若要独立于以前定义的 **Connection** 对象创建 **Command** 对象，请将 Command 对象的 **ActiveConnection** 属性设置为有效的连接字符串。ADO 仍然创建 **Connection** 对象，但不将该对象分配给对象变量。但是，如果将多个 **Command** 对象与同一连接关联，则应显式创建和打开 **Connection** 对象；这样就会将 **Connection** 对象分配给对象变量。如果不将 **Command** 对象的 **ActiveConnection** 属性设置为该对象变量，ADO 就会为每个 **Command** 对象创建一个新的 **Connection** 对象，即便使用相同的连接字符串也是如此。</span><span class="sxs-lookup"><span data-stu-id="1da2c-p103">To create a **Command** object independently of a previously defined **Connection** object, set its **ActiveConnection** property to a valid connection string. ADO still creates a **Connection** object, but it doesn't assign that object to an object variable. However, if you are associating multiple **Command** objects with the same connection, you should explicitly create and open a **Connection** object; this assigns the **Connection** object to an object variable. If you do not set the **Command** object's **ActiveConnection** property to this object variable, ADO creates a new **Connection** object for each **Command** object, even if you use the same connection string.</span></span>

<span data-ttu-id="1da2c-p104">若要执行 **Command** ，只需通过其关联的 [Connection](name-property-ado.md) 对象的 **Name** 属性调用它即可。 **Command** 的 **ActiveConnection** 属性必须设置为 **Connection** 对象。如果 **Command** 具有参数，请将它们的值作为参数传递给方法。</span><span class="sxs-lookup"><span data-stu-id="1da2c-p104">To execute a **Command**, simply call it by its [Name](name-property-ado.md) property on the associated **Connection** object. The **Command** must have its **ActiveConnection** property set to the **Connection** object. If the **Command** has parameters, pass their values as arguments to the method.</span></span>

<span data-ttu-id="1da2c-p105">在同一连接上执行两个或多个 **Command** 对象时，如果任一 **Command** 对象是具有输出参数的存储过程，将产生错误。若要执行每个 **Command** 对象，可使用单独的连接或将其他所有 **Command** 对象与该连接断开。</span><span class="sxs-lookup"><span data-stu-id="1da2c-p105">If two or more **Command** objects are executed on the same connection and either **Command** object is a stored procedure with output parameters, an error occurs. To execute each **Command** object, use separate connections or disconnect all other **Command** objects from the connection.</span></span>

<span data-ttu-id="1da2c-p106">**Parameters** 集合是 **Command** 对象的默认成员。因此，以下两个代码语句是等效的。</span><span class="sxs-lookup"><span data-stu-id="1da2c-p106">The **Parameters** collection is the default member of the **Command** object. As a result, the following two code statements are equivalent.</span></span>

