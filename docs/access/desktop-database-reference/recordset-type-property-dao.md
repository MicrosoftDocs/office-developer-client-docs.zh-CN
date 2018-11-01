---
title: Recordset.Type Property (DAO)
TOCTitle: Type Property
ms:assetid: d841b088-50bf-16d9-33e0-2140050e1ac6
ms:mtpsurl: https://msdn.microsoft.com/library/Ff835080(v=office.15)
ms:contentKeyID: 48548030
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 7bf4d06ad1785c829291fb907585a8784d6b0b75
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25888004"
---
# <a name="recordsettype-property-dao"></a><span data-ttu-id="0489c-102">Recordset.Type Property (DAO)</span><span class="sxs-lookup"><span data-stu-id="0489c-102">Recordset.Type Property (DAO)</span></span>


<span data-ttu-id="0489c-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="0489c-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="0489c-p101">设置或返回一个值，该值指示对象的操作类型或数据类型。只读 **Integer**。</span><span class="sxs-lookup"><span data-stu-id="0489c-p101">Sets or returns a value that indicates the operational type or data type of an object. Read-only **Integer**.</span></span>

## <a name="syntax"></a><span data-ttu-id="0489c-106">语法</span><span class="sxs-lookup"><span data-stu-id="0489c-106">Syntax</span></span>

<span data-ttu-id="0489c-107">*表达式*。类型</span><span class="sxs-lookup"><span data-stu-id="0489c-107">*expression* .Type</span></span>

<span data-ttu-id="0489c-108">*表达式*一个表示**Recordset**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="0489c-108">*expression* A variable that represents a **Recordset** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="0489c-109">注解</span><span class="sxs-lookup"><span data-stu-id="0489c-109">Remarks</span></span>

<span data-ttu-id="0489c-110">对于 **Recordset** 对象，可能的设置和返回值如下。</span><span class="sxs-lookup"><span data-stu-id="0489c-110">For a **Recordset** object, the possible settings and return values are as follows.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="0489c-111">常量</span><span class="sxs-lookup"><span data-stu-id="0489c-111">Constant</span></span></p></th>
<th><p><span data-ttu-id="0489c-112">记录集类型</span><span class="sxs-lookup"><span data-stu-id="0489c-112">Recordset type</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0489c-113"><strong>dbOpenTable</strong></span><span class="sxs-lookup"><span data-stu-id="0489c-113"><strong>dbOpenTable</strong></span></span></p></td>
<td><p><span data-ttu-id="0489c-114">表（仅适用于 Microsoft Access 工作区）</span><span class="sxs-lookup"><span data-stu-id="0489c-114">Table (Microsoft Access workspaces only)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0489c-115"><strong>dbOpenDynamic</strong></span><span class="sxs-lookup"><span data-stu-id="0489c-115"><strong>dbOpenDynamic</strong></span></span></p></td>
<td><p><span data-ttu-id="0489c-116">动态（仅适用于 ODBCDirect 工作区）</span><span class="sxs-lookup"><span data-stu-id="0489c-116">Dynamic (ODBCDirect workspaces only)</span></span></p>

> [!NOTE]
> <P><span data-ttu-id="0489c-117">Microsoft Access 2013 中不支持适用于 ODBCDirect 工作区。</span><span class="sxs-lookup"><span data-stu-id="0489c-117">ODBCDirect workspaces are not supported in Microsoft Access 2013.</span></span> <span data-ttu-id="0489c-118">如果要在不使用 Microsoft Access 数据库引擎的情况下访问外部数据源，请使用 ADO。</span><span class="sxs-lookup"><span data-stu-id="0489c-118">Use ADO if you want to access external data sources without using the Microsoft Access database engine.</span></span></P>


<p></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0489c-119"><strong>dbOpenDynaset</strong></span><span class="sxs-lookup"><span data-stu-id="0489c-119"><strong>dbOpenDynaset</strong></span></span></p></td>
<td><p><span data-ttu-id="0489c-120">动态集</span><span class="sxs-lookup"><span data-stu-id="0489c-120">Dynaset</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0489c-121"><strong>dbOpenSnapshot</strong></span><span class="sxs-lookup"><span data-stu-id="0489c-121"><strong>dbOpenSnapshot</strong></span></span></p></td>
<td><p><span data-ttu-id="0489c-122">快照</span><span class="sxs-lookup"><span data-stu-id="0489c-122">Snapshot</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0489c-123"><strong>dbOpenForwardOnly</strong></span><span class="sxs-lookup"><span data-stu-id="0489c-123"><strong>dbOpenForwardOnly</strong></span></span></p></td>
<td><p><span data-ttu-id="0489c-124">仅向前</span><span class="sxs-lookup"><span data-stu-id="0489c-124">Forward-only</span></span></p></td>
</tr>
</tbody>
</table>

