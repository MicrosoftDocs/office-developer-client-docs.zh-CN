---
title: 数据库同步方法 (DAO)
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
localization_priority: Normal
ms.openlocfilehash: 411948f3c0ac4d6c353cd2722136dffb6a25fb17
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32294706"
---
# <a name="databasesynchronize-method-dao"></a>数据库同步方法 (DAO)


**适用于**：Access 2013、Office 2013

同步两个副本。 （仅适用于 Microsoft Access 工作区）。

## <a name="syntax"></a>语法

*表达式*。Synchronize (***DbPathName***, ***ExchangeType***)

*表达式*一个代表**Database**对象的变量。

## <a name="parameters"></a>参数

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
<td><p><em>DbPathName</em></p></td>
<td><p>必需</p></td>
<td><p><strong>String</strong></p></td>
<td><p>指向数据库将与其同步的目标副本的路径。</p></td>
</tr>
<tr class="even">
<td><p><em>ExchangeType</em></p></td>
<td><p>可选</p></td>
<td><p><strong>Variant</strong></p></td>
<td><p>一个<strong><a href="synchronizetypeenum-enumeration-dao.md">SynchronizeTypeEnum</a></strong>常量, 该常量指示两个数据库之间的同步更改的方向。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>注解

可以使用 **Synchronize** 交换两个数据库之间的数据和设计更改。 始终先发生设计更改。 要交换数据，两个数据库必须在相同的设计级别。 例如, **dbRepExportChanges**类型的交换可能会导致在副本上进行设计更改, 即使数据更改仅流从数据库到 DbPathName。

DbPathName 中标识的副本必须是同一副本集的一部分。 如果两个副本具有相同的 **ReplicaID** 属性设置或者是两个不同副本集的设计母版，则同步失败。

通过 Internet 同步两个副本时，必须使用 **dbRepSyncInternet** 常量。 在这种情况下, 您可以为 DbPathName 参数指定统一资源定位器 (URL) 地址, 而不是指定局域网路径。


> [!NOTE]
> [!注释] 不能将部分副本与其他部分副本同步。 有关详细信息，请参阅 [PopulatePartial](database-populatepartial-method-dao.md) 方法。


