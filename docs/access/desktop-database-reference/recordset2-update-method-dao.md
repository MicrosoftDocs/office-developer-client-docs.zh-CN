---
title: Recordset2.Update Method (DAO)
TOCTitle: Update Method
ms:assetid: 1b47606a-e79c-23f1-b120-46d1429bc167
ms:mtpsurl: https://msdn.microsoft.com/library/Ff845700(v=office.15)
ms:contentKeyID: 48543537
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1052882
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 223846a50dd06cfe1b47f954e1dc55a40b9cc083
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25869314"
---
# <a name="recordset2update-method-dao"></a><span data-ttu-id="c5c48-102">Recordset2.Update Method (DAO)</span><span class="sxs-lookup"><span data-stu-id="c5c48-102">Recordset2.Update Method (DAO)</span></span>


<span data-ttu-id="c5c48-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="c5c48-103">**Applies to**: Access 2013, Office 2013</span></span>

## <a name="syntax"></a><span data-ttu-id="c5c48-104">语法</span><span class="sxs-lookup"><span data-stu-id="c5c48-104">Syntax</span></span>

<span data-ttu-id="c5c48-105">*表达式*。更新 （***UpdateType***，***强制***）</span><span class="sxs-lookup"><span data-stu-id="c5c48-105">*expression* .Update(***UpdateType***, ***Force***)</span></span>

<span data-ttu-id="c5c48-106">*表达式*一个表示**Recordset2**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="c5c48-106">*expression* A variable that represents a **Recordset2** object.</span></span>

### <a name="parameters"></a><span data-ttu-id="c5c48-107">参数</span><span class="sxs-lookup"><span data-stu-id="c5c48-107">Parameters</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="c5c48-108">名称</span><span class="sxs-lookup"><span data-stu-id="c5c48-108">Name</span></span></p></th>
<th><p><span data-ttu-id="c5c48-109">必需/可选</span><span class="sxs-lookup"><span data-stu-id="c5c48-109">Required/Optional</span></span></p></th>
<th><p><span data-ttu-id="c5c48-110">数据类型</span><span class="sxs-lookup"><span data-stu-id="c5c48-110">Data Type</span></span></p></th>
<th><p><span data-ttu-id="c5c48-111">说明</span><span class="sxs-lookup"><span data-stu-id="c5c48-111">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c5c48-112">UpdateType</span><span class="sxs-lookup"><span data-stu-id="c5c48-112">UpdateType</span></span></p></td>
<td><p><span data-ttu-id="c5c48-113">可选</span><span class="sxs-lookup"><span data-stu-id="c5c48-113">Optional</span></span></p></td>
<td><p><span data-ttu-id="c5c48-114"><strong>Long</strong></span><span class="sxs-lookup"><span data-stu-id="c5c48-114"><strong>Long</strong></span></span></p></td>
<td><p><span data-ttu-id="c5c48-115">一个 <strong><a href="updatetypeenum-enumeration-dao.md">UpdateTypeEnum</a></strong> 常量，指示"设置"中指定的更新类型（仅适用于 ODBCDirect 工作区）。</span><span class="sxs-lookup"><span data-stu-id="c5c48-115">A <strong><a href="updatetypeenum-enumeration-dao.md">UpdateTypeEnum</a></strong> constant indicating the type of update, as specified in Settings (ODBCDirect workspaces only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5c48-116">Force</span><span class="sxs-lookup"><span data-stu-id="c5c48-116">Force</span></span></p></td>
<td><p><span data-ttu-id="c5c48-117">可选</span><span class="sxs-lookup"><span data-stu-id="c5c48-117">Optional</span></span></p></td>
<td><p><span data-ttu-id="c5c48-118"><strong>Boolean</strong></span><span class="sxs-lookup"><span data-stu-id="c5c48-118"><strong>Boolean</strong></span></span></p></td>
<td><p><span data-ttu-id="c5c48-p101">一个 <strong>Boolean</strong> 值，指示是否将更改强制到数据库中，而不管自从 <strong><a href="recordset-addnew-method-dao.md">AddNew</a></strong> 、 <strong><a href="fields-delete-method-dao.md">Delete</a></strong> 或 <strong><a href="recordset2-edit-method-dao.md">Edit</a></strong> 调用以来，其他用户是否更改了基础数据。如果为 <strong>True</strong> ，则会强制更改，并且只是覆盖由其他用户所做的更改。如果为 <strong>False</strong> （默认值），在更新处于待定状态时由其他用户所做的更改将导致更改对冲突的更改失败。不发生错误，但是 <strong><a href="recordset-batchcollisioncount-property-dao.md">BatchCollisionCount</a></strong> 和 <strong>BatchCollisions</strong> 属性将分别指示冲突数和受冲突影响的行数（仅适用于 ODBCDirect 工作区）。  </span><span class="sxs-lookup"><span data-stu-id="c5c48-p101">A <strong>Boolean</strong> value indicating whether or not to force the changes into the database, regardless of whether the underlying data has been changed by another user since the <strong><a href="recordset-addnew-method-dao.md">AddNew</a></strong>, <strong><a href="fields-delete-method-dao.md">Delete</a></strong>, or <strong><a href="recordset2-edit-method-dao.md">Edit</a></strong> call. If <strong>True</strong>, the changes are forced and changes made by other users are simply overwritten. If <strong>False</strong> (default), changes made by another user while the update is pending will cause the update to fail for those changes that are in conflict. No error occurs, but the <strong><a href="recordset-batchcollisioncount-property-dao.md">BatchCollisionCount</a></strong> and <strong>BatchCollisions</strong> properties will indicate the number of conflicts and the rows affected by conflicts, respectively (ODBCDirect workspaces only).</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="c5c48-123">注解</span><span class="sxs-lookup"><span data-stu-id="c5c48-123">Remarks</span></span>

<span data-ttu-id="c5c48-124">使用 **Update** 可保存当前记录以及对它所做的任何更改。</span><span class="sxs-lookup"><span data-stu-id="c5c48-124">Use **Update** to save the current record and any changes you've made to it.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="c5c48-125">[!重要信息] 在以下情况下，对当前记录所做的更改将会丢失：</span><span class="sxs-lookup"><span data-stu-id="c5c48-125">Changes to the current record are lost if:</span></span>
> - <span data-ttu-id="c5c48-126">使用了 **Edit** 或 **AddNew** 方法，然后在没有事先使用 **Update** 的情况下移到另一条记录。</span><span class="sxs-lookup"><span data-stu-id="c5c48-126">You use the **Edit** or **AddNew** method, and then move to another record without first using **Update**.</span></span>
> - <span data-ttu-id="c5c48-127">使用了 **Edit** 或 **AddNew** ，然后在没有事先使用 **Update** 的情况下再次使用 **Edit** 或 **AddNew** 。</span><span class="sxs-lookup"><span data-stu-id="c5c48-127">You use **Edit** or **AddNew**, and then use **Edit** or **AddNew** again without first using **Update**.</span></span>
> - <span data-ttu-id="c5c48-128">将 **[Bookmark](recordset2-bookmark-property-dao.md)** 属性设置为另一条记录。</span><span class="sxs-lookup"><span data-stu-id="c5c48-128">You set the **[Bookmark](recordset2-bookmark-property-dao.md)** property to another record.</span></span>
> - <span data-ttu-id="c5c48-129">在没有事先使用 **Update** 的情况下关闭了 **Recordset** 。</span><span class="sxs-lookup"><span data-stu-id="c5c48-129">You close the **Recordset** without first using **Update**.</span></span>
> - <span data-ttu-id="c5c48-130">使用 [**CancelUpdate**](recordset2-cancelupdate-method-dao.md) 取消 **Edit** 操作。</span><span class="sxs-lookup"><span data-stu-id="c5c48-130">You cancel the **Edit** operation by using **[CancelUpdate](recordset2-cancelupdate-method-dao.md)**.</span></span>

<span data-ttu-id="c5c48-p102">要编辑一条记录，请使用 **Edit** 方法将当前记录的内容复制到复制缓冲区。如果不首先使用 **Edit** ，在使用 **Update** 或试图更改字段值时将会发生错误。</span><span class="sxs-lookup"><span data-stu-id="c5c48-p102">To edit a record, use the **Edit** method to copy the contents of the current record to the copy buffer. If you don't use **Edit** first, an error occurs when you use **Update** or attempt to change a field's value.</span></span>

<span data-ttu-id="c5c48-133">在 ODBCDirect 工作区中，如果游标库支持批更新，并且使用开放式批锁定选项打开了 **Recordset** ，则可以执行批更新。</span><span class="sxs-lookup"><span data-stu-id="c5c48-133">In an ODBCDirect workspace, you can do batch updates, provided the cursor library supports batch updates, and the **Recordset** was opened with the optimistic batch locking option.</span></span>

<span data-ttu-id="c5c48-134">在 Microsoft Access 工作区中，如果多用户环境中的 **Recordset** 对象的 **LockEdits** 属性设置为 **True** （悲观锁定），那么从使用 **Edit** 开始到执行了 **Update** 方法或取消了编辑的时间范围内，记录将保持锁定状态。</span><span class="sxs-lookup"><span data-stu-id="c5c48-134">In a Microsoft Access workspace, when the **Recordset** object's **LockEdits** property setting is **True** (pessimistically locked) in a multiuser environment, the record remains locked from the time **Edit** is used until the **Update** method is executed or the edit is canceled.</span></span> <span data-ttu-id="c5c48-135">如果 **LockEdits** 属性设置为 **False** （乐观锁定），那会锁定此记录，并且在数据库中对它更新之前，将它与预编辑的记录进行比较。</span><span class="sxs-lookup"><span data-stu-id="c5c48-135">If the **LockEdits** property setting is **False** (optimistically locked), the record is locked and compared with the pre-edited record just before it is updated in the database.</span></span> <span data-ttu-id="c5c48-136">如果自从使用 **Edit** 方法之后记录发生了更改， **Update** 操作将会失败。</span><span class="sxs-lookup"><span data-stu-id="c5c48-136">If the record has changed since you used the **Edit** method, the **Update** operation fails.</span></span> <span data-ttu-id="c5c48-137">Microsoft Access 数据库引擎连接的 ODBC 和可安装的 ISAM 数据库始终使用乐观锁定。</span><span class="sxs-lookup"><span data-stu-id="c5c48-137">Microsoft Access database engine-connected ODBC and installable ISAM databases always use optimistic locking.</span></span> <span data-ttu-id="c5c48-138">若要使用更改继续 **Update** 操作，请再次使用 **Update** 方法。</span><span class="sxs-lookup"><span data-stu-id="c5c48-138">To continue the **Update** operation with your changes, use the **Update** method again.</span></span> <span data-ttu-id="c5c48-139">若要恢复到其他用户记录更改它，刷新当前记录，请使用 Move 0。</span><span class="sxs-lookup"><span data-stu-id="c5c48-139">To revert to the record as the other user changed it, refresh the current record by using Move 0.</span></span>


> [!NOTE]
> <span data-ttu-id="c5c48-p104">[!注释] 若要添加、编辑或删除记录，基础数据源中的记录必须存在唯一索引。如果不存在此索引，在 Microsoft Access 工作区中， **AddNew**、 **Delete** 或 **Edit** 方法调用将发生"权限被拒绝"错误，在 ODBCDirect 工作区中， **Update** 调用将发生"无效参数"错误。</span><span class="sxs-lookup"><span data-stu-id="c5c48-p104">To add, edit, or delete a record, there must be a unique index on the record in the underlying data source. If not, a "Permission denied" error will occur on the **AddNew**, **Delete**, or **Edit** method call in a Microsoft Access workspace, or an "Invalid argument" error will occur on the **Update** call in an ODBCDirect workspace.</span></span>


