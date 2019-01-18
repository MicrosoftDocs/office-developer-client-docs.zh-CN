---
title: Recordset 对象 (ADO)
TOCTitle: Recordset object (ADO)
ms:assetid: 0f963bf8-f066-dc8a-b754-f427de712df1
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248865(v=office.15)
ms:contentKeyID: 48543267
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 636681cf8e0c20f078387b21974141a9cb66cfcd
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28719993"
---
# <a name="recordset-object-ado"></a>Recordset 对象 (ADO)

**适用于**： Access 2013、 Office 2013

表示从基表得到的整个记录集，或执行命令的结果。在任何时候， **Recordset** 对象只引用该集合中的单个记录作为当前记录。

## <a name="remarks"></a>说明

可以使用 **Recordset** 对象处理来自提供程序的数据。使用 ADO 时，几乎可以完全使用 **Recordset** 对象处理数据。所有 **Recordset** 对象都是由记录（行）和字段（列）构成的。取决于提供程序支持的功能，某些 **Recordset** 方法或属性可能不可用。

ADODB.Recordset 是创建 **Recordset** 对象应使用的 ProgID。引用过时的 ADOR.Recordset ProgID 的现有应用程序将继续运行，不进行重新编译，但新开发的应用程序应引用 ADODB.Recordset。

在 ADO 中定义了四种不同的游标类型：

  - **动态游标** - 允许您查看其他用户所做的添加、更改和删除；允许不依赖书签的 **Recordset** 中的所有类型的活动；如果提供程序支持书签，还允许使用书签。

  - **键集游标** - 行为类似动态游标，但它不允许您查看其他用户添加的记录，并且不允许您访问其他用户删除的记录。由其他用户所作的数据更改仍然可见。它始终支持书签，因此允许 **Recordset** 中的所有类型的活动。

  - **静态游标** - 提供记录集的静态副本，供您用来查找数据和生成报表；始终允许书签，因此允许 **Recordset** 中所有类型的活动。其他用户所做的添加、更改或删除不可见。打开客户端 **Recordset** 对象是，该游标是唯一允许的游标类型。

  - **仅向前型游标** - 允许您在 **Recordset** 中仅向前滚动。其他用户所做的添加、更改或删除不可见。如果只需遍历 **Recordset** 一次，这样可提高性能。

将打开**Recordset**的游标类型，选择之前[CursorType](cursortype-property-ado.md)属性设置或使用[Open](open-method-ado-recordset.md)方法传递*CursorType*参数。 某些提供程序不支持所有游标类型。 请参考提供程序的文档。 如果未指定游标类型，ADO 会默认打开仅向前型游标。

如果将 [CursorLocation](cursorlocation-property-ado.md) 属性设置为 **adUseClient** 来打开 **Recordset** ，则 **Field** 对象的 [UnderlyingValue](field-object-ado.md) 属性在返回的 **Recordset** 对象中不可用。当用于某些提供程序（例如，将 Microsoft ODBC Provider for OLE DB 与 Microsoft SQL Server 结合使用）时，您可以使用 **Open** 方法传递连接字符串，独立于以前定义的 [Connection](connection-object-ado.md) 对象来创建 **Recordset** 对象。ADO 仍然创建 [Connection](connection-object-ado.md) 对象，但不将该对象分配给对象变量。不过，若要通过相同的连接打开多个 **Recordset** 对象，则应显式创建和打开 **Connection** 对象；这样就会将 **Connection** 对象分配给对象变量。如果打开 **Recordset** 对象时不使用该对象变量，ADO 会为每个新 **Recordset** 创建一个新 **Connection** 对象，即使您传递的是同一个连接字符串。

可根据需要创建任意数目的 **Recordset** 对象。

当您打开 **Recordset** 时，当前记录会位于第一条记录（如果有）的位置，并且 [BOF](bof-eof-properties-ado.md) 和 [EOF](bof-eof-properties-ado.md) 属性设置为 **False** 。如果没有任何记录， **BOF** 和 **EOF** 属性设置为 **True** 。

可以使用 [MoveFirst](movefirst-movelast-movenext-and-moveprevious-methods-ado.md)、**MoveLast**、**MoveNext** 和 **MovePrevious** 方法；[Move](move-method-ado.md) 方法；以及 [AbsolutePosition](absoluteposition-property-ado.md)、[AbsolutePage](absolutepage-property-ado.md) 和 [Filter](filter-property-ado.md) 属性来重新定位当前记录，前提是提供程序支持相关功能。仅向前型 **Recordset** 对象仅支持 [MoveNext](movefirst-movelast-movenext-and-moveprevious-methods-ado.md) 方法。当使用 **Move** 方法访问每条记录（或枚举 **Recordset**）时，可以使用 **BOF** 和 **EOF** 确定是否移到了 **Recordset** 的开头或结尾之外。

**Recordset** 对象可支持两种类型的更新：即时更新和批更新。在即时更新中，调用 [Update](update-method-ado.md) 方法时，对数据所做的所有更改会立即写入基础数据源。您还可以使用 [AddNew](addnew-method-ado.md) 和 **Update** 方法将值数组作为参数传递，并同时更新记录中的多个字段。

如果提供程序支持批更新，则可以让提供程序缓存对多个记录所做的更改，然后使用 [UpdateBatch](updatebatch-method-ado.md) 方法通过对数据库的一次调用传送这些更改。这适用于通过 **AddNew** 、 **Update** 和 [Delete](delete-method-ado-recordset.md) 方法所做的更改。调用 **UpdateBatch** 方法后，可以使用 [Status](status-property-ado-recordset.md) 属性检查任何数据冲突，以便进行解决。

> [!NOTE]
> [!注释] 若要在不使用 [Command](command-object-ado.md) 对象的情况下执行查询，可将查询字符串传递给 **Recordset** 对象的 **Open** 方法。但是，如果要持久保留命令文本并重新执行它，或使用查询参数，则使用 **Command** 对象。

[Mode](mode-property-ado.md) 属性控制访问权限。

**Fields** 集合是 **Recordset** 对象的默认成员。因此，以下两个代码语句是等效的。

```vb
    Debug.Print objRs.Fields.Item(0)  ' Both statements print 
    Debug.Print objRs(0)              '  the Value of Item(0).
```
