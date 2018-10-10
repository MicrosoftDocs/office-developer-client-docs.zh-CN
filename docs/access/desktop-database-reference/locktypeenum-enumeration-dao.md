---
title: LockTypeEnum Enumeration (DAO)
TOCTitle: LockTypeEnum Enumeration
ms:assetid: d40f984c-b37f-72f7-7b05-752f106b6029
ms:mtpsurl: https://msdn.microsoft.com/library/Ff834802(v=office.15)
ms:contentKeyID: 48547925
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 82a09db7baff93ba7fd51de593bc4d1dfff41dc1
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467072"
---
# <a name="locktypeenum-enumeration-dao"></a><span data-ttu-id="14112-102">LockTypeEnum Enumeration (DAO)</span><span class="sxs-lookup"><span data-stu-id="14112-102">LockTypeEnum Enumeration (DAO)</span></span>


<span data-ttu-id="14112-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="14112-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="14112-104">指定在打开记录集时使用的记录锁定的类型。</span><span class="sxs-lookup"><span data-stu-id="14112-104">Specifies the type of record locking used when opening a recordset.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="14112-105">名称</span><span class="sxs-lookup"><span data-stu-id="14112-105">Name</span></span></p></th>
<th><p><span data-ttu-id="14112-106">值</span><span class="sxs-lookup"><span data-stu-id="14112-106">Value</span></span></p></th>
<th><p><span data-ttu-id="14112-107">说明</span><span class="sxs-lookup"><span data-stu-id="14112-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="14112-108">dbOptimistic</span><span class="sxs-lookup"><span data-stu-id="14112-108">dbOptimistic</span></span></p></td>
<td><p><span data-ttu-id="14112-109">3</span><span class="sxs-lookup"><span data-stu-id="14112-109">3</span></span></p></td>
<td><p><span data-ttu-id="14112-p101">基于记录 ID 的开放式并发。游标对新旧记录中的记录 ID 进行比较，以确定自上次访问该记录以来是否进行过任何更改。</span><span class="sxs-lookup"><span data-stu-id="14112-p101">Optimistic concurrency based on record ID. Cursor compares record ID in old and new records to determine if changes have been made since the record was last accessed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14112-112">dbOptimisticBatch</span><span class="sxs-lookup"><span data-stu-id="14112-112">dbOptimisticBatch</span></span></p></td>
<td><p><span data-ttu-id="14112-113">5</span><span class="sxs-lookup"><span data-stu-id="14112-113">5</span></span></p></td>
<td><p><span data-ttu-id="14112-114">启用批处理开放式更新（仅适用于 ODBCDirect 工作区）。</span><span class="sxs-lookup"><span data-stu-id="14112-114">Enables batch optimistic updates (ODBCDirect workspaces only).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14112-115">dbOptimisticValue</span><span class="sxs-lookup"><span data-stu-id="14112-115">dbOptimisticValue</span></span></p></td>
<td><p><span data-ttu-id="14112-116">1</span><span class="sxs-lookup"><span data-stu-id="14112-116">1</span></span></p></td>
<td><p><span data-ttu-id="14112-p102">基于记录值的开放式并发。游标对新旧记录中的数据值进行比较，以确定自上次访问该记录以来是否进行过任何更改。（仅适用于 ODBCDirect 工作区）</span><span class="sxs-lookup"><span data-stu-id="14112-p102">Optimistic concurrency based on record values. Cursor compares data values in old and new records to determine if changes have been made since the record was last accessed (ODBCDirect workspaces only).</span></span></p>

> [!NOTE]
> <P><span data-ttu-id="14112-119">Microsoft Access 2013 中不支持适用于 ODBCDirect 工作区。</span><span class="sxs-lookup"><span data-stu-id="14112-119">ODBCDirect workspaces are not supported in Microsoft Access 2013.</span></span> <span data-ttu-id="14112-120">如果要在不使用 Microsoft Access 数据库引擎的情况下访问外部数据源，请使用 ADO。</span><span class="sxs-lookup"><span data-stu-id="14112-120">Use ADO if you want to access external data sources without using the Microsoft Access database engine.</span></span></P>


</td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14112-121">dbPessimistic</span><span class="sxs-lookup"><span data-stu-id="14112-121">dbPessimistic</span></span></p></td>
<td><p><span data-ttu-id="14112-122">2</span><span class="sxs-lookup"><span data-stu-id="14112-122">2</span></span></p></td>
<td><p><span data-ttu-id="14112-p104">保守式并发。游标使用足以确保对记录进行更新的最低级别的锁定。</span><span class="sxs-lookup"><span data-stu-id="14112-p104">Pessimistic concurrency. Cursor uses the lowest level of locking sufficient to ensure that the record can be updated.</span></span></p></td>
</tr>
</tbody>
</table>

