---
title: ADO 对象和接口
TOCTitle: ADO Objects and Interfaces
ms:assetid: bebf4a80-8b6e-c43c-4138-897055cc60d3
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249927(v=office.15)
ms:contentKeyID: 48547471
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: ce04896e6ae59af6917497d9e37dc1ae97222eff
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25465874"
---
# <a name="ado-objects-and-interfaces"></a><span data-ttu-id="2415e-102">ADO 对象和接口</span><span class="sxs-lookup"><span data-stu-id="2415e-102">ADO Objects and Interfaces</span></span>


<span data-ttu-id="2415e-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="2415e-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="2415e-104">ADO 对象模型展示了这些对象之间的关系。</span><span class="sxs-lookup"><span data-stu-id="2415e-104">The relationships between these objects are represented in the ADO Object Model.</span></span>

<span data-ttu-id="2415e-p101">每个对象可包含在其对应的集合中。例如，[Error](error-object-ado.md) 对象可以包含在 [Errors](errors-collection-ado.md) 集合中。有关详细信息，请参阅 [ADO 集合](ado-collections.md)或具体的集合主题。</span><span class="sxs-lookup"><span data-stu-id="2415e-p101">Each object can be contained in its corresponding collection. For example, an [Error](error-object-ado.md) object can be contained in an [Errors](errors-collection-ado.md) collection. For more information, see [ADO Collections](ado-collections.md) or a specific collection topic.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2415e-108"><a href="adorecordconstruction-interface-ado.md">ADORecordConstruction</a></span><span class="sxs-lookup"><span data-stu-id="2415e-108"><a href="adorecordconstruction-interface-ado.md">ADORecordConstruction</a></span></span></p></td>
<td><p><span data-ttu-id="2415e-109">在 C/C++ 应用程序中从 OLE DB <strong>Row</strong> 对象构建 ADO <strong>Record</strong> 对象。</span><span class="sxs-lookup"><span data-stu-id="2415e-109">Constructs an ADO <strong>Record</strong> object from an OLE DB <strong>Row</strong> object in a C/C++ application.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2415e-110"><a href="adorecordsetconstruction-interface-ado.md">ADORecordsetConstruction</a></span><span class="sxs-lookup"><span data-stu-id="2415e-110"><a href="adorecordsetconstruction-interface-ado.md">ADORecordsetConstruction</a></span></span></p></td>
<td><p><span data-ttu-id="2415e-111">在 C/C++ 应用程序中从 OLE DB <strong>Rowset</strong> 对象构建 ADO <strong>Recordset</strong> 对象。</span><span class="sxs-lookup"><span data-stu-id="2415e-111">Constructs an ADO <strong>Recordset</strong> object from an OLE DB <strong>Rowset</strong> object in a C/C++ application.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2415e-112"><a href="error-object-ado.md">Error</a></span><span class="sxs-lookup"><span data-stu-id="2415e-112"><a href="error-object-ado.md">Error</a></span></span></p></td>
<td><p><span data-ttu-id="2415e-113">包含有关数据访问错误的详细信息，该错误与涉及提供程序的单个操作相关。</span><span class="sxs-lookup"><span data-stu-id="2415e-113">Contains details about data access errors that pertain to a single operation involving the provider.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2415e-114"><a href="field-object-ado.md">Field</a></span><span class="sxs-lookup"><span data-stu-id="2415e-114"><a href="field-object-ado.md">Field</a></span></span></p></td>
<td><p><span data-ttu-id="2415e-115">表示具有常规数据类型的数据列。</span><span class="sxs-lookup"><span data-stu-id="2415e-115">Represents a column of data with a common data type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2415e-116"><a href="parameter-object-ado.md">参数</a></span><span class="sxs-lookup"><span data-stu-id="2415e-116"><a href="parameter-object-ado.md">Parameter</a></span></span></p></td>
<td><p><span data-ttu-id="2415e-117">表示与基于参数化查询或存储过程的 <strong>Command</strong> 对象关联的参数或变量。</span><span class="sxs-lookup"><span data-stu-id="2415e-117">Represents a parameter or argument associated with a <strong>Command</strong> object based on a parameterized query or stored procedure.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2415e-118"><a href="property-object-ado.md">属性</a></span><span class="sxs-lookup"><span data-stu-id="2415e-118"><a href="property-object-ado.md">Property</a></span></span></p></td>
<td><p><span data-ttu-id="2415e-119">表示提供程序所定义的 ADO 对象的动态特征。</span><span class="sxs-lookup"><span data-stu-id="2415e-119">Represents a dynamic characteristic of an ADO object that is defined by the provider.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2415e-120"><a href="record-object-ado.md">Record</a></span><span class="sxs-lookup"><span data-stu-id="2415e-120"><a href="record-object-ado.md">Record</a></span></span></p></td>
<td><p><span data-ttu-id="2415e-121">表示 <strong>Recordset</strong> 的一行，或文件系统中的目录或文件。</span><span class="sxs-lookup"><span data-stu-id="2415e-121">Represents a row of a <strong>Recordset</strong>, or a directory or file in a file system.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2415e-122"><a href="recordset-object-ado.md">Recordset</a></span><span class="sxs-lookup"><span data-stu-id="2415e-122"><a href="recordset-object-ado.md">Recordset</a></span></span></p></td>
<td><p><span data-ttu-id="2415e-p102">表示从基表得到的整个记录集，或执行命令的结果。在任何时候， <strong>Recordset</strong> 对象只引用该集合中的单个记录作为当前记录。</span><span class="sxs-lookup"><span data-stu-id="2415e-p102">Represents the entire set of records from a base table or the results of an executed command. At any time, the <strong>Recordset</strong> object refers to only a single record within the set as the current record.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2415e-125"><a href="stream-object-ado.md">Stream</a></span><span class="sxs-lookup"><span data-stu-id="2415e-125"><a href="stream-object-ado.md">Stream</a></span></span></p></td>
<td><p><span data-ttu-id="2415e-126">表示二进制数据流。</span><span class="sxs-lookup"><span data-stu-id="2415e-126">Represents a binary stream of data.</span></span></p></td>
</tr>
</tbody>
</table>

