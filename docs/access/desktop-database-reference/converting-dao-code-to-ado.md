---
<span data-ttu-id="a5079-101"><<<<<<< 标头标题： 将 DAO 代码转换为 ADO TOCTitle： 将 DAO 代码转换为 ADO ms:assetid: 4720906b-d6b1-aa6d-3b18-ff828d16acae ms:mtpsurl: https://msdn.microsoft.com/library/Ff193201(v=office.15) ms:contentKeyID: 48544585 ms.date: 09/18/2015年 === 标题： 转换 DAOADO TOCTitle 代码： ADO ms:assetid 转换 DAO 代码： 4720906b-d6b1-aa6d-3b18-ff828d16acae ms:mtpsurl: https://msdn.microsoft.com/library/Ff193201(v=office.15) ms:contentKeyID: 48544585 ms.date: 10/16/2018</span><span class="sxs-lookup"><span data-stu-id="a5079-101"><<<<<<< HEAD title: Converting DAO Code to ADO TOCTitle: Converting DAO Code to ADO ms:assetid: 4720906b-d6b1-aa6d-3b18-ff828d16acae ms:mtpsurl: https://msdn.microsoft.com/library/Ff193201(v=office.15) ms:contentKeyID: 48544585 ms.date: 09/18/2015 ======= title: Convert DAO code to ADO TOCTitle: Convert DAO code to ADO ms:assetid: 4720906b-d6b1-aa6d-3b18-ff828d16acae ms:mtpsurl: https://msdn.microsoft.com/library/Ff193201(v=office.15) ms:contentKeyID: 48544585 ms.date: 10/16/2018</span></span>
>>>>>>> <span data-ttu-id="a5079-102">主 mtps_version: office.15.aspx f1_keywords:</span><span class="sxs-lookup"><span data-stu-id="a5079-102">master mtps_version: v=office.15 f1_keywords:</span></span>
- <span data-ttu-id="a5079-103">vbaac10.chm5267115 f1_categories:</span><span class="sxs-lookup"><span data-stu-id="a5079-103">vbaac10.chm5267115 f1_categories:</span></span>
- <span data-ttu-id="a5079-104">Office.Version=v15</span><span class="sxs-lookup"><span data-stu-id="a5079-104">Office.Version=v15</span></span>
---

<span data-ttu-id="a5079-105"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="a5079-105"><<<<<<< HEAD</span></span>
# <a name="converting-dao-code-to-ado"></a><span data-ttu-id="a5079-106">将 DAO 代码转换为 ADO</span><span class="sxs-lookup"><span data-stu-id="a5079-106">Converting DAO Code to ADO</span></span>
=======
# <a name="convert-dao-code-to-ado"></a><span data-ttu-id="a5079-107">将 DAO 代码转换为 ADO</span><span class="sxs-lookup"><span data-stu-id="a5079-107">Convert DAO code to ADO</span></span>
>>>>>>> <span data-ttu-id="a5079-108">master</span><span class="sxs-lookup"><span data-stu-id="a5079-108">master</span></span>

<span data-ttu-id="a5079-109">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="a5079-109">**Applies to**: Access 2013 | Office 2013</span></span>

> [!NOTE]
> <span data-ttu-id="a5079-110">3.6 的 DAO 库版本不提供或支持在 Access 中。</span><span class="sxs-lookup"><span data-stu-id="a5079-110">Versions of the DAO library prior to 3.6 are not provided or supported in Access.</span></span>

## <a name="dao-to-ado-object-map"></a><span data-ttu-id="a5079-111">DAO 到 ADO 对象映射</span><span class="sxs-lookup"><span data-stu-id="a5079-111">DAO to ADO object map</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="a5079-112"><strong>DAO</strong></span><span class="sxs-lookup"><span data-stu-id="a5079-112"><strong>DAO</strong></span></span></p></th>
<span data-ttu-id="a5079-113"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="a5079-113"><<<<<<< HEAD</span></span>
<th><p><span data-ttu-id="a5079-114"><strong>ADO(ADODB)</strong></span><span class="sxs-lookup"><span data-stu-id="a5079-114"><strong>ADO(ADODB)</strong></span></span></p></th>
=======
<th><p><span data-ttu-id="a5079-115"><strong>ADO (ADODB)</strong></span><span class="sxs-lookup"><span data-stu-id="a5079-115"><strong>ADO (ADODB)</strong></span></span></p></th><span data-ttu-id="a5079-116">
>>>>>>>主控形状</span><span class="sxs-lookup"><span data-stu-id="a5079-116">
>>>>>>> master</span></span>
<th><p><span data-ttu-id="a5079-117"><strong>注意</strong></span><span class="sxs-lookup"><span data-stu-id="a5079-117"><strong>Note</strong></span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a5079-118">DBEngine</span><span class="sxs-lookup"><span data-stu-id="a5079-118">DBEngine</span></span></p></td>
<td><p><span data-ttu-id="a5079-119">无</span><span class="sxs-lookup"><span data-stu-id="a5079-119">None</span></span></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5079-120">Workspace</span><span class="sxs-lookup"><span data-stu-id="a5079-120">Workspace</span></span></p></td>
<td><p><span data-ttu-id="a5079-121">无</span><span class="sxs-lookup"><span data-stu-id="a5079-121">None</span></span></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5079-122">Database</span><span class="sxs-lookup"><span data-stu-id="a5079-122">Database</span></span></p></td>
<td><p><span data-ttu-id="a5079-123">Connection</span><span class="sxs-lookup"><span data-stu-id="a5079-123">Connection</span></span></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5079-124">Recordset</span><span class="sxs-lookup"><span data-stu-id="a5079-124">Recordset</span></span></p></td>
<td><p><span data-ttu-id="a5079-125">Recordset</span><span class="sxs-lookup"><span data-stu-id="a5079-125">Recordset</span></span></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5079-126">动态集类型</span><span class="sxs-lookup"><span data-stu-id="a5079-126">Dynaset-Type</span></span></p></td>
<td><p><span data-ttu-id="a5079-127">键集</span><span class="sxs-lookup"><span data-stu-id="a5079-127">Keyset</span></span></p></td>
<span data-ttu-id="a5079-128"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="a5079-128"><<<<<<< HEAD</span></span>
<td><p><span data-ttu-id="a5079-129">在记录集中检索指向记录的指针集合</span><span class="sxs-lookup"><span data-stu-id="a5079-129">Retrieves a set of pointers to the records in the recordset</span></span></p></td>
=======
<td><p><span data-ttu-id="a5079-130">检索到 recordset 中记录指针的一组。</span><span class="sxs-lookup"><span data-stu-id="a5079-130">Retrieves a set of pointers to the records in the recordset.</span></span></p></td><span data-ttu-id="a5079-131">
>>>>>>>主控形状</span><span class="sxs-lookup"><span data-stu-id="a5079-131">
>>>>>>> master</span></span>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5079-132">快照类型</span><span class="sxs-lookup"><span data-stu-id="a5079-132">Snapshot-Type</span></span></p></td>
<td><p><span data-ttu-id="a5079-133">静态</span><span class="sxs-lookup"><span data-stu-id="a5079-133">Static</span></span></p></td>
<span data-ttu-id="a5079-134"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="a5079-134"><<<<<<< HEAD</span></span>
<td><p><span data-ttu-id="a5079-135">两者都检索全部记录，但是“静态”型记录集可以更新。</span><span class="sxs-lookup"><span data-stu-id="a5079-135">Both retrieve full records but a Static recordset can be updated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5079-136">表类型</span><span class="sxs-lookup"><span data-stu-id="a5079-136">Table-Type</span></span></p></td>
<td><p><span data-ttu-id="a5079-137">带 adCmdTableDirect 选项的键集</span><span class="sxs-lookup"><span data-stu-id="a5079-137">Keyset with adCmdTableDirect Option</span></span></p></td>
=======
<td><p><span data-ttu-id="a5079-138">两者都检索全部记录，但可以更新静态记录。</span><span class="sxs-lookup"><span data-stu-id="a5079-138">Both retrieve full records, but a Static recordset can be updated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5079-139">表类型</span><span class="sxs-lookup"><span data-stu-id="a5079-139">Table-Type</span></span></p></td>
<td><p><span data-ttu-id="a5079-140">使用 adCmdTableDirect 选项的键集。</span><span class="sxs-lookup"><span data-stu-id="a5079-140">Keyset with adCmdTableDirect option.</span></span></p></td><span data-ttu-id="a5079-141">
>>>>>>>主控形状</span><span class="sxs-lookup"><span data-stu-id="a5079-141">
>>>>>>> master</span></span>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5079-142">Field</span><span class="sxs-lookup"><span data-stu-id="a5079-142">Field</span></span></p></td>
<td><p><span data-ttu-id="a5079-143">Field</span><span class="sxs-lookup"><span data-stu-id="a5079-143">Field</span></span></p></td>
<span data-ttu-id="a5079-144"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="a5079-144"><<<<<<< HEAD</span></span>
<td><p><span data-ttu-id="a5079-145">在记录集中引用时</span><span class="sxs-lookup"><span data-stu-id="a5079-145">When referred to in a recordset</span></span></p></td>
=======
<td><p><span data-ttu-id="a5079-146">当 recordset 中引用。</span><span class="sxs-lookup"><span data-stu-id="a5079-146">When referred to in a recordset.</span></span></p></td><span data-ttu-id="a5079-147">
>>>>>>>主控形状</span><span class="sxs-lookup"><span data-stu-id="a5079-147">
>>>>>>> master</span></span>
</tr>
</tbody>
</table>

<br/>
<br/>

### <a name="dao"></a><span data-ttu-id="a5079-148">DAO</span><span class="sxs-lookup"><span data-stu-id="a5079-148">DAO</span></span>

#### <a name="open-a-recordset"></a><span data-ttu-id="a5079-149">打开记录集</span><span class="sxs-lookup"><span data-stu-id="a5079-149">Open a Recordset</span></span>

```vb
 Dim db as Database
 Dim rs as DAO.Recordset
 Set db = CurrentDB()
 Set rs = db.OpenRecordset("Employees")
```

#### <a name="edit-a-recordset"></a><span data-ttu-id="a5079-150">编辑记录集</span><span class="sxs-lookup"><span data-stu-id="a5079-150">Edit a Recordset</span></span>

```vb
 rs.Edit 
 rs("TextFieldName") = "NewValue"
 rs.Update
```

### <a name="ado"></a><span data-ttu-id="a5079-151">ADO</span><span class="sxs-lookup"><span data-stu-id="a5079-151">ADO</span></span>

#### <a name="open-a-recordset"></a><span data-ttu-id="a5079-152">打开记录集</span><span class="sxs-lookup"><span data-stu-id="a5079-152">Open a Recordset</span></span>

```vb
 Dim rs as New ADODB.Recordset
 rs.Open "Employees", CurrentProject.Connection, _
         adOpenKeySet, adLockOptimistic
```

#### <a name="edit-a-recordset"></a><span data-ttu-id="a5079-153">编辑记录集</span><span class="sxs-lookup"><span data-stu-id="a5079-153">Edit a Recordset</span></span>

```vb
 rs("TextFieldName") = "NewValue" 
 rs.Update
```


> [!NOTE]
<span data-ttu-id="a5079-154"><<<<<<< 标头移动在没有先使用**CancelUpdate**方法将隐含执行**Update**方法从当前记录**MoveNext、 MoveLast MoveFirst，MovePrevious**通过重点。</span><span class="sxs-lookup"><span data-stu-id="a5079-154"><<<<<<< HEAD Moving focus from current record via **MoveNext, MoveLast, MoveFirst, MovePrevious** without first using the **CancelUpdate** method will implicitly execute the **Update** method.</span></span>
> <span data-ttu-id="a5079-155">=== 焦点从当前记录移通过**MoveNext、 MoveLast、 MoveFirst、 MovePrevious**没有先使用**CancelUpdate**方法隐式执行**Update**方法。</span><span class="sxs-lookup"><span data-stu-id="a5079-155">======= Moving focus from current record via **MoveNext, MoveLast, MoveFirst, MovePrevious** without first using the **CancelUpdate** method implicitly executes the **Update** method.</span></span>
>>>>>>> <span data-ttu-id="a5079-156">master</span><span class="sxs-lookup"><span data-stu-id="a5079-156">master</span></span>

### <a name="about-the-contributors"></a><span data-ttu-id="a5079-157">关于参与者</span><span class="sxs-lookup"><span data-stu-id="a5079-157">About the contributors</span></span>

<span data-ttu-id="a5079-158">**链接提供** [UtterAccess](https://www.utteraccess.com)社区。</span><span class="sxs-lookup"><span data-stu-id="a5079-158">**Link provided by** the [UtterAccess](https://www.utteraccess.com) community.</span></span> <span data-ttu-id="a5079-159">UtterAccess 是主要的 Microsoft Access Wiki 和帮助论坛。</span><span class="sxs-lookup"><span data-stu-id="a5079-159">UtterAccess is the premier Microsoft Access wiki and help forum.</span></span>

- [<span data-ttu-id="a5079-160">DAO 和 ADO 之间进行选择</span><span class="sxs-lookup"><span data-stu-id="a5079-160">Choosing between DAO and ADO</span></span>](https://www.utteraccess.com/wiki/index.php/choosing_between_dao_and_ado)

<span data-ttu-id="a5079-161"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="a5079-161"><<<<<<< HEAD</span></span>

=======
<br/>
>>>>>>> <span data-ttu-id="a5079-162">master</span><span class="sxs-lookup"><span data-stu-id="a5079-162">master</span></span>

