---
title: RecordsetOptionEnum 枚举 (DAO)
TOCTitle: RecordsetOptionEnum Enumeration
ms:assetid: 3a9d8664-dcb6-cb60-7cf6-e229eb699ef1
ms:mtpsurl: https://msdn.microsoft.com/library/Ff192649(v=office.15)
ms:contentKeyID: 48544266
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Priority
ms.openlocfilehash: b9e2a69f6952feb892de736e7ff3c3ca94e9da64
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32307180"
---
# <a name="recordsetoptionenum-enumeration-dao"></a><span data-ttu-id="9ed40-102">RecordsetOptionEnum 枚举 (DAO)</span><span class="sxs-lookup"><span data-stu-id="9ed40-102">RecordsetOptionEnum enumeration (DAO)</span></span>


<span data-ttu-id="9ed40-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="9ed40-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="9ed40-104">结合使用 **OpenRecordset** 方法来指定新的 **Recordset** 对象的特征。</span><span class="sxs-lookup"><span data-stu-id="9ed40-104">Used with the **OpenRecordset** method to specify characteristics of a new **Recordset** object.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="9ed40-105">名称</span><span class="sxs-lookup"><span data-stu-id="9ed40-105">Name</span></span></p></th>
<th><p><span data-ttu-id="9ed40-106">值</span><span class="sxs-lookup"><span data-stu-id="9ed40-106">Value</span></span></p></th>
<th><p><span data-ttu-id="9ed40-107">说明</span><span class="sxs-lookup"><span data-stu-id="9ed40-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9ed40-108">dbAppendOnly</span><span class="sxs-lookup"><span data-stu-id="9ed40-108">dbAppendOnly</span></span></p></td>
<td><p><span data-ttu-id="9ed40-109">8</span><span class="sxs-lookup"><span data-stu-id="9ed40-109">8.</span></span></p></td>
<td><p><span data-ttu-id="9ed40-110">允许用户向动态集内添加新记录，但是禁止用户读取现有记录。</span><span class="sxs-lookup"><span data-stu-id="9ed40-110">Allows user to add new records to the dynaset, but prevents user from reading existing records.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ed40-111">dbConsistent</span><span class="sxs-lookup"><span data-stu-id="9ed40-111">dbConsistent</span></span></p></td>
<td><p><span data-ttu-id="9ed40-112">32</span><span class="sxs-lookup"><span data-stu-id="9ed40-112">3.2</span></span></p></td>
<td><p><span data-ttu-id="9ed40-113">仅向那些将不影响动态集内其他记录的字段应用更新（仅适用于动态集类型和快照类型）。</span><span class="sxs-lookup"><span data-stu-id="9ed40-113">Applies updates only to those fields that will not affect other records in the dynaset (dynaset- and snapshot-type only).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ed40-114">dbDenyRead</span><span class="sxs-lookup"><span data-stu-id="9ed40-114">dbDenyRead</span></span></p></td>
<td><p><span data-ttu-id="9ed40-115">2</span><span class="sxs-lookup"><span data-stu-id="9ed40-115">2.</span></span></p></td>
<td><p><span data-ttu-id="9ed40-116">禁止其他用户读取记录集记录（仅适用于表类型）。</span><span class="sxs-lookup"><span data-stu-id="9ed40-116">Prevents other users from reading Recordset records (table-type  only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ed40-117">dbDenyWrite</span><span class="sxs-lookup"><span data-stu-id="9ed40-117">dbDenyWrite</span></span></p></td>
<td><p><span data-ttu-id="9ed40-118">1</span><span class="sxs-lookup"><span data-stu-id="9ed40-118">-1</span></span></p></td>
<td><p><span data-ttu-id="9ed40-119">禁止其他用户更改记录集记录。</span><span class="sxs-lookup"><span data-stu-id="9ed40-119">Prevents other users from changing Recordset records.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ed40-120">dbExecDirect</span><span class="sxs-lookup"><span data-stu-id="9ed40-120">dbExecDirect</span></span></p></td>
<td><p><span data-ttu-id="9ed40-121">2048</span><span class="sxs-lookup"><span data-stu-id="9ed40-121">2048 MB</span></span></p></td>
<td><p><span data-ttu-id="9ed40-122">在不首先调用 SQLPrepare ODBC 函数的情况下执行查询。</span><span class="sxs-lookup"><span data-stu-id="9ed40-122">Executes the query without first calling the SQLPrepare ODBC function.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ed40-123">dbFailOnError</span><span class="sxs-lookup"><span data-stu-id="9ed40-123">dbFailOnError</span></span></p></td>
<td><p><span data-ttu-id="9ed40-124">128</span><span class="sxs-lookup"><span data-stu-id="9ed40-124">Default: 128</span></span></p></td>
<td><p><span data-ttu-id="9ed40-125">在出错时回滚更新。</span><span class="sxs-lookup"><span data-stu-id="9ed40-125">Rolls back updates if an error occurs.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ed40-126">dbForwardOnly</span><span class="sxs-lookup"><span data-stu-id="9ed40-126">dbForwardOnly</span></span></p></td>
<td><p><span data-ttu-id="9ed40-127">256</span><span class="sxs-lookup"><span data-stu-id="9ed40-127">validAccesses: 256</span></span></p></td>
<td><p><span data-ttu-id="9ed40-128">创建仅向前型滚动快照类型的记录集（仅适用于快照类型）。</span><span class="sxs-lookup"><span data-stu-id="9ed40-128">Creates a forward-only scrolling snapshot-type Recordset (snapshot-type only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ed40-129">dbInconsistent</span><span class="sxs-lookup"><span data-stu-id="9ed40-129">dbInconsistent</span></span></p></td>
<td><p><span data-ttu-id="9ed40-130">16</span><span class="sxs-lookup"><span data-stu-id="9ed40-130">1.6</span></span></p></td>
<td><p><span data-ttu-id="9ed40-131">向所有的动态集字段应用更新，即使其他记录受到影响也是如此（仅适用于动态集类型和快照类型）。</span><span class="sxs-lookup"><span data-stu-id="9ed40-131">Applies updates to all dynaset fields, even if other records are affected (dynaset- and snapshot-type only).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ed40-132">dbReadOnly</span><span class="sxs-lookup"><span data-stu-id="9ed40-132">dbReadOnly</span></span></p></td>
<td><p><span data-ttu-id="9ed40-133">4</span><span class="sxs-lookup"><span data-stu-id="9ed40-133">4.</span></span></p></td>
<td><p><span data-ttu-id="9ed40-134">以只读方式打开记录集。</span><span class="sxs-lookup"><span data-stu-id="9ed40-134">Opens the Recordset as read-only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ed40-135">dbRunAsync</span><span class="sxs-lookup"><span data-stu-id="9ed40-135">dbRunAsync</span></span></p></td>
<td><p><span data-ttu-id="9ed40-136">1024</span><span class="sxs-lookup"><span data-stu-id="9ed40-136">1024 attachments4</span></span></p></td>
<td><p><span data-ttu-id="9ed40-137">异步执行查询。</span><span class="sxs-lookup"><span data-stu-id="9ed40-137">Executes the query asynchronously.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ed40-138">dbSeeChanges</span><span class="sxs-lookup"><span data-stu-id="9ed40-138">dbSeeChanges</span></span></p></td>
<td><p><span data-ttu-id="9ed40-139">512</span><span class="sxs-lookup"><span data-stu-id="9ed40-139">5.12</span></span></p></td>
<td><p><span data-ttu-id="9ed40-140">如果其他用户更改您正编辑的数据，则生成运行时错误（仅适用于动态集类型）。</span><span class="sxs-lookup"><span data-stu-id="9ed40-140">Generates a run-time error if another user is changing data you are editing (dynaset-type only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ed40-141">dbSQLPassThrough</span><span class="sxs-lookup"><span data-stu-id="9ed40-141">dbSQLPassThrough</span></span></p></td>
<td><p><span data-ttu-id="9ed40-142">64</span><span class="sxs-lookup"><span data-stu-id="9ed40-142">6.4</span></span></p></td>
<td><p><span data-ttu-id="9ed40-143">向 ODBC 数据库发送 SQL 语句（仅适用于快照类型）。</span><span class="sxs-lookup"><span data-stu-id="9ed40-143">Sends an SQL statement to an ODBC database (snapshot-type only).</span></span></p></td>
</tr>
</tbody>
</table>

