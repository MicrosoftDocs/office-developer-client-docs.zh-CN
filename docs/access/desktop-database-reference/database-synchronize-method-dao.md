---
title: Database.Synchronize Method (DAO)
TOCTitle: Synchronize Method
ms:assetid: 5e716a4a-2430-8106-5c34-a02dd28bc4f6
ms:mtpsurl: https://msdn.microsoft.com/library/Ff194659(v=office.15)
ms:contentKeyID: 48545137
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1053357
f1_categories:
- Office.Version=v15
ms.openlocfilehash: c55eab611cae8431a3ff3f2220cdfa8b1923d891
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467213"
---
# <a name="databasesynchronize-method-dao"></a>Database.Synchronize Method (DAO)


**适用于**： Access 2013 |Office 2013

同步两个副本。（仅适用于 Microsoft Access 工作区）。

## <a name="syntax"></a>语法

*表达式*。同步 (***DbPathName***， ***ExchangeType***)

*表达式*一个代表**Database**对象的变量。

### <a name="parameters"></a>参数

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p>名称</p></th>
<th><p>必需/可选</p></th>
<th><p>数据类型</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DbPathName</p></td>
<td><p>必需</p></td>
<td><p><strong>字符串</strong></p></td>
<td><p>指向数据库将与其同步的目标副本的路径。</p></td>
</tr>
<tr class="even">
<td><p>ExchangeType</p></td>
<td><p>可选</p></td>
<td><p><strong>Variant</strong></p></td>
<td><p>一个 <strong><a href="synchronizetypeenum-enumeration-dao.md">SynchronizeTypeEnum</a></strong> 常量，指示朝哪个方向同步两个数据库之间的更改。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>注解

可以使用 **Synchronize** 交换两个数据库之间的数据和设计更改。 始终先发生设计更改。 要交换数据，两个数据库必须在相同的设计级别。 例如，即使数据更改流只会从数据库为 DbPathName 类型**dbRepExportChanges** exchange 可能会导致在副本的设计更改。

DbPathName 中标识的副本必须是同一副本集中的一部分。 如果两个副本具有相同的 **ReplicaID** 属性设置或者是两个不同副本集的设计母版，则同步失败。

通过 Internet 同步两个副本时，必须使用 **dbRepSyncInternet** 常量。 在这种情况下，您指定为 DbPathName 参数而不是指定的本地网络路径的统一资源定位器 (URL) 地址。


> [!NOTE]
> <P>[!注释] 不能将部分副本与其他部分副本同步。有关详细信息，请参阅 <STRONG><A href="database-populatepartial-method-dao.md">PopulatePartial</A></STRONG> 方法。</P>


