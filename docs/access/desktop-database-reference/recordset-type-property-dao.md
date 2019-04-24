---
title: Recordset。 Type 属性 (DAO)
TOCTitle: Type Property
ms:assetid: d841b088-50bf-16d9-33e0-2140050e1ac6
ms:mtpsurl: https://msdn.microsoft.com/library/Ff835080(v=office.15)
ms:contentKeyID: 48548030
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 4a55af8aaa5cfb3d87e13125871a6ccbe1e7f2dd
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32307551"
---
# <a name="recordsettype-property-dao"></a><span data-ttu-id="6651a-102">Recordset。 Type 属性 (DAO)</span><span class="sxs-lookup"><span data-stu-id="6651a-102">Recordset.Type property (DAO)</span></span>


<span data-ttu-id="6651a-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="6651a-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="6651a-104">设置或返回一个值，该值指示对象的操作类型或数据类型。</span><span class="sxs-lookup"><span data-stu-id="6651a-104">Sets or returns a value that indicates the operational type or data type of an object.</span></span> <span data-ttu-id="6651a-105">只读 **Integer**。</span><span class="sxs-lookup"><span data-stu-id="6651a-105">Read-only **Integer**.</span></span>

## <a name="syntax"></a><span data-ttu-id="6651a-106">语法</span><span class="sxs-lookup"><span data-stu-id="6651a-106">Syntax</span></span>

<span data-ttu-id="6651a-107">*表达式*。类型</span><span class="sxs-lookup"><span data-stu-id="6651a-107">*expression* .Type</span></span>

<span data-ttu-id="6651a-108">*表达式*一个代表**Recordset**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="6651a-108">*expression* A variable that represents a **Recordset** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="6651a-109">注解</span><span class="sxs-lookup"><span data-stu-id="6651a-109">Remarks</span></span>

<span data-ttu-id="6651a-110">对于 **Recordset** 对象，可能的设置和返回值如下。</span><span class="sxs-lookup"><span data-stu-id="6651a-110">For a **Recordset** object, the possible settings and return values are as follows.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="6651a-111">常量</span><span class="sxs-lookup"><span data-stu-id="6651a-111">Constant</span></span></p></th>
<th><p><span data-ttu-id="6651a-112">记录集类型</span><span class="sxs-lookup"><span data-stu-id="6651a-112">Recordset type</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6651a-113"><strong>dbOpenTable</strong></span><span class="sxs-lookup"><span data-stu-id="6651a-113"><strong>dbOpenTable</strong></span></span></p></td>
<td><p><span data-ttu-id="6651a-114">表（仅适用于 Microsoft Access 工作区）</span><span class="sxs-lookup"><span data-stu-id="6651a-114">Table (Microsoft Access workspaces only)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6651a-115"><strong>dbOpenDynamic</strong></span><span class="sxs-lookup"><span data-stu-id="6651a-115"><strong>dbOpenDynamic</strong></span></span></p></td>
<td><p><span data-ttu-id="6651a-116">动态（仅适用于 ODBCDirect 工作区）</span><span class="sxs-lookup"><span data-stu-id="6651a-116">Dynamic (ODBCDirect workspaces only)</span></span></p>
<p><span data-ttu-id="6651a-117"><strong>注意</strong>: Microsoft Access 2013 中不支持 ODBCDirect 工作区。</span><span class="sxs-lookup"><span data-stu-id="6651a-117"><strong>NOTE</strong>: ODBCDirect workspaces are not supported in Microsoft Access 2013.</span></span> <span data-ttu-id="6651a-118">如果要在不使用 Microsoft Access 数据库引擎的情况下访问外部数据源，请使用 ADO。</span><span class="sxs-lookup"><span data-stu-id="6651a-118">Use ADO if you want to access external data sources without using the Microsoft Access database engine.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6651a-119"><strong>dbOpenDynaset</strong></span><span class="sxs-lookup"><span data-stu-id="6651a-119"><strong>dbOpenDynaset</strong></span></span></p></td>
<td><p><span data-ttu-id="6651a-120">可见</span><span class="sxs-lookup"><span data-stu-id="6651a-120">Dynaset</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6651a-121"><strong>dbOpenSnapshot</strong></span><span class="sxs-lookup"><span data-stu-id="6651a-121"><strong>dbOpenSnapshot</strong></span></span></p></td>
<td><p><span data-ttu-id="6651a-122">概述</span><span class="sxs-lookup"><span data-stu-id="6651a-122">Snapshot</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6651a-123"><strong>dbOpenForwardOnly</strong></span><span class="sxs-lookup"><span data-stu-id="6651a-123"><strong>dbOpenForwardOnly</strong></span></span></p></td>
<td><p><span data-ttu-id="6651a-124">仅向前</span><span class="sxs-lookup"><span data-stu-id="6651a-124">Forward-only</span></span></p></td>
</tr>
</tbody>
</table>

