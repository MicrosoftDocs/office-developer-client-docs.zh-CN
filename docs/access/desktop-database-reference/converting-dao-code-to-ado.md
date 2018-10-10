---
title: 将 DAO 代码转换为 ADO
TOCTitle: Converting DAO Code to ADO
ms:assetid: 4720906b-d6b1-aa6d-3b18-ff828d16acae
ms:mtpsurl: https://msdn.microsoft.com/library/Ff193201(v=office.15)
ms:contentKeyID: 48544585
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm5267115
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 7039d9322956e4fcbca4081eff75868ccf306e25
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25465536"
---
# <a name="converting-dao-code-to-ado"></a><span data-ttu-id="33afe-102">将 DAO 代码转换为 ADO</span><span class="sxs-lookup"><span data-stu-id="33afe-102">Converting DAO Code to ADO</span></span>

<span data-ttu-id="33afe-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="33afe-103">**Applies to**: Access 2013 | Office 2013</span></span>

> [!NOTE]
> <span data-ttu-id="33afe-104">3.6 的 DAO 库版本不提供或支持在 Access 中。</span><span class="sxs-lookup"><span data-stu-id="33afe-104">Versions of the DAO library prior to 3.6 are not provided or supported in Access.</span></span>

## <a name="dao-to-ado-object-map"></a><span data-ttu-id="33afe-105">DAO 到 ADO 对象映射</span><span class="sxs-lookup"><span data-stu-id="33afe-105">DAO to ADO object map</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="33afe-106"><strong>DAO</strong></span><span class="sxs-lookup"><span data-stu-id="33afe-106"><strong>DAO</strong></span></span></p></th>
<th><p><span data-ttu-id="33afe-107"><strong>ADO(ADODB)</strong></span><span class="sxs-lookup"><span data-stu-id="33afe-107"><strong>ADO(ADODB)</strong></span></span></p></th>
<th><p><span data-ttu-id="33afe-108"><strong>注意</strong></span><span class="sxs-lookup"><span data-stu-id="33afe-108"><strong>Note</strong></span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="33afe-109">DBEngine</span><span class="sxs-lookup"><span data-stu-id="33afe-109">DBEngine</span></span></p></td>
<td><p><span data-ttu-id="33afe-110">无</span><span class="sxs-lookup"><span data-stu-id="33afe-110">None</span></span></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33afe-111">Workspace</span><span class="sxs-lookup"><span data-stu-id="33afe-111">Workspace</span></span></p></td>
<td><p><span data-ttu-id="33afe-112">无</span><span class="sxs-lookup"><span data-stu-id="33afe-112">None</span></span></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33afe-113">Database</span><span class="sxs-lookup"><span data-stu-id="33afe-113">Database</span></span></p></td>
<td><p><span data-ttu-id="33afe-114">Connection</span><span class="sxs-lookup"><span data-stu-id="33afe-114">Connection</span></span></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33afe-115">Recordset</span><span class="sxs-lookup"><span data-stu-id="33afe-115">Recordset</span></span></p></td>
<td><p><span data-ttu-id="33afe-116">Recordset</span><span class="sxs-lookup"><span data-stu-id="33afe-116">Recordset</span></span></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33afe-117">动态集类型</span><span class="sxs-lookup"><span data-stu-id="33afe-117">Dynaset-Type</span></span></p></td>
<td><p><span data-ttu-id="33afe-118">键集</span><span class="sxs-lookup"><span data-stu-id="33afe-118">Keyset</span></span></p></td>
<td><p><span data-ttu-id="33afe-119">在记录集中检索指向记录的指针集合</span><span class="sxs-lookup"><span data-stu-id="33afe-119">Retrieves a set of pointers to the records in the recordset</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33afe-120">快照类型</span><span class="sxs-lookup"><span data-stu-id="33afe-120">Snapshot-Type</span></span></p></td>
<td><p><span data-ttu-id="33afe-121">静态</span><span class="sxs-lookup"><span data-stu-id="33afe-121">Static</span></span></p></td>
<td><p><span data-ttu-id="33afe-122">两者都检索全部记录，但是“静态”型记录集可以更新。</span><span class="sxs-lookup"><span data-stu-id="33afe-122">Both retrieve full records but a Static recordset can be updated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33afe-123">表类型</span><span class="sxs-lookup"><span data-stu-id="33afe-123">Table-Type</span></span></p></td>
<td><p><span data-ttu-id="33afe-124">带 adCmdTableDirect 选项的键集</span><span class="sxs-lookup"><span data-stu-id="33afe-124">Keyset with adCmdTableDirect Option</span></span></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33afe-125">域</span><span class="sxs-lookup"><span data-stu-id="33afe-125">Field</span></span></p></td>
<td><p><span data-ttu-id="33afe-126">域</span><span class="sxs-lookup"><span data-stu-id="33afe-126">Field</span></span></p></td>
<td><p><span data-ttu-id="33afe-127">在记录集中引用时</span><span class="sxs-lookup"><span data-stu-id="33afe-127">When referred to in a recordset</span></span></p></td>
</tr>
</tbody>
</table>

<br/>
<br/>

### <a name="dao"></a><span data-ttu-id="33afe-128">DAO</span><span class="sxs-lookup"><span data-stu-id="33afe-128">DAO</span></span>

#### <a name="open-a-recordset"></a><span data-ttu-id="33afe-129">打开记录集</span><span class="sxs-lookup"><span data-stu-id="33afe-129">Open a Recordset</span></span>

```vb
 Dim db as Database
 Dim rs as DAO.Recordset
 Set db = CurrentDB()
 Set rs = db.OpenRecordset("Employees")
```

#### <a name="edit-a-recordset"></a><span data-ttu-id="33afe-130">编辑记录集</span><span class="sxs-lookup"><span data-stu-id="33afe-130">Edit a Recordset</span></span>

```vb
 rs.Edit 
 rs("TextFieldName") = "NewValue"
 rs.Update
```

### <a name="ado"></a><span data-ttu-id="33afe-131">ADO</span><span class="sxs-lookup"><span data-stu-id="33afe-131">ADO</span></span>

#### <a name="open-a-recordset"></a><span data-ttu-id="33afe-132">打开记录集</span><span class="sxs-lookup"><span data-stu-id="33afe-132">Open a Recordset</span></span>

```vb
 Dim rs as New ADODB.Recordset
 rs.Open "Employees", CurrentProject.Connection, _
         adOpenKeySet, adLockOptimistic
```

#### <a name="edit-a-recordset"></a><span data-ttu-id="33afe-133">编辑记录集</span><span class="sxs-lookup"><span data-stu-id="33afe-133">Edit a Recordset</span></span>

```vb
 rs("TextFieldName") = "NewValue" 
 rs.Update
```


> [!NOTE]
> <span data-ttu-id="33afe-134">在没有先使用 **CancelUpdate** 方法而利用 **MoveNext、MoveLast、MoveFirst、MovePrevious** 将焦点从当前记录移开时，将隐含执行 **Update** 方法。</span><span class="sxs-lookup"><span data-stu-id="33afe-134">Moving focus from current record via **MoveNext, MoveLast, MoveFirst, MovePrevious** without first using the **CancelUpdate** method will implicitly execute the **Update** method.</span></span>

### <a name="about-the-contributors"></a><span data-ttu-id="33afe-135">关于参与者</span><span class="sxs-lookup"><span data-stu-id="33afe-135">About the contributors</span></span>

<span data-ttu-id="33afe-136">**链接提供** [UtterAccess](https://www.utteraccess.com)社区。</span><span class="sxs-lookup"><span data-stu-id="33afe-136">**Link provided by** the [UtterAccess](https://www.utteraccess.com) community.</span></span> <span data-ttu-id="33afe-137">UtterAccess 是主要的 Microsoft Access Wiki 和帮助论坛。</span><span class="sxs-lookup"><span data-stu-id="33afe-137">UtterAccess is the premier Microsoft Access wiki and help forum.</span></span>

- [<span data-ttu-id="33afe-138">DAO 和 ADO 之间进行选择</span><span class="sxs-lookup"><span data-stu-id="33afe-138">Choosing between DAO and ADO</span></span>](https://www.utteraccess.com/wiki/index.php/choosing_between_dao_and_ado)



