---
<<<<<<< 标头标题： 将 DAO 代码转换为 ADO TOCTitle： 将 DAO 代码转换为 ADO ms:assetid: 4720906b-d6b1-aa6d-3b18-ff828d16acae ms:mtpsurl: https://msdn.microsoft.com/library/Ff193201(v=office.15) ms:contentKeyID: 48544585 ms.date: 09/18/2015年 === 标题： 转换 DAOADO TOCTitle 代码： ADO ms:assetid 转换 DAO 代码： 4720906b-d6b1-aa6d-3b18-ff828d16acae ms:mtpsurl: https://msdn.microsoft.com/library/Ff193201(v=office.15) ms:contentKeyID: 48544585 ms.date: 10/16/2018
>>>>>>> 主 mtps_version: office.15.aspx f1_keywords:
- vbaac10.chm5267115 f1_categories:
- Office.Version=v15
---

<<<<<<< 标头
# <a name="converting-dao-code-to-ado"></a>将 DAO 代码转换为 ADO
=======
# <a name="convert-dao-code-to-ado"></a>将 DAO 代码转换为 ADO
>>>>>>> master

**适用于**： Access 2013 |Office 2013

> [!NOTE]
> 3.6 的 DAO 库版本不提供或支持在 Access 中。

## <a name="dao-to-ado-object-map"></a>DAO 到 ADO 对象映射

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><strong>DAO</strong></p></th>
<<<<<<< 标头
<th><p><strong>ADO(ADODB)</strong></p></th>
=======
<th><p><strong>ADO (ADODB)</strong></p></th>
>>>>>>>主控形状
<th><p><strong>注意</strong></p></th>
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
<td><p>动态集类型</p></td>
<td><p>键集</p></td>
<<<<<<< 标头
<td><p>在记录集中检索指向记录的指针集合</p></td>
=======
<td><p>检索到 recordset 中记录指针的一组。</p></td>
>>>>>>>主控形状
</tr>
<tr class="even">
<td><p>快照类型</p></td>
<td><p>静态</p></td>
<<<<<<< 标头
<td><p>两者都检索全部记录，但是“静态”型记录集可以更新。</p></td>
</tr>
<tr class="odd">
<td><p>表类型</p></td>
<td><p>带 adCmdTableDirect 选项的键集</p></td>
=======
<td><p>两者都检索全部记录，但可以更新静态记录。</p></td>
</tr>
<tr class="odd">
<td><p>表类型</p></td>
<td><p>使用 adCmdTableDirect 选项的键集。</p></td>
>>>>>>>主控形状
<td><p></p></td>
</tr>
<tr class="even">
<td><p>Field</p></td>
<td><p>Field</p></td>
<<<<<<< 标头
<td><p>在记录集中引用时</p></td>
=======
<td><p>当 recordset 中引用。</p></td>
>>>>>>>主控形状
</tr>
</tbody>
</table>

<br/>
<br/>

### <a name="dao"></a>DAO

#### <a name="open-a-recordset"></a>打开记录集

```vb
 Dim db as Database
 Dim rs as DAO.Recordset
 Set db = CurrentDB()
 Set rs = db.OpenRecordset("Employees")
```

#### <a name="edit-a-recordset"></a>编辑记录集

```vb
 rs.Edit 
 rs("TextFieldName") = "NewValue"
 rs.Update
```

### <a name="ado"></a>ADO

#### <a name="open-a-recordset"></a>打开记录集

```vb
 Dim rs as New ADODB.Recordset
 rs.Open "Employees", CurrentProject.Connection, _
         adOpenKeySet, adLockOptimistic
```

#### <a name="edit-a-recordset"></a>编辑记录集

```vb
 rs("TextFieldName") = "NewValue" 
 rs.Update
```


> [!NOTE]
<<<<<<< 标头移动在没有先使用**CancelUpdate**方法将隐含执行**Update**方法从当前记录**MoveNext、 MoveLast MoveFirst，MovePrevious**通过重点。
> === 焦点从当前记录移通过**MoveNext、 MoveLast、 MoveFirst、 MovePrevious**没有先使用**CancelUpdate**方法隐式执行**Update**方法。
>>>>>>> master

### <a name="about-the-contributors"></a>关于参与者

**链接提供** [UtterAccess](https://www.utteraccess.com)社区。 UtterAccess 是主要的 Microsoft Access Wiki 和帮助论坛。

- [DAO 和 ADO 之间进行选择](https://www.utteraccess.com/wiki/index.php/choosing_between_dao_and_ado)

<<<<<<< 标头

=======
<br/>
>>>>>>> master

