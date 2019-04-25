---
title: 将 DAO 代码转换为 ADO
TOCTitle: Convert DAO code to ADO
ms:assetid: 4720906b-d6b1-aa6d-3b18-ff828d16acae
ms:mtpsurl: https://msdn.microsoft.com/library/Ff193201(v=office.15)
ms:contentKeyID: 48544585
ms.date: 10/16/2018
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm5267115
f1_categories:
- Office.Version=v15
localization_priority: Priority
ms.openlocfilehash: 77d56efd63d6a0841b595f12456baa808751706e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32295518"
---
# <a name="convert-dao-code-to-ado"></a><span data-ttu-id="c395d-102">将 DAO 代码转换为 ADO</span><span class="sxs-lookup"><span data-stu-id="c395d-102">Convert DAO code to ADO</span></span>

<span data-ttu-id="c395d-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="c395d-103">**Applies to**: Access 2013, Office 2013</span></span>

> [!NOTE]
> <span data-ttu-id="c395d-104">Access 中不提供或支持版本号低于 3.6 的 DAO 库。</span><span class="sxs-lookup"><span data-stu-id="c395d-104">Versions of the DAO library prior to 3.6 are not provided or supported in Microsoft Access 2010.</span></span>

## <a name="dao-to-ado-object-map"></a><span data-ttu-id="c395d-105">DAO 到 ADO 的对象映射表</span><span class="sxs-lookup"><span data-stu-id="c395d-105">DAO to ADO object Map</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="c395d-106"><strong>DAO</strong></span><span class="sxs-lookup"><span data-stu-id="c395d-106"><strong>DAO</strong></span></span></p></th>
<th><p><span data-ttu-id="c395d-107"><strong>ADO (ADODB)</strong></span><span class="sxs-lookup"><span data-stu-id="c395d-107"><strong>ADO (ADODB)</strong></span></span></p></th>
<th><p><span data-ttu-id="c395d-108"><strong>备注</strong></span><span class="sxs-lookup"><span data-stu-id="c395d-108"><strong>Note</strong></span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c395d-109">DBEngine</span><span class="sxs-lookup"><span data-stu-id="c395d-109">DBEngine</span></span></p></td>
<td><p><span data-ttu-id="c395d-110">无</span><span class="sxs-lookup"><span data-stu-id="c395d-110">None</span></span></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c395d-111">Workspace</span><span class="sxs-lookup"><span data-stu-id="c395d-111">Workspace</span></span></p></td>
<td><p><span data-ttu-id="c395d-112">无</span><span class="sxs-lookup"><span data-stu-id="c395d-112">None</span></span></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c395d-113">Database</span><span class="sxs-lookup"><span data-stu-id="c395d-113">Database</span></span></p></td>
<td><p><span data-ttu-id="c395d-114">Connection</span><span class="sxs-lookup"><span data-stu-id="c395d-114">Connection</span></span></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c395d-115">Recordset</span><span class="sxs-lookup"><span data-stu-id="c395d-115">Recordset</span></span></p></td>
<td><p><span data-ttu-id="c395d-116">Recordset</span><span class="sxs-lookup"><span data-stu-id="c395d-116">Recordset</span></span></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c395d-117">Dynaset-Type</span><span class="sxs-lookup"><span data-stu-id="c395d-117">Dynaset-Type</span></span></p></td>
<td><p><span data-ttu-id="c395d-118">Keyset</span><span class="sxs-lookup"><span data-stu-id="c395d-118">Keyset cursors</span></span></p></td>
<td><p><span data-ttu-id="c395d-119">在记录集中检索指向记录的指针集合。</span><span class="sxs-lookup"><span data-stu-id="c395d-119">Retrieves a set of pointers to the records in the recordset</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c395d-120">Snapshot-Type</span><span class="sxs-lookup"><span data-stu-id="c395d-120">Snapshot-Type</span></span></p></td>
<td><p><span data-ttu-id="c395d-121">Static</span><span class="sxs-lookup"><span data-stu-id="c395d-121">Static</span></span></p></td>
<td><p><span data-ttu-id="c395d-122">两者都检索全部记录，但是 Static 记录集可以更新。</span><span class="sxs-lookup"><span data-stu-id="c395d-122">Both retrieve full records but a Static recordset can be updated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c395d-123">Table-Type</span><span class="sxs-lookup"><span data-stu-id="c395d-123">TableType</span></span></p></td>
<td><p><span data-ttu-id="c395d-124">带 adCmdTableDirect 选项的 Keyset。</span><span class="sxs-lookup"><span data-stu-id="c395d-124">Keyset with adCmdTableDirect Option</span></span></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c395d-125">Field</span><span class="sxs-lookup"><span data-stu-id="c395d-125">Field</span></span></p></td>
<td><p><span data-ttu-id="c395d-126">Field</span><span class="sxs-lookup"><span data-stu-id="c395d-126">Field</span></span></p></td>
<td><p><span data-ttu-id="c395d-127">在记录集中引用时。</span><span class="sxs-lookup"><span data-stu-id="c395d-127">When referred to in a recordset</span></span></p></td>
</tr>
</tbody>
</table>

<br/>
<br/>

### <a name="dao"></a><span data-ttu-id="c395d-128">DAO</span><span class="sxs-lookup"><span data-stu-id="c395d-128">DAO</span></span>

#### <a name="open-a-recordset"></a><span data-ttu-id="c395d-129">打开 Recordset</span><span class="sxs-lookup"><span data-stu-id="c395d-129">Open a Recordset</span></span>

```vb
 Dim db as Database
 Dim rs as DAO.Recordset
 Set db = CurrentDB()
 Set rs = db.OpenRecordset("Employees")
```

#### <a name="edit-a-recordset"></a><span data-ttu-id="c395d-130">编辑 Recordset</span><span class="sxs-lookup"><span data-stu-id="c395d-130">Edit a Recordset</span></span>

```vb
 rs.Edit 
 rs("TextFieldName") = "NewValue"
 rs.Update
```

### <a name="ado"></a><span data-ttu-id="c395d-131">ADO</span><span class="sxs-lookup"><span data-stu-id="c395d-131">ADO</span></span>

#### <a name="open-a-recordset"></a><span data-ttu-id="c395d-132">打开 Recordset</span><span class="sxs-lookup"><span data-stu-id="c395d-132">Open a Recordset</span></span>

```vb
 Dim rs as New ADODB.Recordset
 rs.Open "Employees", CurrentProject.Connection, _
         adOpenKeySet, adLockOptimistic
```

#### <a name="edit-a-recordset"></a><span data-ttu-id="c395d-133">编辑 Recordset</span><span class="sxs-lookup"><span data-stu-id="c395d-133">Edit a Recordset</span></span>

```vb
 rs("TextFieldName") = "NewValue" 
 rs.Update
```


> [!NOTE]
> <span data-ttu-id="c395d-134">在没有先使用 **CancelUpdate** 方法而利用 **MoveNext、MoveLast、MoveFirst、MovePrevious** 将焦点从当前记录移开时，会隐含执行 **Update** 方法。</span><span class="sxs-lookup"><span data-stu-id="c395d-134">Moving focus from current record via **MoveNext, MoveLast, MoveFirst, MovePrevious** without first using the **CancelUpdate** method will implicitly execute the **Update** method.</span></span>

### <a name="about-the-contributors"></a><span data-ttu-id="c395d-135">关于参与者</span><span class="sxs-lookup"><span data-stu-id="c395d-135">About the contributors</span></span>

<span data-ttu-id="c395d-136">**链接提供者：**[UtterAccess](https://www.utteraccess.com) 社区。</span><span class="sxs-lookup"><span data-stu-id="c395d-136">**Link provided by:** The [UtterAccess](https://www.utteraccess.com) community</span></span> <span data-ttu-id="c395d-137">UtterAccess 是主要的 Microsoft Access Wiki 和帮助论坛。</span><span class="sxs-lookup"><span data-stu-id="c395d-137">UtterAccess is the premier Microsoft Access wiki and help forum.</span></span>

- [<span data-ttu-id="c395d-138">在 DAO 和 ADO 之间进行选择</span><span class="sxs-lookup"><span data-stu-id="c395d-138">Choosing between DAO and ADO</span></span>](https://www.utteraccess.com/wiki/index.php/choosing_between_dao_and_ado)

<br/>

