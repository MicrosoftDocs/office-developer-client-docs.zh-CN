---
title: 命名空间 （访问桌面数据库参考 （英文）
TOCTitle: Namespaces
ms:assetid: e39f003c-3d16-1fae-48c5-304593c41f2f
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250158(v=office.15)
ms:contentKeyID: 48548318
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: ef37f04ec6824cedf773cb72751b2364d2b3edf8
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25876559"
---
# <a name="namespaces"></a><span data-ttu-id="e4457-102">命名空间</span><span class="sxs-lookup"><span data-stu-id="e4457-102">Namespaces</span></span>


<span data-ttu-id="e4457-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="e4457-103">**Applies to**: Access 2013, Office 2013</span></span>

## <a name="namespaces"></a><span data-ttu-id="e4457-104">命名空间</span><span class="sxs-lookup"><span data-stu-id="e4457-104">Namespaces</span></span>

<span data-ttu-id="e4457-105">ADO 中的 XML 持久化格式使用以下四个命名空间。</span><span class="sxs-lookup"><span data-stu-id="e4457-105">The XML persistence format in ADO uses the following four namespaces.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="e4457-106">前缀</span><span class="sxs-lookup"><span data-stu-id="e4457-106">Prefix</span></span></p></th>
<th><p><span data-ttu-id="e4457-107">说明</span><span class="sxs-lookup"><span data-stu-id="e4457-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e4457-108">s</span><span class="sxs-lookup"><span data-stu-id="e4457-108">s</span></span></p></td>
<td><p><span data-ttu-id="e4457-109">指的是&quot;XML 数据&quot;命名空间包含的元素和属性的定义当前<strong>Recordset</strong>的架构。</span><span class="sxs-lookup"><span data-stu-id="e4457-109">Refers to the &quot;XML-Data&quot; namespace containing the elements and attributes that define the schema of the current <strong>Recordset</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e4457-110">dt</span><span class="sxs-lookup"><span data-stu-id="e4457-110">dt</span></span></p></td>
<td><p><span data-ttu-id="e4457-111">指的是数据类型定义规范。</span><span class="sxs-lookup"><span data-stu-id="e4457-111">Refers to the data type definitions specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e4457-112">rs</span><span class="sxs-lookup"><span data-stu-id="e4457-112">rs</span></span></p></td>
<td><p><span data-ttu-id="e4457-113">指的是命名空间，该命名空间包含特定于 ADO <strong>Recordset</strong> 属性和特性的元素和特性。</span><span class="sxs-lookup"><span data-stu-id="e4457-113">Refers to the namespace containing elements and attributes specific to ADO <strong>Recordset</strong> properties and attributes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e4457-114">z</span><span class="sxs-lookup"><span data-stu-id="e4457-114">z</span></span></p></td>
<td><p><span data-ttu-id="e4457-115">指的是当前行集的架构。</span><span class="sxs-lookup"><span data-stu-id="e4457-115">Refers to the schema of the current rowset.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="e4457-p101">客户端不应当向这些命名空间添加它自己的标记，因为它们是由规格定义的。例如，客户端不应当将命名空间定义为"urn:schemas-microsoft-com:rowset"，然后写出诸如"rs:MyOwnTag"这样的内容。若要详细了解命名空间，请参阅 [XML 命名空间](https://www.w3.org/tr/xml-names/)。</span><span class="sxs-lookup"><span data-stu-id="e4457-p101">A client should not add its own tags to these namespaces, as defined by the specification. For example, a client should not define a namespace as "urn:schemas-microsoft-com:rowset" and then write out something such as "rs:MyOwnTag." To learn more about namespaces, see [XML Namespaces](https://www.w3.org/tr/xml-names/).</span></span>


> [!NOTE]
> <P><span data-ttu-id="e4457-119">[!注释] 架构标记的 ID 必须是"RowsetSchema"，并且用来引用当前行集架构的命名空间必须指向"#RowsetSchema"。</span><span class="sxs-lookup"><span data-stu-id="e4457-119">The ID for the schema tag must be "RowsetSchema," and the namespace used to refer to the schema of the current rowset must point to "#RowsetSchema."</span></span></P>



<span data-ttu-id="e4457-120">注意，命名空间的前缀（即冒号右侧和等号左侧的部分）是任意的。</span><span class="sxs-lookup"><span data-stu-id="e4457-120">Note that the prefix of the namespace, that part to the right of the colon and to the left of the equal sign, is arbitrary.</span></span>

```vb 
 
xmlns:rs="urn:schemas-microsoft-com:rowset" 
```

<span data-ttu-id="e4457-p102">用户可以将它定义为任何名称，只要在整个 XML 文档中都一致地使用此名称。ADO 始终写出"s"、"rs"、"dt"和"z"，但这些前缀名称不会硬编码到加载组件中。</span><span class="sxs-lookup"><span data-stu-id="e4457-p102">The user can define this to be any name as long as this name is consistently used throughout the XML document. ADO always writes out "s," "rs," "dt," and "z," but these prefix names are not hard-coded into the loading component.</span></span>

## <a name="namespaces"></a><span data-ttu-id="e4457-123">命名空间</span><span class="sxs-lookup"><span data-stu-id="e4457-123">Namespaces</span></span>

<span data-ttu-id="e4457-124">ADO 中的 XML 持久化格式使用以下四个命名空间。</span><span class="sxs-lookup"><span data-stu-id="e4457-124">The XML persistence format in ADO uses the following four namespaces.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="e4457-125">前缀</span><span class="sxs-lookup"><span data-stu-id="e4457-125">Prefix</span></span></p></th>
<th><p><span data-ttu-id="e4457-126">说明</span><span class="sxs-lookup"><span data-stu-id="e4457-126">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e4457-127">s</span><span class="sxs-lookup"><span data-stu-id="e4457-127">s</span></span></p></td>
<td><p><span data-ttu-id="e4457-128">指的是&quot;XML 数据&quot;命名空间包含的元素和属性的定义当前<strong>Recordset</strong>的架构。</span><span class="sxs-lookup"><span data-stu-id="e4457-128">Refers to the &quot;XML-Data&quot; namespace containing the elements and attributes that define the schema of the current <strong>Recordset</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e4457-129">dt</span><span class="sxs-lookup"><span data-stu-id="e4457-129">dt</span></span></p></td>
<td><p><span data-ttu-id="e4457-130">指的是数据类型定义规范。</span><span class="sxs-lookup"><span data-stu-id="e4457-130">Refers to the data type definitions specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e4457-131">rs</span><span class="sxs-lookup"><span data-stu-id="e4457-131">rs</span></span></p></td>
<td><p><span data-ttu-id="e4457-132">指的是命名空间，该命名空间包含特定于 ADO <strong>Recordset</strong> 属性和特性的元素和特性。</span><span class="sxs-lookup"><span data-stu-id="e4457-132">Refers to the namespace containing elements and attributes specific to ADO <strong>Recordset</strong> properties and attributes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e4457-133">z</span><span class="sxs-lookup"><span data-stu-id="e4457-133">z</span></span></p></td>
<td><p><span data-ttu-id="e4457-134">指的是当前行集的架构。</span><span class="sxs-lookup"><span data-stu-id="e4457-134">Refers to the schema of the current rowset.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="e4457-p103">客户端不应当向这些命名空间添加它自己的标记，因为它们是由规格定义的。例如，客户端不应当将命名空间定义为"urn:schemas-microsoft-com:rowset"，然后写出诸如"rs:MyOwnTag"这样的内容。若要详细了解命名空间，请参阅 [XML 命名空间](https://www.w3.org/tr/xml-names/)。</span><span class="sxs-lookup"><span data-stu-id="e4457-p103">A client should not add its own tags to these namespaces, as defined by the specification. For example, a client should not define a namespace as "urn:schemas-microsoft-com:rowset" and then write out something such as "rs:MyOwnTag." To learn more about namespaces, see [XML Namespaces](https://www.w3.org/tr/xml-names/).</span></span>


> [!NOTE]
> <P><span data-ttu-id="e4457-138">[!注释] 架构标记的 ID 必须是"RowsetSchema"，并且用来引用当前行集架构的命名空间必须指向"#RowsetSchema"。</span><span class="sxs-lookup"><span data-stu-id="e4457-138">The ID for the schema tag must be "RowsetSchema," and the namespace used to refer to the schema of the current rowset must point to "#RowsetSchema."</span></span></P>



<span data-ttu-id="e4457-139">注意，命名空间的前缀（即冒号右侧和等号左侧的部分）是任意的。</span><span class="sxs-lookup"><span data-stu-id="e4457-139">Note that the prefix of the namespace, that part to the right of the colon and to the left of the equal sign, is arbitrary.</span></span>

```vb 
 
xmlns:rs="urn:schemas-microsoft-com:rowset" 
```

<span data-ttu-id="e4457-p104">用户可以将它定义为任何名称，只要在整个 XML 文档中都一致地使用此名称。ADO 始终写出"s"、"rs"、"dt"和"z"，但这些前缀名称不会硬编码到加载组件中。</span><span class="sxs-lookup"><span data-stu-id="e4457-p104">The user can define this to be any name as long as this name is consistently used throughout the XML document. ADO always writes out "s," "rs," "dt," and "z," but these prefix names are not hard-coded into the loading component.</span></span>

