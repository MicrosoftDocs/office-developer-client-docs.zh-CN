---
title: 文档成员 (DAO)
TOCTitle: Document Members
ms:assetid: 8de770e6-e4d1-372a-3ef8-8539c921b41f
ms:mtpsurl: https://msdn.microsoft.com/library/Ff197365(v=office.15)
ms:contentKeyID: 48546270
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: cd50ec72113b0615849ff6b8b2e8d73c0e61c3ce
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28720007"
---
# <a name="document-members-dao"></a><span data-ttu-id="ab8c5-102">文档成员 (DAO)</span><span class="sxs-lookup"><span data-stu-id="ab8c5-102">Document members (DAO)</span></span>


<span data-ttu-id="ab8c5-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="ab8c5-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="ab8c5-p101">Document 对象包含有关对象实例的信息。该对象可以是数据库、保存的表、查询或关系（仅适用于 Microsoft Access 数据库引擎数据库）。</span><span class="sxs-lookup"><span data-stu-id="ab8c5-p101">A Document object includes information about one instance of an object. The object can be a database, saved table, query, or relationship (Microsoft Access database engine databases only).</span></span>

## <a name="methods"></a><span data-ttu-id="ab8c5-106">方法</span><span class="sxs-lookup"><span data-stu-id="ab8c5-106">Methods</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="ab8c5-107">名称</span><span class="sxs-lookup"><span data-stu-id="ab8c5-107">Name</span></span></p></th>
<th><p><span data-ttu-id="ab8c5-108">说明</span><span class="sxs-lookup"><span data-stu-id="ab8c5-108">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ab8c5-109"><strong><a href="document-createproperty-method-dao.md">CreateProperty</a></strong></span><span class="sxs-lookup"><span data-stu-id="ab8c5-109"><strong><a href="document-createproperty-method-dao.md">CreateProperty</a></strong></span></span></p></td>
<td><p><span data-ttu-id="ab8c5-110">创建一个新的用户定义的 <strong><a href="property-object-dao.md">Property</a></strong> 对象（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="ab8c5-110">Creates a new user-defined <strong><a href="property-object-dao.md">Property</a></strong> object (Microsoft Access workspaces only).</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="properties"></a><span data-ttu-id="ab8c5-111">属性</span><span class="sxs-lookup"><span data-stu-id="ab8c5-111">Properties</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="ab8c5-112">名称</span><span class="sxs-lookup"><span data-stu-id="ab8c5-112">Name</span></span></p></th>
<th><p><span data-ttu-id="ab8c5-113">说明</span><span class="sxs-lookup"><span data-stu-id="ab8c5-113">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ab8c5-114"><strong><a href="document-container-property-dao.md">Container</a></strong></span><span class="sxs-lookup"><span data-stu-id="ab8c5-114"><strong><a href="document-container-property-dao.md">Container</a></strong></span></span></p></td>
<td><p><span data-ttu-id="ab8c5-p102">返回 <a href="container-object-dao.md">Document</a> 对象所属的 <strong><strong>Container</strong></strong> 对象的名称（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="ab8c5-p102">Returns the name of the <strong><a href="container-object-dao.md">Container</a></strong> object to which a <strong>Document</strong> object belongs (Microsoft Access workspaces only). .</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab8c5-117"><strong><a href="document-datecreated-property-dao.md">DateCreated</a></strong></span><span class="sxs-lookup"><span data-stu-id="ab8c5-117"><strong><a href="document-datecreated-property-dao.md">DateCreated</a></strong></span></span></p></td>
<td><p><span data-ttu-id="ab8c5-p103">返回对象的创建日期和时间。只读 <strong>Variant</strong>。</span><span class="sxs-lookup"><span data-stu-id="ab8c5-p103">Returns the date and time that an object was created. Read-only <strong>Variant</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab8c5-120"><strong><a href="document-lastupdated-property-dao.md">LastUpdated</a></strong></span><span class="sxs-lookup"><span data-stu-id="ab8c5-120"><strong><a href="document-lastupdated-property-dao.md">LastUpdated</a></strong></span></span></p></td>
<td><p><span data-ttu-id="ab8c5-p104">返回对象的最近更改日期和时间。只读 <strong>Variant</strong>。</span><span class="sxs-lookup"><span data-stu-id="ab8c5-p104">Returns the date and time of the most recent change made to an object. Read-only <strong>Variant</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab8c5-123"><strong><a href="document-name-property-dao.md">Name</a></strong></span><span class="sxs-lookup"><span data-stu-id="ab8c5-123"><strong><a href="document-name-property-dao.md">Name</a></strong></span></span></p></td>
<td><p><span data-ttu-id="ab8c5-p105">返回指定对象的名称。只读 <strong>String</strong>。</span><span class="sxs-lookup"><span data-stu-id="ab8c5-p105">Returns the name of the specified object. Read-only <strong>String</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab8c5-126"><strong><a href="document-properties-property-dao.md">属性</a></strong></span><span class="sxs-lookup"><span data-stu-id="ab8c5-126"><strong><a href="document-properties-property-dao.md">Properties</a></strong></span></span></p></td>
<td><p><span data-ttu-id="ab8c5-p106">返回指定对象的 <strong><a href="properties-collection-dao.md">Properties</a></strong> 集合。只读。</span><span class="sxs-lookup"><span data-stu-id="ab8c5-p106">Returns the <strong><a href="properties-collection-dao.md">Properties</a></strong> collection of the specified object. Read-only.</span></span></p></td>
</tr>
</tbody>
</table>

