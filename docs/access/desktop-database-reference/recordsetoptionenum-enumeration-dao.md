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
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28717277"
---
# <a name="recordsetoptionenum-enumeration-dao"></a><span data-ttu-id="aaca4-102">RecordsetOptionEnum 枚举 (DAO)</span><span class="sxs-lookup"><span data-stu-id="aaca4-102">RecordsetOptionEnum enumeration (DAO)</span></span>


<span data-ttu-id="aaca4-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="aaca4-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="aaca4-104">与 **OpenRecordset** 方法一起用来指定新 **Recordset** 对象的特征。</span><span class="sxs-lookup"><span data-stu-id="aaca4-104">Used with the **OpenRecordset** method to specify characteristics of a new **Recordset** object.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="aaca4-105">Name</span><span class="sxs-lookup"><span data-stu-id="aaca4-105">Name</span></span></p></th>
<th><p><span data-ttu-id="aaca4-106">值</span><span class="sxs-lookup"><span data-stu-id="aaca4-106">Value</span></span></p></th>
<th><p><span data-ttu-id="aaca4-107">说明</span><span class="sxs-lookup"><span data-stu-id="aaca4-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="aaca4-108">dbAppendOnly</span><span class="sxs-lookup"><span data-stu-id="aaca4-108">dbAppendOnly</span></span></p></td>
<td><p><span data-ttu-id="aaca4-109">8</span><span class="sxs-lookup"><span data-stu-id="aaca4-109">8</span></span></p></td>
<td><p><span data-ttu-id="aaca4-110">允许用户向动态集内添加新记录，但是禁止用户读取现有记录。</span><span class="sxs-lookup"><span data-stu-id="aaca4-110">Allows user to add new records to the dynaset, but prevents user from reading existing records.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aaca4-111">dbConsistent</span><span class="sxs-lookup"><span data-stu-id="aaca4-111">dbConsistent</span></span></p></td>
<td><p><span data-ttu-id="aaca4-112">32</span><span class="sxs-lookup"><span data-stu-id="aaca4-112">32</span></span></p></td>
<td><p><span data-ttu-id="aaca4-113">仅向那些将不影响动态集内其他记录的字段应用更新（仅适用于动态集类型和快照类型）。</span><span class="sxs-lookup"><span data-stu-id="aaca4-113">Applies updates only to those fields that will not affect other records in the dynaset (dynaset- and snapshot-type only).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aaca4-114">dbDenyRead</span><span class="sxs-lookup"><span data-stu-id="aaca4-114">dbDenyRead</span></span></p></td>
<td><p><span data-ttu-id="aaca4-115">2</span><span class="sxs-lookup"><span data-stu-id="aaca4-115">2</span></span></p></td>
<td><p><span data-ttu-id="aaca4-116">防止其他用户读取记录集记录 （仅限表类型）。</span><span class="sxs-lookup"><span data-stu-id="aaca4-116">Prevents other users from reading Recordset records (table-type only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aaca4-117">dbDenyWrite</span><span class="sxs-lookup"><span data-stu-id="aaca4-117">dbDenyWrite</span></span></p></td>
<td><p><span data-ttu-id="aaca4-118">1</span><span class="sxs-lookup"><span data-stu-id="aaca4-118">1</span></span></p></td>
<td><p><span data-ttu-id="aaca4-119">禁止其他用户更改记录集记录。</span><span class="sxs-lookup"><span data-stu-id="aaca4-119">Prevents other users from changing Recordset records.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aaca4-120">一设置</span><span class="sxs-lookup"><span data-stu-id="aaca4-120">dbExecDirect</span></span></p></td>
<td><p><span data-ttu-id="aaca4-121">2048</span><span class="sxs-lookup"><span data-stu-id="aaca4-121">2048</span></span></p></td>
<td><p><span data-ttu-id="aaca4-122">在不首先调用 SQLPrepare ODBC 函数的情况下执行查询。</span><span class="sxs-lookup"><span data-stu-id="aaca4-122">Executes the query without first calling the SQLPrepare ODBC function.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aaca4-123">dbFailOnError</span><span class="sxs-lookup"><span data-stu-id="aaca4-123">dbFailOnError</span></span></p></td>
<td><p><span data-ttu-id="aaca4-124">128</span><span class="sxs-lookup"><span data-stu-id="aaca4-124">128</span></span></p></td>
<td><p><span data-ttu-id="aaca4-125">在出错时回滚更新。</span><span class="sxs-lookup"><span data-stu-id="aaca4-125">Rolls back updates if an error occurs.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aaca4-126">dbForwardOnly</span><span class="sxs-lookup"><span data-stu-id="aaca4-126">dbForwardOnly</span></span></p></td>
<td><p><span data-ttu-id="aaca4-127">256</span><span class="sxs-lookup"><span data-stu-id="aaca4-127">256</span></span></p></td>
<td><p><span data-ttu-id="aaca4-128">创建仅向前型滚动快照类型的记录集（仅适用于快照类型）。</span><span class="sxs-lookup"><span data-stu-id="aaca4-128">Creates a forward-only scrolling snapshot-type Recordset (snapshot-type only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aaca4-129">dbInconsistent</span><span class="sxs-lookup"><span data-stu-id="aaca4-129">dbInconsistent</span></span></p></td>
<td><p><span data-ttu-id="aaca4-130">16</span><span class="sxs-lookup"><span data-stu-id="aaca4-130">16</span></span></p></td>
<td><p><span data-ttu-id="aaca4-131">向所有的动态集字段应用更新，即使其他记录受到影响也是如此（仅适用于动态集类型和快照类型）。</span><span class="sxs-lookup"><span data-stu-id="aaca4-131">Applies updates to all dynaset fields, even if other records are affected (dynaset- and snapshot-type only).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aaca4-132">dbReadOnly</span><span class="sxs-lookup"><span data-stu-id="aaca4-132">dbReadOnly</span></span></p></td>
<td><p><span data-ttu-id="aaca4-133">4</span><span class="sxs-lookup"><span data-stu-id="aaca4-133">4</span></span></p></td>
<td><p><span data-ttu-id="aaca4-134">以只读方式打开记录集。</span><span class="sxs-lookup"><span data-stu-id="aaca4-134">Opens the Recordset as read-only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aaca4-135">dbRunAsync</span><span class="sxs-lookup"><span data-stu-id="aaca4-135">dbRunAsync</span></span></p></td>
<td><p><span data-ttu-id="aaca4-136">1024</span><span class="sxs-lookup"><span data-stu-id="aaca4-136">1024</span></span></p></td>
<td><p><span data-ttu-id="aaca4-137">异步执行查询。</span><span class="sxs-lookup"><span data-stu-id="aaca4-137">Executes the query asynchronously.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aaca4-138">dbSeeChanges</span><span class="sxs-lookup"><span data-stu-id="aaca4-138">dbSeeChanges</span></span></p></td>
<td><p><span data-ttu-id="aaca4-139">512</span><span class="sxs-lookup"><span data-stu-id="aaca4-139">512</span></span></p></td>
<td><p><span data-ttu-id="aaca4-140">如果其他用户更改您正编辑的数据，则生成运行时错误（仅适用于动态集类型）。</span><span class="sxs-lookup"><span data-stu-id="aaca4-140">Generates a run-time error if another user is changing data you are editing (dynaset-type only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aaca4-141">dbSQLPassThrough</span><span class="sxs-lookup"><span data-stu-id="aaca4-141">dbSQLPassThrough</span></span></p></td>
<td><p><span data-ttu-id="aaca4-142">64</span><span class="sxs-lookup"><span data-stu-id="aaca4-142">64</span></span></p></td>
<td><p><span data-ttu-id="aaca4-143">向 ODBC 数据库发送 SQL 语句（仅适用于快照类型）。</span><span class="sxs-lookup"><span data-stu-id="aaca4-143">Sends an SQL statement to an ODBC database (snapshot-type only).</span></span></p></td>
</tr>
</tbody>
</table>

