---
title: 命名空间 （访问桌面数据库参考 （英文）
TOCTitle: Namespaces
ms:assetid: e39f003c-3d16-1fae-48c5-304593c41f2f
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250158(v=office.15)
ms:contentKeyID: 48548318
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 905edba502fcc2994be6f6b8e50a7200b66a82b8
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28703004"
---
# <a name="namespaces"></a><span data-ttu-id="5f50c-102">命名空间</span><span class="sxs-lookup"><span data-stu-id="5f50c-102">Namespaces</span></span>

<span data-ttu-id="5f50c-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="5f50c-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="5f50c-104">ADO 中的 XML 持久化格式使用以下四个命名空间。</span><span class="sxs-lookup"><span data-stu-id="5f50c-104">The XML persistence format in ADO uses the following four namespaces.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="5f50c-105">前缀</span><span class="sxs-lookup"><span data-stu-id="5f50c-105">Prefix</span></span></p></th>
<th><p><span data-ttu-id="5f50c-106">说明</span><span class="sxs-lookup"><span data-stu-id="5f50c-106">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5f50c-107">s</span><span class="sxs-lookup"><span data-stu-id="5f50c-107">s</span></span></p></td>
<td><p><span data-ttu-id="5f50c-108">指的是&quot;XML 数据&quot;命名空间包含的元素和属性的定义当前<strong>Recordset</strong>的架构。</span><span class="sxs-lookup"><span data-stu-id="5f50c-108">Refers to the &quot;XML-Data&quot; namespace containing the elements and attributes that define the schema of the current <strong>Recordset</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f50c-109">dt</span><span class="sxs-lookup"><span data-stu-id="5f50c-109">dt</span></span></p></td>
<td><p><span data-ttu-id="5f50c-110">指的是数据类型定义规范。</span><span class="sxs-lookup"><span data-stu-id="5f50c-110">Refers to the data type definitions specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f50c-111">rs</span><span class="sxs-lookup"><span data-stu-id="5f50c-111">rs</span></span></p></td>
<td><p><span data-ttu-id="5f50c-112">指的是命名空间，该命名空间包含特定于 ADO <strong>Recordset</strong> 属性和特性的元素和特性。</span><span class="sxs-lookup"><span data-stu-id="5f50c-112">Refers to the namespace containing elements and attributes specific to ADO <strong>Recordset</strong> properties and attributes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f50c-113">z</span><span class="sxs-lookup"><span data-stu-id="5f50c-113">z</span></span></p></td>
<td><p><span data-ttu-id="5f50c-114">指的是当前行集的架构。</span><span class="sxs-lookup"><span data-stu-id="5f50c-114">Refers to the schema of the current rowset.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="5f50c-p101">客户端不应当向这些命名空间添加它自己的标记，因为它们是由规格定义的。例如，客户端不应当将命名空间定义为"urn:schemas-microsoft-com:rowset"，然后写出诸如"rs:MyOwnTag"这样的内容。若要详细了解命名空间，请参阅 [XML 命名空间](https://www.w3.org/tr/xml-names/)。</span><span class="sxs-lookup"><span data-stu-id="5f50c-p101">A client should not add its own tags to these namespaces, as defined by the specification. For example, a client should not define a namespace as "urn:schemas-microsoft-com:rowset" and then write out something such as "rs:MyOwnTag." To learn more about namespaces, see [XML Namespaces](https://www.w3.org/tr/xml-names/).</span></span>

> [!NOTE]
> <span data-ttu-id="5f50c-118">[!注释] 架构标记的 ID 必须是"RowsetSchema"，并且用来引用当前行集架构的命名空间必须指向"#RowsetSchema"。</span><span class="sxs-lookup"><span data-stu-id="5f50c-118">The ID for the schema tag must be "RowsetSchema," and the namespace used to refer to the schema of the current rowset must point to "#RowsetSchema."</span></span>

<span data-ttu-id="5f50c-119">注意，命名空间的前缀（即冒号右侧和等号左侧的部分）是任意的。</span><span class="sxs-lookup"><span data-stu-id="5f50c-119">Note that the prefix of the namespace, that part to the right of the colon and to the left of the equal sign, is arbitrary.</span></span>

```vb 
 
xmlns:rs="urn:schemas-microsoft-com:rowset" 
```

<span data-ttu-id="5f50c-p102">用户可以将它定义为任何名称，只要在整个 XML 文档中都一致地使用此名称。ADO 始终写出"s"、"rs"、"dt"和"z"，但这些前缀名称不会硬编码到加载组件中。</span><span class="sxs-lookup"><span data-stu-id="5f50c-p102">The user can define this to be any name as long as this name is consistently used throughout the XML document. ADO always writes out "s," "rs," "dt," and "z," but these prefix names are not hard-coded into the loading component.</span></span>



