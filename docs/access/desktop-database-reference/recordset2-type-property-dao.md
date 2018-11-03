---
title: Recordset2.Type 属性 (DAO)
TOCTitle: Type Property
ms:assetid: 9bec543e-7f59-ea59-dc79-41d0e08b5ab6
ms:mtpsurl: https://msdn.microsoft.com/library/Ff198080(v=office.15)
ms:contentKeyID: 48546583
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1052880
f1_categories:
- Office.Version=v15
ms.openlocfilehash: ca75e1b21e017dfbbbc5028d06a4799a9afd50f3
ms.sourcegitcommit: 38d0db57580cc5f4a0231c27b1643f8db5431ca3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25936593"
---
# <a name="recordset2type-property-dao"></a><span data-ttu-id="7f1e6-102">Recordset2.Type 属性 (DAO)</span><span class="sxs-lookup"><span data-stu-id="7f1e6-102">Recordset2.Type property (DAO)</span></span>


<span data-ttu-id="7f1e6-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="7f1e6-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="7f1e6-p101">设置或返回一个值，该值指示对象的操作类型或数据类型。只读 **Integer**。</span><span class="sxs-lookup"><span data-stu-id="7f1e6-p101">Sets or returns a value that indicates the operational type or data type of an object. Read-only **Integer**.</span></span>

## <a name="syntax"></a><span data-ttu-id="7f1e6-106">语法</span><span class="sxs-lookup"><span data-stu-id="7f1e6-106">Syntax</span></span>

<span data-ttu-id="7f1e6-107">*表达式*。类型</span><span class="sxs-lookup"><span data-stu-id="7f1e6-107">*expression* .Type</span></span>

<span data-ttu-id="7f1e6-108">*表达式*一个表示**Recordset2**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="7f1e6-108">*expression* A variable that represents a **Recordset2** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="7f1e6-109">注解</span><span class="sxs-lookup"><span data-stu-id="7f1e6-109">Remarks</span></span>

<span data-ttu-id="7f1e6-110">对于 **Recordset** 对象，可能的设置和返回值如下。</span><span class="sxs-lookup"><span data-stu-id="7f1e6-110">For a **Recordset** object, the possible settings and return values are as follows.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="7f1e6-111">常量</span><span class="sxs-lookup"><span data-stu-id="7f1e6-111">Constant</span></span></p></th>
<th><p><span data-ttu-id="7f1e6-112">记录集类型</span><span class="sxs-lookup"><span data-stu-id="7f1e6-112">Recordset type</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7f1e6-113"><strong>dbOpenTable</strong></span><span class="sxs-lookup"><span data-stu-id="7f1e6-113"><strong>dbOpenTable</strong></span></span></p></td>
<td><p><span data-ttu-id="7f1e6-114">表（仅适用于 Microsoft Access 工作区）</span><span class="sxs-lookup"><span data-stu-id="7f1e6-114">Table (Microsoft Access workspaces only)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7f1e6-115"><strong>dbOpenDynamic</strong></span><span class="sxs-lookup"><span data-stu-id="7f1e6-115"><strong>dbOpenDynamic</strong></span></span></p></td>
<td><p><span data-ttu-id="7f1e6-116">动态（仅适用于 ODBCDirect 工作区）</span><span class="sxs-lookup"><span data-stu-id="7f1e6-116">Dynamic (ODBCDirect workspaces only)</span></span></p>
<p><span data-ttu-id="7f1e6-117"><strong>注意</strong>： Microsoft Access 2013 中不支持适用于 ODBCDirect 工作区。</span><span class="sxs-lookup"><span data-stu-id="7f1e6-117"><strong>NOTE</strong>: ODBCDirect workspaces are not supported in Microsoft Access 2013.</span></span> <span data-ttu-id="7f1e6-118">如果要在不使用 Microsoft Access 数据库引擎的情况下访问外部数据源，请使用 ADO。</span><span class="sxs-lookup"><span data-stu-id="7f1e6-118">Use ADO if you want to access external data sources without using the Microsoft Access database engine.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7f1e6-119"><strong>dbOpenDynaset</strong></span><span class="sxs-lookup"><span data-stu-id="7f1e6-119"><strong>dbOpenDynaset</strong></span></span></p></td>
<td><p><span data-ttu-id="7f1e6-120">动态集</span><span class="sxs-lookup"><span data-stu-id="7f1e6-120">Dynaset</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7f1e6-121"><strong>dbOpenSnapshot</strong></span><span class="sxs-lookup"><span data-stu-id="7f1e6-121"><strong>dbOpenSnapshot</strong></span></span></p></td>
<td><p><span data-ttu-id="7f1e6-122">快照</span><span class="sxs-lookup"><span data-stu-id="7f1e6-122">Snapshot</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7f1e6-123"><strong>dbOpenForwardOnly</strong></span><span class="sxs-lookup"><span data-stu-id="7f1e6-123"><strong>dbOpenForwardOnly</strong></span></span></p></td>
<td><p><span data-ttu-id="7f1e6-124">仅向前</span><span class="sxs-lookup"><span data-stu-id="7f1e6-124">Forward-only</span></span></p></td>
</tr>
</tbody>
</table>

