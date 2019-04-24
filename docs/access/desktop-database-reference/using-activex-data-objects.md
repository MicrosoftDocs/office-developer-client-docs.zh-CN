---
title: 使用 ActiveX 数据对象
TOCTitle: Use ActiveX Data Objects
description: Microsoft Access 提供了三种对象模型, 可用于创建、维护和管理 Access 数据库及其相关数据 (使用 Visual Basic)。
ms:assetid: 64055c45-7a27-2296-468a-015362898329
ms:mtpsurl: https://msdn.microsoft.com/library/Ff194969(v=office.15)
ms:contentKeyID: 48545279
ms.date: 10/16/2018
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm5285627
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: 3b530db43a816e66b9fbef254984142aadf0b841
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32312738"
---
# <a name="use-activex-data-objects"></a>使用 ActiveX 数据对象

**适用于**：Access 2013、Office 2013

Microsoft Access 提供了三种对象模型, 可用于创建、维护和管理 Access 数据库及其相关数据 (使用 Visual Basic)。

## <a name="microsoft-activex-data-objects-ado"></a>Microsoft ActiveX 数据对象 (ADO)

ADO 包含在给定数据源中创建、维护和删除记录所需的对象。

## <a name="microsoft-ado-ext-for-ddl-and-security-adox"></a>Microsoft ADO ext (针对 DDL 和安全性) (ADOX)

除了管理安全性所需的对象之外, ADOX 还提供了创建新数据库及其包含的对象所需的数据定义语言 (DDL) 对象。

### <a name="microsoft-jet-and-replication-objects-25-library-jro"></a>Microsoft Jet 和 Replication 对象2.5 库 (JRO)

由于 ADO 对象设计为与 Microsoft Jet 数据库之外的多个数据库配合使用, 因此特定于 Jet 的功能被分解为 JRO 库。

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
(仅限 MDBs)</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>创建记录集。</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>编辑启动属性。</p></td>
<td><p>X</p></td>
<td><p>X * *</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>支持遵守 ansi92 SQL. * * *</p></td>
<td><p></p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>创建表。</p></td>
<td><p>X</p></td>
<td><p></p></td>
<td><p>X</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>创建新数据库。</p></td>
<td><p>X</p></td>
<td><p></p></td>
<td><p>版</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>编辑现有的表属性。</p></td>
<td><p>X</p></td>
<td><p></p></td>
<td><p>X</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>创建表关系。</p></td>
<td><p>X</p></td>
<td><p></p></td>
<td><p>版</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>编辑安全设置。</p></td>
<td><p>X</p></td>
<td><p></p></td>
<td><p>版</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>支持对列数据进行压缩属性。</p></td>
<td><p></p></td>
<td><p></p></td>
<td><p>X</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>编辑存储的、基本的 SQL 查询或视图。</p></td>
<td><p>X</p></td>
<td><p></p></td>
<td><p>版</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>创建只能通过代码访问的永久查询。</p></td>
<td><p></p></td>
<td><p></p></td>
<td><p>版</p></td>
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
<td><p>压缩/编码数据库。</p></td>
<td><p>X</p></td>
<td><p></p></td>
<td><p></p></td>
<td><p>四</p></td>
</tr>
<tr class="even">
<td><p>刷新缓存。</p></td>
<td><p>X</p></td>
<td><p></p></td>
<td><p></p></td>
<td><p>X</p></td>
</tr>
<tr class="odd">
<td><p>使数据库可同步复制。</p></td>
<td><p>X</p></td>
<td><p></p></td>
<td><p></p></td>
<td><p>X3</p></td>
</tr>
<tr class="even">
<td><p>生成数据库副本。</p></td>
<td><p>X</p></td>
<td><p></p></td>
<td><p></p></td>
<td><p>X3</p></td>
</tr>
<tr class="odd">
<td><p>同步副本。</p></td>
<td><p>X</p></td>
<td><p></p></td>
<td><p></p></td>
<td><p>X3</p></td>
</tr>
<tr class="even">
<td><p>编辑数据库属性。</p></td>
<td><p>X</p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>创建自定义数据库属性。</p></td>
<td><p>X</p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>编辑表列属性。</p></td>
<td><p>X</p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
</tbody>
</table>


\* 仅当使用 Microsoft Access 数据库时才可用。以后的 SQL 提供程序版本可能会在 Microsoft Access 项目 (.adp) 中提供该功能。

\*\* 仅当使用 Access 项目时才可用。

\*\*\*虽然 Access 数据库引擎支持某些 ANSI 92 SQL, 但它尚未完全符合遵守 ansi92。

1使用**Connection**对象引用数据库。

2使用**Catalog**对象引用数据库。

3使用**副本**对象引用数据库。

4使用**JetEngine**对象来引用数据库。


> [!NOTE]
> 与 DAO 不同, ADO 和 ADOX 对象可以在除 Jet 之外的数据库中执行标记的操作, 只要这些数据库的提供程序支持该操作。


