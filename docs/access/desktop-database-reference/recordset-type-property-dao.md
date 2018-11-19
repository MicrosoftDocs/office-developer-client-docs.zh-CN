---
title: Recordset.Type 属性 (DAO)
TOCTitle: Type Property
ms:assetid: d841b088-50bf-16d9-33e0-2140050e1ac6
ms:mtpsurl: https://msdn.microsoft.com/library/Ff835080(v=office.15)
ms:contentKeyID: 48548030
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: b3eedbab083807f91ffef78aab25d110db779188
ms.sourcegitcommit: 45feafb3b55de0402dddf5548c0c1c43a0eabafd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2018
ms.locfileid: "26026083"
---
# <a name="recordsettype-property-dao"></a><span data-ttu-id="6df37-102">Recordset.Type 属性 (DAO)</span><span class="sxs-lookup"><span data-stu-id="6df37-102">Recordset.Type property (DAO)</span></span>


<span data-ttu-id="6df37-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="6df37-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="6df37-p101">设置或返回一个值，该值指示对象的操作类型或数据类型。只读 **Integer**。</span><span class="sxs-lookup"><span data-stu-id="6df37-p101">Sets or returns a value that indicates the operational type or data type of an object. Read-only **Integer**.</span></span>

## <a name="syntax"></a><span data-ttu-id="6df37-106">语法</span><span class="sxs-lookup"><span data-stu-id="6df37-106">Syntax</span></span>

<span data-ttu-id="6df37-107">*表达式*。类型</span><span class="sxs-lookup"><span data-stu-id="6df37-107">*expression* .Type</span></span>

<span data-ttu-id="6df37-108">*表达式*一个表示**Recordset**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="6df37-108">*expression* A variable that represents a **Recordset** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="6df37-109">注解</span><span class="sxs-lookup"><span data-stu-id="6df37-109">Remarks</span></span>

<span data-ttu-id="6df37-110">对于 **Recordset** 对象，可能的设置和返回值如下。</span><span class="sxs-lookup"><span data-stu-id="6df37-110">For a **Recordset** object, the possible settings and return values are as follows.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="6df37-111">常量</span><span class="sxs-lookup"><span data-stu-id="6df37-111">Constant</span></span></p></th>
<th><p><span data-ttu-id="6df37-112">记录集类型</span><span class="sxs-lookup"><span data-stu-id="6df37-112">Recordset type</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6df37-113"><strong>dbOpenTable</strong></span><span class="sxs-lookup"><span data-stu-id="6df37-113"><strong>dbOpenTable</strong></span></span></p></td>
<td><p><span data-ttu-id="6df37-114">表（仅适用于 Microsoft Access 工作区）</span><span class="sxs-lookup"><span data-stu-id="6df37-114">Table (Microsoft Access workspaces only)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6df37-115"><strong>dbOpenDynamic</strong></span><span class="sxs-lookup"><span data-stu-id="6df37-115"><strong>dbOpenDynamic</strong></span></span></p></td>
<td><p><span data-ttu-id="6df37-116">动态（仅适用于 ODBCDirect 工作区）</span><span class="sxs-lookup"><span data-stu-id="6df37-116">Dynamic (ODBCDirect workspaces only)</span></span></p>
<p><span data-ttu-id="6df37-117"><strong>注意</strong>： Microsoft Access 2013 中不支持适用于 ODBCDirect 工作区。</span><span class="sxs-lookup"><span data-stu-id="6df37-117"><strong>NOTE</strong>: ODBCDirect workspaces are not supported in Microsoft Access 2013.</span></span> <span data-ttu-id="6df37-118">如果要在不使用 Microsoft Access 数据库引擎的情况下访问外部数据源，请使用 ADO。</span><span class="sxs-lookup"><span data-stu-id="6df37-118">Use ADO if you want to access external data sources without using the Microsoft Access database engine.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6df37-119"><strong>dbOpenDynaset</strong></span><span class="sxs-lookup"><span data-stu-id="6df37-119"><strong>dbOpenDynaset</strong></span></span></p></td>
<td><p><span data-ttu-id="6df37-120">动态集</span><span class="sxs-lookup"><span data-stu-id="6df37-120">Dynaset</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6df37-121"><strong>dbOpenSnapshot</strong></span><span class="sxs-lookup"><span data-stu-id="6df37-121"><strong>dbOpenSnapshot</strong></span></span></p></td>
<td><p><span data-ttu-id="6df37-122">快照</span><span class="sxs-lookup"><span data-stu-id="6df37-122">Snapshot</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6df37-123"><strong>dbOpenForwardOnly</strong></span><span class="sxs-lookup"><span data-stu-id="6df37-123"><strong>dbOpenForwardOnly</strong></span></span></p></td>
<td><p><span data-ttu-id="6df37-124">仅向前</span><span class="sxs-lookup"><span data-stu-id="6df37-124">Forward-only</span></span></p></td>
</tr>
</tbody>
</table>

