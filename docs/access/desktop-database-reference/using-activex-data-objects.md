---
<<<<<<< 标头标题： 使用 ActiveX 数据对象 TOCTitle： 使用 ActiveX 数据对象 ms:assetid: 64055c45-7a27-2296-468a-015362898329 ms:mtpsurl: https://msdn.microsoft.com/library/Ff194969(v=office.15) ms:contentKeyID: 48545279 ms.date: 09/18/2015年 === 标题： 使用 ActiveX数据对象 TOCTitle： 使用 ActiveX 数据对象说明： Microsoft Access 提供三个对象模型用于创建、 维护和管理 Access 数据库及其相关的数据的使用 Visual Basic。
ms:assetid: 64055c45-7a27-2296-468a-015362898329 ms:mtpsurl: https://msdn.microsoft.com/library/Ff194969(v=office.15) ms:contentKeyID: 48545279 ms.date: 10/16/2018
>>>>>>> 主 mtps_version: office.15.aspx f1_keywords:
- vbaac10.chm5285627 f1_categories:
- Office.Version=v15
---

<<<<<<< 标头
# <a name="using-activex-data-objects"></a>使用 ActiveX 数据对象


**适用于**： Access 2013 |Office 2013

<a name="microsoft-access-provides-three-object-models-to-use-in-the-creation-maintaining-and-managing-of-your-access-databases-and-their-related-data-by-using-visual-basic"></a>Microsoft Access 提供了三种对象模型，使用 Visual Basic 来创建、维护和管理 Access 数据库及其相关数据时要用到这些对象模型。
=======
# <a name="use-activex-data-objects"></a>使用 ActiveX 数据对象

**适用于**： Access 2013 |Office 2013

Microsoft Access 提供了三个对象模型用于创建、 维护和管理 Access 数据库及其相关的数据的使用 Visual Basic。
>>>>>>> master

## <a name="microsoft-activex-data-objects-ado"></a>Microsoft ActiveX 数据对象 (ADO)

ADO 包含在给定数据源中创建、维护和删除记录所需的对象。

<<<<<<< 标头
## <a name="microsoft-ado-ext-for-ddl-and-security-adox"></a>Microsoft ADO Ext. for DDL and Security (ADOX)

ADOX 除了提供管理安全性所需的对象之外，还提供了新建数据库及其所含对象所需的"数据定义语言 (DDL)"对象。

**Microsoft Jet and Replication Objects 2.5 Library (JRO)**

<a name="since-ado-objects-were-designed-to-work-with-many-databases-in-addition-to-microsoft-jet-databases-functionality-specific-to-jet-was-broken-out-into-the-jro-library"></a>因为 ADO 对象是为了与 Microsoft Jet 数据库以及其他许多数据库一起使用而设计的，所以 Jet 所特有的功能被分解到 JRO 库中。
=======
## <a name="microsoft-ado-ext-for-ddl-and-security-adox"></a>Microsoft ADO 分机 DDL 和安全性 (ADOX)

ADOX 提供所需创建一个新数据库的数据定义语言 (DDL) 对象和管理安全性所需的对象除了其所含的对象。

### <a name="microsoft-jet-and-replication-objects-25-library-jro"></a>Microsoft Jet 和复制对象 2.5 库 (JRO)

因为 ADO 对象已旨在能够使用 Microsoft Jet 数据库许多数据库，特定于 Jet 功能被分解到 JRO 库。
>>>>>>> master

下表列出了每个对象模型所提供的功能并与 DAO 相比较。

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><p>功能</p></th>
<th><p>DAO</p></th>
<th><p>ADO1</p></th>
<th><p>ADOX2</p></th>
<th><p>JRO<br />
<<<<<<< 标头 (仅限于 mdb)</p></th>
=== (仅适用于 Mdb)</p></th>
>>>>>>> master
</tr>
</thead>
<tbody>
<tr class="odd">
<<<<<<< 标头
<td><p>创建记录集</p></td>
=======
<td><p>创建记录集。</p></td>
>>>>>>>主控形状
<td><p>X</p></td>
<td><p>X</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<<<<<<< 标头
<td><p>编辑“启动”属性</p></td>
=======
<td><p>编辑启动属性。</p></td>
>>>>>>>主控形状
<td><p>X</p></td>
<td><p>X**</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<<<<<<< 标头
<td><p>支持 ANSI92 SQL***</p></td>
=======
<td><p>支持 ANSI92 SQL.* * *</p></td>
>>>>>>>主控形状
<td><p></p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<<<<<<< 标头
<td><p>创建表</p></td>
=======
<td><p>创建表。</p></td>
>>>>>>>主控形状
<td><p>X</p></td>
<td><p></p></td>
<td><p>X</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<<<<<<< 标头
<td><p>新建数据库</p></td>
=======
<td><p>创建新数据库。</p></td>
>>>>>>>主控形状
<td><p>X</p></td>
<td><p></p></td>
<td><p>X*</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<<<<<<< 标头
<td><p>编辑现有表属性</p></td>
=======
<td><p>编辑现有表属性。</p></td>
>>>>>>>主控形状
<td><p>X</p></td>
<td><p></p></td>
<td><p>X</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<<<<<<< 标头
<td><p>创建表关系</p></td>
=======
<td><p>创建表关系。</p></td>
>>>>>>>主控形状
<td><p>X</p></td>
<td><p></p></td>
<td><p>X*</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<<<<<<< 标头
<td><p>编辑安全设置</p></td>
=======
<td><p>编辑安全设置。</p></td>
>>>>>>>主控形状
<td><p>X</p></td>
<td><p></p></td>
<td><p>X*</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<<<<<<< 标头
<td><p>对列数据的“压缩”属性的支持</p></td>
=======
<td><p>支持对列数据压缩属性。</p></td>
>>>>>>>主控形状
<td><p></p></td>
<td><p></p></td>
<td><p>X</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<<<<<<< 标头
<td><p>编辑已保存、基本 SQL 查询或视图</p></td>
=======
<td><p>编辑保存、 基本 SQL 查询或视图。</p></td>
>>>>>>>主控形状
<td><p>X</p></td>
<td><p></p></td>
<td><p>X*</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>创建只能通过代码访问的永久查询。</p></td>
<td><p></p></td>
<td><p></p></td>
<td><p>X*</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>创建通过数据库容器/UI 和代码访问的查询。</p></td>
<td><p>X</p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<<<<<<< 标头
<td><p>压缩/编码数据库</p></td>
=======
<td><p>压缩/编码数据库。</p></td>
>>>>>>>主控形状
<td><p>X</p></td>
<td><p></p></td>
<td><p></p></td>
<td><p>X4</p></td>
</tr>
<tr class="even">
<<<<<<< 标头
<td><p>刷新缓存</p></td>
=======
<td><p>刷新缓存。</p></td>
>>>>>>>主控形状
<td><p>X</p></td>
<td><p></p></td>
<td><p></p></td>
<td><p>X</p></td>
</tr>
<tr class="odd">
<<<<<<< 标头
<td><p>使得数据库可复制</p></td>
=======
<td><p>使数据库变为可复制。</p></td>
>>>>>>>主控形状
<td><p>X</p></td>
<td><p></p></td>
<td><p></p></td>
<td><p>X3</p></td>
</tr>
<tr class="even">
<<<<<<< 标头
<td><p>制作数据库副本</p></td>
=======
<td><p>制作数据库副本。</p></td>
>>>>>>>主控形状
<td><p>X</p></td>
<td><p></p></td>
<td><p></p></td>
<td><p>X3</p></td>
</tr>
<tr class="odd">
<<<<<<< 标头
<td><p>使副本同步</p></td>
=======
<td><p>将副本同步。</p></td>
>>>>>>>主控形状
<td><p>X</p></td>
<td><p></p></td>
<td><p></p></td>
<td><p>X3</p></td>
</tr>
<tr class="even">
<<<<<<< 标头
<td><p>编辑数据库属性</p></td>
=======
<td><p>编辑数据库属性。</p></td>
>>>>>>>主控形状
<td><p>X</p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<<<<<<< 标头
<td><p>创建自定义数据库属性</p></td>
=======
<td><p>创建自定义数据库属性。</p></td>
>>>>>>>主控形状
<td><p>X</p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<<<<<<< 标头
<td><p>编辑表列属性</p></td>
=======
<td><p>编辑表列属性。</p></td>
>>>>>>>主控形状
<td><p>X</p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
</tbody>
</table>


\* 仅当使用 Microsoft Access 数据库时才可用。以后的 SQL 提供程序版本可能会在 Microsoft Access 项目 (.adp) 中提供该功能。

\*\* 仅当使用 Access 项目时才可用。

<<<<<<< 标头\* \* \*尽管 Access 数据库引擎支持某些 ANSI 92 SQL 它尚不存在完全 ANSI92。

1使用 **Connection** 对象来引用数据库

2使用 **Catalog** 对象来引用数据库

3使用 **Replica** 对象来引用数据库

4使用 **JetEngine** 对象来引用数据库


> [!NOTE]
> <a name="punlike-dao-ado-and-adox-objects-can-perform-the-marked-actions-in-databases-other-then-jet-as-long-as-the-provider-for-those-databases-supports-that-actionp"></a><P>[!注释] 与 DAO 不同，ADO 和 ADOX 对象可以在非 Jet 数据库中执行所标出的操作（只要这些数据库的提供程序支持该操作）。</P>
=======
\*\*\*尽管 Access 数据库引擎支持某些 ANSI 92 SQL，但它尚未完全遵守 ANSI92。

1 使用**Connection**对象来引用数据库。

使用**Catalog**对象来引用数据库 2。

3 使用**副本**对象来引用数据库。

4 使用**JetEngine**对象来引用数据库。


> [!NOTE]
> 与 DAO，不同 ADO 和 ADOX 对象可以执行标记的操作之外 Jet 数据库中，只要这些数据库的提供程序支持的操作。
>>>>>>> master


