---
title: 参数成员 (DAO)
TOCTitle: Parameter Members
ms:assetid: 38e19de8-5318-6077-13b1-10653069aaeb
ms:mtpsurl: https://msdn.microsoft.com/library/Ff192517(v=office.15)
ms:contentKeyID: 48544228
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 25eae70d88307331c44983c4e7cbbcce3fe9d309
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32288110"
---
# <a name="parameter-members-dao"></a><span data-ttu-id="fa2b4-102">参数成员 (DAO)</span><span class="sxs-lookup"><span data-stu-id="fa2b4-102">Parameter members (DAO)</span></span>

<span data-ttu-id="fa2b4-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="fa2b4-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="fa2b4-104">Parameter 对象代表提供给查询的值。</span><span class="sxs-lookup"><span data-stu-id="fa2b4-104">A Parameter object represents a value supplied to a query.</span></span> <span data-ttu-id="fa2b4-105">此参数与从参数查询创建的 QueryDef 对象关联。</span><span class="sxs-lookup"><span data-stu-id="fa2b4-105">The parameter is associated with a QueryDef object created from a parameter query.</span></span>

## <a name="properties"></a><span data-ttu-id="fa2b4-106">属性</span><span class="sxs-lookup"><span data-stu-id="fa2b4-106">Properties</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="fa2b4-107">名称</span><span class="sxs-lookup"><span data-stu-id="fa2b4-107">Name</span></span></p></th>
<th><p><span data-ttu-id="fa2b4-108">说明</span><span class="sxs-lookup"><span data-stu-id="fa2b4-108">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fa2b4-109"><strong><a href="parameter-direction-property-dao.md">Direction</a></strong></span><span class="sxs-lookup"><span data-stu-id="fa2b4-109"><strong><a href="parameter-direction-property-dao.md">Direction</a></strong></span></span></p></td>
<td><p><span data-ttu-id="fa2b4-110"><strong>注意</strong>: Microsoft Access 2013 中不支持 ODBCDirect 工作区。</span><span class="sxs-lookup"><span data-stu-id="fa2b4-110"><strong>NOTE</strong>: ODBCDirect workspaces are not supported in Microsoft Access 2013.</span></span> <span data-ttu-id="fa2b4-111">如果要在不使用 Microsoft Access 数据库引擎的情况下访问外部数据源，请使用 ADO。</span><span class="sxs-lookup"><span data-stu-id="fa2b4-111">Use ADO if you want to access external data sources without using the Microsoft Access database engine.</span></span></p>
<p><span data-ttu-id="fa2b4-112">设置或返回一个值，该值指示 <strong><a href="parameter-object-dao.md">Parameter</a></strong> 对象代表的是输入参数、输出参数、此两者还是过程的返回值（仅适用于 ODBCDirect 工作区）。</span><span class="sxs-lookup"><span data-stu-id="fa2b4-112">Sets or returns a value that indicates whether a <strong><a href="parameter-object-dao.md">Parameter</a></strong> object represents an input parameter, an output parameter, both, or the return value from the procedure (ODBCDirect workspaces only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa2b4-113"><strong><a href="parameter-name-property-dao.md">Name</a></strong></span><span class="sxs-lookup"><span data-stu-id="fa2b4-113"><strong><a href="parameter-name-property-dao.md">Name</a></strong></span></span></p></td>
<td><p><span data-ttu-id="fa2b4-114">返回指定对象的名称。</span><span class="sxs-lookup"><span data-stu-id="fa2b4-114">Returns the name of the specified object.</span></span> <span data-ttu-id="fa2b4-115">只读的 <strong>字符串</strong> 。</span><span class="sxs-lookup"><span data-stu-id="fa2b4-115">Read-only <strong>String</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa2b4-116"><strong><a href="parameter-properties-property-dao.md">属性</a></strong></span><span class="sxs-lookup"><span data-stu-id="fa2b4-116"><strong><a href="parameter-properties-property-dao.md">Properties</a></strong></span></span></p></td>
<td><p><span data-ttu-id="fa2b4-117">返回指定对象的 <strong><a href="properties-collection-dao.md">Properties</a></strong> 集合。</span><span class="sxs-lookup"><span data-stu-id="fa2b4-117">Returns the <strong><a href="properties-collection-dao.md">Properties</a></strong> collection of the specified object.</span></span> <span data-ttu-id="fa2b4-118">只读。</span><span class="sxs-lookup"><span data-stu-id="fa2b4-118">Read-only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa2b4-119"><strong><a href="parameter-type-property-dao.md">Type</a></strong></span><span class="sxs-lookup"><span data-stu-id="fa2b4-119"><strong><a href="parameter-type-property-dao.md">Type</a></strong></span></span></p></td>
<td><p><span data-ttu-id="fa2b4-120">设置或返回一个值，该值指示对象的操作类型或数据类型。</span><span class="sxs-lookup"><span data-stu-id="fa2b4-120">Sets or returns a value that indicates the operational type or data type of an object.</span></span> <span data-ttu-id="fa2b4-121">可读/写 <strong>Integer</strong> 类型。</span><span class="sxs-lookup"><span data-stu-id="fa2b4-121">Read/write <strong>Integer</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa2b4-122"><strong><a href="parameter-value-property-dao.md">值</a></strong></span><span class="sxs-lookup"><span data-stu-id="fa2b4-122"><strong><a href="parameter-value-property-dao.md">Value</a></strong></span></span></p></td>
<td><p><span data-ttu-id="fa2b4-123">设置或返回对象的值。</span><span class="sxs-lookup"><span data-stu-id="fa2b4-123">Sets or returns the value of an object.</span></span> <span data-ttu-id="fa2b4-124"><strong>Variant</strong> 类型，可读写。</span><span class="sxs-lookup"><span data-stu-id="fa2b4-124">Read/write <strong>Variant</strong>.</span></span></p></td>
</tr>
</tbody>
</table>

