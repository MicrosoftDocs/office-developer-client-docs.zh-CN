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
# <a name="convert-dao-code-to-ado"></a>将 DAO 代码转换为 ADO

**适用于**：Access 2013、Office 2013

> [!NOTE]
> Access 中不提供或支持版本号低于 3.6 的 DAO 库。

## <a name="dao-to-ado-object-map"></a>DAO 到 ADO 的对象映射表

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><strong>DAO</strong></p></th>
<th><p><strong>ADO (ADODB)</strong></p></th>
<th><p><strong>备注</strong></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DBEngine</p></td>
<td><p>无</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>Workspace</p></td>
<td><p>无</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>Database</p></td>
<td><p>Connection</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>Recordset</p></td>
<td><p>Recordset</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>Dynaset-Type</p></td>
<td><p>Keyset</p></td>
<td><p>在记录集中检索指向记录的指针集合。</p></td>
</tr>
<tr class="even">
<td><p>Snapshot-Type</p></td>
<td><p>Static</p></td>
<td><p>两者都检索全部记录，但是 Static 记录集可以更新。</p></td>
</tr>
<tr class="odd">
<td><p>Table-Type</p></td>
<td><p>带 adCmdTableDirect 选项的 Keyset。</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>Field</p></td>
<td><p>Field</p></td>
<td><p>在记录集中引用时。</p></td>
</tr>
</tbody>
</table>

<br/>
<br/>

### <a name="dao"></a>DAO

#### <a name="open-a-recordset"></a>打开 Recordset

```vb
 Dim db as Database
 Dim rs as DAO.Recordset
 Set db = CurrentDB()
 Set rs = db.OpenRecordset("Employees")
```

#### <a name="edit-a-recordset"></a>编辑 Recordset

```vb
 rs.Edit 
 rs("TextFieldName") = "NewValue"
 rs.Update
```

### <a name="ado"></a>ADO

#### <a name="open-a-recordset"></a>打开 Recordset

```vb
 Dim rs as New ADODB.Recordset
 rs.Open "Employees", CurrentProject.Connection, _
         adOpenKeySet, adLockOptimistic
```

#### <a name="edit-a-recordset"></a>编辑 Recordset

```vb
 rs("TextFieldName") = "NewValue" 
 rs.Update
```


> [!NOTE]
> 在没有先使用 **CancelUpdate** 方法而利用 **MoveNext、MoveLast、MoveFirst、MovePrevious** 将焦点从当前记录移开时，会隐含执行 **Update** 方法。

### <a name="about-the-contributors"></a>关于参与者

**链接提供者：**[UtterAccess](https://www.utteraccess.com) 社区。 UtterAccess 是主要的 Microsoft Access Wiki 和帮助论坛。

- [在 DAO 和 ADO 之间进行选择](https://www.utteraccess.com/wiki/index.php/choosing_between_dao_and_ado)

<br/>

