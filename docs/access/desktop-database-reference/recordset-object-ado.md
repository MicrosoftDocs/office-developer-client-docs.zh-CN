---
title: Recordset 对象 (ADO)
TOCTitle: Recordset object (ADO)
ms:assetid: 0f963bf8-f066-dc8a-b754-f427de712df1
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248865(v=office.15)
ms:contentKeyID: 48543267
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: a99b3f792518e65900841bab90977e2edda6e804
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25927037"
---
# <a name="recordset-object-ado"></a><span data-ttu-id="f72a5-102">Recordset 对象 (ADO)</span><span class="sxs-lookup"><span data-stu-id="f72a5-102">Recordset object (ADO)</span></span>

<span data-ttu-id="f72a5-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="f72a5-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="f72a5-p101">表示从基表得到的整个记录集，或执行命令的结果。在任何时候， **Recordset** 对象只引用该集合中的单个记录作为当前记录。</span><span class="sxs-lookup"><span data-stu-id="f72a5-p101">Represents the entire set of records from a base table or the results of an executed command. At any time, the **Recordset** object refers to only a single record within the set as the current record.</span></span>

## <a name="remarks"></a><span data-ttu-id="f72a5-106">说明</span><span class="sxs-lookup"><span data-stu-id="f72a5-106">Remarks</span></span>

<span data-ttu-id="f72a5-p102">可以使用 **Recordset** 对象处理来自提供程序的数据。使用 ADO 时，几乎可以完全使用 **Recordset** 对象处理数据。所有 **Recordset** 对象都是由记录（行）和字段（列）构成的。取决于提供程序支持的功能，某些 **Recordset** 方法或属性可能不可用。</span><span class="sxs-lookup"><span data-stu-id="f72a5-p102">You use **Recordset** objects to manipulate data from a provider. When you use ADO, you manipulate data almost entirely using **Recordset** objects. All **Recordset** objects consist of records (rows) and fields (columns). Depending on the functionality supported by the provider, some **Recordset** methods or properties may not be available.</span></span>

<span data-ttu-id="f72a5-p103">ADODB.Recordset 是创建 **Recordset** 对象应使用的 ProgID。引用过时的 ADOR.Recordset ProgID 的现有应用程序将继续运行，不进行重新编译，但新开发的应用程序应引用 ADODB.Recordset。</span><span class="sxs-lookup"><span data-stu-id="f72a5-p103">ADODB.Recordset is the ProgID that should be used to create a **Recordset** object. Existing applications that reference the outdated ADOR.Recordset ProgID will continue to work without recompiling, but new development should reference ADODB.Recordset.</span></span>

<span data-ttu-id="f72a5-113">在 ADO 中定义了四种不同的游标类型：</span><span class="sxs-lookup"><span data-stu-id="f72a5-113">There are four different cursor types defined in ADO:</span></span>

  - <span data-ttu-id="f72a5-114">**动态游标** - 允许您查看其他用户所做的添加、更改和删除；允许不依赖书签的 **Recordset** 中的所有类型的活动；如果提供程序支持书签，还允许使用书签。</span><span class="sxs-lookup"><span data-stu-id="f72a5-114">**Dynamic cursor** — allows you to view additions, changes, and deletions by other users; allows all types of movement through the **Recordset** that doesn't rely on bookmarks; and allows bookmarks if the provider supports them.</span></span>

  - <span data-ttu-id="f72a5-p104">**键集游标** - 行为类似动态游标，但它不允许您查看其他用户添加的记录，并且不允许您访问其他用户删除的记录。由其他用户所作的数据更改仍然可见。它始终支持书签，因此允许 **Recordset** 中的所有类型的活动。</span><span class="sxs-lookup"><span data-stu-id="f72a5-p104">**Keyset cursor** — behaves like a dynamic cursor, except that it prevents you from seeing records that other users add, and prevents access to records that other users delete. Data changes by other users will still be visible. It always supports bookmarks and therefore allows all types of movement through the **Recordset**.</span></span>

  - <span data-ttu-id="f72a5-p105">**静态游标** - 提供记录集的静态副本，供您用来查找数据和生成报表；始终允许书签，因此允许 **Recordset** 中所有类型的活动。其他用户所做的添加、更改或删除不可见。打开客户端 **Recordset** 对象是，该游标是唯一允许的游标类型。</span><span class="sxs-lookup"><span data-stu-id="f72a5-p105">**Static cursor** — provides a static copy of a set of records for you to use to find data or generate reports; always allows bookmarks and therefore allows all types of movement through the **Recordset**. Additions, changes, or deletions by other users will not be visible. This is the only type of cursor allowed when you open a client-side **Recordset** object.</span></span>

  - <span data-ttu-id="f72a5-p106">**仅向前型游标** - 允许您在 **Recordset** 中仅向前滚动。其他用户所做的添加、更改或删除不可见。如果只需遍历 **Recordset** 一次，这样可提高性能。</span><span class="sxs-lookup"><span data-stu-id="f72a5-p106">**Forward-only cursor** — allows you to only scroll forward through the **Recordset**. Additions, changes, or deletions by other users will not be visible. This improves performance in situations where you need to make only a single pass through a **Recordset**.</span></span>

<span data-ttu-id="f72a5-124">将打开**Recordset**的游标类型，选择之前[CursorType](cursortype-property-ado.md)属性设置或使用[Open](open-method-ado-recordset.md)方法传递*CursorType*参数。</span><span class="sxs-lookup"><span data-stu-id="f72a5-124">Set the [CursorType](cursortype-property-ado.md) property prior to opening the **Recordset** to choose the cursor type, or pass a *CursorType* argument with the [Open](open-method-ado-recordset.md) method.</span></span> <span data-ttu-id="f72a5-125">某些提供程序不支持所有游标类型。</span><span class="sxs-lookup"><span data-stu-id="f72a5-125">Some providers don't support all cursor types.</span></span> <span data-ttu-id="f72a5-126">请参考提供程序的文档。</span><span class="sxs-lookup"><span data-stu-id="f72a5-126">Check the documentation for the provider.</span></span> <span data-ttu-id="f72a5-127">如果未指定游标类型，ADO 会默认打开仅向前型游标。</span><span class="sxs-lookup"><span data-stu-id="f72a5-127">If you don't specify a cursor type, ADO opens a forward-only cursor by default.</span></span>

<span data-ttu-id="f72a5-p108">如果将 [CursorLocation](cursorlocation-property-ado.md) 属性设置为 **adUseClient** 来打开 **Recordset** ，则 **Field** 对象的 [UnderlyingValue](field-object-ado.md) 属性在返回的 **Recordset** 对象中不可用。当用于某些提供程序（例如，将 Microsoft ODBC Provider for OLE DB 与 Microsoft SQL Server 结合使用）时，您可以使用 **Open** 方法传递连接字符串，独立于以前定义的 [Connection](connection-object-ado.md) 对象来创建 **Recordset** 对象。ADO 仍然创建 [Connection](connection-object-ado.md) 对象，但不将该对象分配给对象变量。不过，若要通过相同的连接打开多个 **Recordset** 对象，则应显式创建和打开 **Connection** 对象；这样就会将 **Connection** 对象分配给对象变量。如果打开 **Recordset** 对象时不使用该对象变量，ADO 会为每个新 **Recordset** 创建一个新 **Connection** 对象，即使您传递的是同一个连接字符串。</span><span class="sxs-lookup"><span data-stu-id="f72a5-p108">If the [CursorLocation](cursorlocation-property-ado.md) property is set to **adUseClient** to open a **Recordset**, the **UnderlyingValue** property on [Field](field-object-ado.md) objects is not available in the returned **Recordset** object. When used with some providers (such as the Microsoft ODBC Provider for OLE DB in conjunction with Microsoft SQL Server), you can create **Recordset** objects independently of a previously defined [Connection](connection-object-ado.md) object by passing a connection string with the **Open** method. ADO still creates a [Connection](connection-object-ado.md) object, but it doesn't assign that object to an object variable. However, if you are opening multiple **Recordset** objects over the same connection, you should explicitly create and open a **Connection** object; this assigns the **Connection** object to an object variable. If you do not use this object variable when opening your **Recordset** objects, ADO creates a new **Connection** object for each new **Recordset**, even if you pass the same connection string.</span></span>

<span data-ttu-id="f72a5-133">可根据需要创建任意数目的 **Recordset** 对象。</span><span class="sxs-lookup"><span data-stu-id="f72a5-133">You can create as many **Recordset** objects as needed.</span></span>

<span data-ttu-id="f72a5-p109">当您打开 **Recordset** 时，当前记录会位于第一条记录（如果有）的位置，并且 [BOF](bof-eof-properties-ado.md) 和 [EOF](bof-eof-properties-ado.md) 属性设置为 **False** 。如果没有任何记录， **BOF** 和 **EOF** 属性设置为 **True** 。</span><span class="sxs-lookup"><span data-stu-id="f72a5-p109">When you open a **Recordset**, the current record is positioned to the first record (if any) and the [BOF](bof-eof-properties-ado.md) and [EOF](bof-eof-properties-ado.md) properties are set to **False**. If there are no records, the **BOF** and **EOF** property settings are **True**.</span></span>

<span data-ttu-id="f72a5-p110">可以使用 [MoveFirst](movefirst-movelast-movenext-and-moveprevious-methods-ado.md)、**MoveLast**、**MoveNext** 和 **MovePrevious** 方法；[Move](move-method-ado.md) 方法；以及 [AbsolutePosition](absoluteposition-property-ado.md)、[AbsolutePage](absolutepage-property-ado.md) 和 [Filter](filter-property-ado.md) 属性来重新定位当前记录，前提是提供程序支持相关功能。仅向前型 **Recordset** 对象仅支持 [MoveNext](movefirst-movelast-movenext-and-moveprevious-methods-ado.md) 方法。当使用 **Move** 方法访问每条记录（或枚举 **Recordset**）时，可以使用 **BOF** 和 **EOF** 确定是否移到了 **Recordset** 的开头或结尾之外。</span><span class="sxs-lookup"><span data-stu-id="f72a5-p110">You can use the [MoveFirst](movefirst-movelast-movenext-and-moveprevious-methods-ado.md), **MoveLast**, **MoveNext**, and **MovePrevious** methods; the [Move](move-method-ado.md) method; and the [AbsolutePosition](absoluteposition-property-ado.md), [AbsolutePage](absolutepage-property-ado.md), and [Filter](filter-property-ado.md) properties to reposition the current record, assuming the provider supports the relevant functionality. Forward-only **Recordset** objects support only the [MoveNext](movefirst-movelast-movenext-and-moveprevious-methods-ado.md) method. When you use the **Move** methods to visit each record (or enumerate the **Recordset**), you can use the **BOF** and **EOF** properties to determine if you've moved beyond the beginning or end of the **Recordset**.</span></span>

<span data-ttu-id="f72a5-p111">**Recordset** 对象可支持两种类型的更新：即时更新和批更新。在即时更新中，调用 [Update](update-method-ado.md) 方法时，对数据所做的所有更改会立即写入基础数据源。您还可以使用 [AddNew](addnew-method-ado.md) 和 **Update** 方法将值数组作为参数传递，并同时更新记录中的多个字段。</span><span class="sxs-lookup"><span data-stu-id="f72a5-p111">**Recordset** objects can support two types of updating: immediate and batched. In immediate updating, all changes to data are written immediately to the underlying data source once you call the [Update](update-method-ado.md) method. You can also pass arrays of values as parameters with the [AddNew](addnew-method-ado.md) and **Update** methods and simultaneously update several fields in a record.</span></span>

<span data-ttu-id="f72a5-p112">如果提供程序支持批更新，则可以让提供程序缓存对多个记录所做的更改，然后使用 [UpdateBatch](updatebatch-method-ado.md) 方法通过对数据库的一次调用传送这些更改。这适用于通过 **AddNew** 、 **Update** 和 [Delete](delete-method-ado-recordset.md) 方法所做的更改。调用 **UpdateBatch** 方法后，可以使用 [Status](status-property-ado-recordset.md) 属性检查任何数据冲突，以便进行解决。</span><span class="sxs-lookup"><span data-stu-id="f72a5-p112">If a provider supports batch updating, you can have the provider cache changes to more than one record and then transmit them in a single call to the database with the [UpdateBatch](updatebatch-method-ado.md) method. This applies to changes made with the **AddNew**, **Update**, and [Delete](delete-method-ado-recordset.md) methods. After you call the **UpdateBatch** method, you can use the [Status](status-property-ado-recordset.md) property to check for any data conflicts in order to resolve them.</span></span>

> [!NOTE]
> <span data-ttu-id="f72a5-p113">[!注释] 若要在不使用 [Command](command-object-ado.md) 对象的情况下执行查询，可将查询字符串传递给 **Recordset** 对象的 **Open** 方法。但是，如果要持久保留命令文本并重新执行它，或使用查询参数，则使用 **Command** 对象。</span><span class="sxs-lookup"><span data-stu-id="f72a5-p113">To execute a query without using a [Command](command-object-ado.md) object, pass a query string to the **Open** method of a **Recordset** object. However, a **Command** object is required when you want to persist the command text and re-execute it, or use query parameters.</span></span>

<span data-ttu-id="f72a5-147">[Mode](mode-property-ado.md) 属性控制访问权限。</span><span class="sxs-lookup"><span data-stu-id="f72a5-147">The [Mode](mode-property-ado.md) property governs access permissions.</span></span>

<span data-ttu-id="f72a5-p114">**Fields** 集合是 **Recordset** 对象的默认成员。因此，以下两个代码语句是等效的。</span><span class="sxs-lookup"><span data-stu-id="f72a5-p114">The **Fields** collection is the default member of the **Recordset** object. As a result, the following two code statements are equivalent.</span></span>

```vb
    Debug.Print objRs.Fields.Item(0)  ' Both statements print 
    Debug.Print objRs(0)              '  the Value of Item(0).
```
