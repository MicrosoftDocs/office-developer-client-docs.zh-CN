---
title: LockTypeEnum 枚举 (DAO)
TOCTitle: LockTypeEnum Enumeration
ms:assetid: d40f984c-b37f-72f7-7b05-752f106b6029
ms:mtpsurl: https://msdn.microsoft.com/library/Ff834802(v=office.15)
ms:contentKeyID: 48547925
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: ec7095df2f2f050171a45fe3639f179eab40e8e1
ms.sourcegitcommit: 558d09fad81f8d80b5ad0edd21934fc09c098f2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25943897"
---
# <a name="locktypeenum-enumeration-dao"></a><span data-ttu-id="e5e61-102">LockTypeEnum 枚举 (DAO)</span><span class="sxs-lookup"><span data-stu-id="e5e61-102">LockTypeEnum enumeration (DAO)</span></span>


<span data-ttu-id="e5e61-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="e5e61-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="e5e61-104">指定在打开记录集时使用的记录锁定的类型。</span><span class="sxs-lookup"><span data-stu-id="e5e61-104">Specifies the type of record locking used when opening a recordset.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="e5e61-105">名称</span><span class="sxs-lookup"><span data-stu-id="e5e61-105">Name</span></span></p></th>
<th><p><span data-ttu-id="e5e61-106">值</span><span class="sxs-lookup"><span data-stu-id="e5e61-106">Value</span></span></p></th>
<th><p><span data-ttu-id="e5e61-107">说明</span><span class="sxs-lookup"><span data-stu-id="e5e61-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e5e61-108">dbOptimistic</span><span class="sxs-lookup"><span data-stu-id="e5e61-108">dbOptimistic</span></span></p></td>
<td><p><span data-ttu-id="e5e61-109">3</span><span class="sxs-lookup"><span data-stu-id="e5e61-109">3</span></span></p></td>
<td><p><span data-ttu-id="e5e61-p101">基于记录 ID 的开放式并发。游标对新旧记录中的记录 ID 进行比较，以确定自上次访问该记录以来是否进行过任何更改。</span><span class="sxs-lookup"><span data-stu-id="e5e61-p101">Optimistic concurrency based on record ID. Cursor compares record ID in old and new records to determine if changes have been made since the record was last accessed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5e61-112">dbOptimisticBatch</span><span class="sxs-lookup"><span data-stu-id="e5e61-112">dbOptimisticBatch</span></span></p></td>
<td><p><span data-ttu-id="e5e61-113">5</span><span class="sxs-lookup"><span data-stu-id="e5e61-113">5</span></span></p></td>
<td><p><span data-ttu-id="e5e61-114">启用批处理开放式更新（仅适用于 ODBCDirect 工作区）。</span><span class="sxs-lookup"><span data-stu-id="e5e61-114">Enables batch optimistic updates (ODBCDirect workspaces only).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5e61-115">dbOptimisticValue</span><span class="sxs-lookup"><span data-stu-id="e5e61-115">dbOptimisticValue</span></span></p></td>
<td><p><span data-ttu-id="e5e61-116">1</span><span class="sxs-lookup"><span data-stu-id="e5e61-116">1</span></span></p></td>
<td><p><span data-ttu-id="e5e61-p102">基于记录值的开放式并发。游标对新旧记录中的数据值进行比较，以确定自上次访问该记录以来是否进行过任何更改。（仅适用于 ODBCDirect 工作区）</span><span class="sxs-lookup"><span data-stu-id="e5e61-p102">Optimistic concurrency based on record values. Cursor compares data values in old and new records to determine if changes have been made since the record was last accessed (ODBCDirect workspaces only).</span></span></p>

> [!NOTE]
> <span data-ttu-id="e5e61-119">Microsoft Access 2013 中不支持适用于 ODBCDirect 工作区。</span><span class="sxs-lookup"><span data-stu-id="e5e61-119">ODBCDirect workspaces are not supported in Microsoft Access 2013.</span></span> <span data-ttu-id="e5e61-120">如果要在不使用 Microsoft Access 数据库引擎的情况下访问外部数据源，请使用 ADO。</span><span class="sxs-lookup"><span data-stu-id="e5e61-120">Use ADO if you want to access external data sources without using the Microsoft Access database engine.</span></span>


</td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5e61-121">dbPessimistic</span><span class="sxs-lookup"><span data-stu-id="e5e61-121">dbPessimistic</span></span></p></td>
<td><p><span data-ttu-id="e5e61-122">2</span><span class="sxs-lookup"><span data-stu-id="e5e61-122">2</span></span></p></td>
<td><p><span data-ttu-id="e5e61-p104">保守式并发。游标使用足以确保对记录进行更新的最低级别的锁定。</span><span class="sxs-lookup"><span data-stu-id="e5e61-p104">Pessimistic concurrency. Cursor uses the lowest level of locking sufficient to ensure that the record can be updated.</span></span></p></td>
</tr>
</tbody>
</table>

