---
title: Fields 集合 (ADO)
TOCTitle: Fields collection (ADO)
ms:assetid: 029aa738-8726-54a6-1813-b152813948bc
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248791(v=office.15)
ms:contentKeyID: 48542962
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 39c801e223eba83a8de6aa7dacda6d8296e77588
ms.sourcegitcommit: 38d0db57580cc5f4a0231c27b1643f8db5431ca3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25936971"
---
# <a name="fields-collection-ado"></a><span data-ttu-id="b09cd-102">Fields 集合 (ADO)</span><span class="sxs-lookup"><span data-stu-id="b09cd-102">Fields collection (ADO)</span></span>


<span data-ttu-id="b09cd-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="b09cd-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="b09cd-104">包含 [Recordset](field-object-ado.md) 或 [Record](recordset-object-ado.md) 对象的所有 [Field](record-object-ado.md) 对象。</span><span class="sxs-lookup"><span data-stu-id="b09cd-104">Contains all the [Field](field-object-ado.md) objects of a [Recordset](recordset-object-ado.md) or [Record](record-object-ado.md) object.</span></span>

## <a name="remarks"></a><span data-ttu-id="b09cd-105">说明</span><span class="sxs-lookup"><span data-stu-id="b09cd-105">Remarks</span></span>

<span data-ttu-id="b09cd-p101">**Recordset** 对象具有由 **Field** 对象组成的 **Fields** 集合。每个 **Field** 对应于 **Recordset** 中的一个列。在打开 **Recordset** 之前，您可以通过对 **Fields** 集合调用 [Refresh](refresh-method-ado.md) 方法来填充该集合。</span><span class="sxs-lookup"><span data-stu-id="b09cd-p101">A **Recordset** object has a **Fields** collection made up of **Field** objects. Each **Field** object corresponds to a column in the **Recordset**. You can populate the **Fields** collection before opening the **Recordset** by calling the [Refresh](refresh-method-ado.md) method on the collection.</span></span>

> [!NOTE]
> <span data-ttu-id="b09cd-109">[!注释] 有关如何使用 **Field** 对象的更详细解释，请参阅 **Field** 对象主题。</span><span class="sxs-lookup"><span data-stu-id="b09cd-109">See the **Field** object topic for a more detailed explanation of how to use **Field** objects.</span></span>

<span data-ttu-id="b09cd-110">**Fields** 集合具有 [Append](append-method-ado.md) 方法（该方法会在集合中临时创建并添加一个 **Field** 对象）和 **Update** 方法（该方法会终止任何添加或删除）。</span><span class="sxs-lookup"><span data-stu-id="b09cd-110">The **Fields** collection has an [Append](append-method-ado.md) method, which provisionally creates and adds a **Field** object to the collection, and an **Update** method, which finalizes any additions or deletions.</span></span>

<span data-ttu-id="b09cd-p102">**Record** 对象具有两个可以通过 [FieldEnum](fieldenum.md) 常量进行索引的特殊字段。一个常量访问包含 **Record** 的默认流的字段，另一个常量访问包含 **Record** 的绝对 URL 字符串的字段。</span><span class="sxs-lookup"><span data-stu-id="b09cd-p102">A **Record** object has two special fields that can be indexed with [FieldEnum](fieldenum.md) constants. One constant accesses a field containing the default stream for the **Record**, and the other accesses a field containing the absolute URL string for the **Record**.</span></span>

<span data-ttu-id="b09cd-p103">某些提供程序（例如，[Microsoft OLE DB Provider for Internet Publishing](microsoft-ole-db-provider-for-internet-publishing.md)）可以使用 **Record** 或 **Recordset** 的可用字段的子集来填充 **Fields** 集合。在用名称首次引用或由代码首次索引之前，其他字段不会添加到集合中。</span><span class="sxs-lookup"><span data-stu-id="b09cd-p103">Certain providers (for example, the [Microsoft OLE DB Provider for Internet Publishing](microsoft-ole-db-provider-for-internet-publishing.md)) may populate the **Fields** collection with a subset of available fields for the **Record** or **Recordset**. Other fields will not be added to the collection until they are first referenced by name or indexed by your code.</span></span>

<span data-ttu-id="b09cd-p104">如果尝试用名称引用一个不存在的字段，则在 **Fields** 中将追加一个新的 **Field** 对象，其 [Status](status-property-ado-field.md) 为 **adFieldPendingInsert** 。调用 [Update](update-method-ado.md) 时，如果提供程序允许，ADO 将在数据源中创建新字段。</span><span class="sxs-lookup"><span data-stu-id="b09cd-p104">If you attempt to reference a nonexistent field by name, a new **Field** object will be appended to the **Fields** collection with a [Status](status-property-ado-field.md) of **adFieldPendingInsert**. When you call [Update](update-method-ado.md), ADO will create a new field in your data source if allowed by your provider.</span></span>

