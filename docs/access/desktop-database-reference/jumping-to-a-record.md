---
title: 跳到记录
TOCTitle: Jumping to a record
ms:assetid: 27177bbe-066c-aeb0-6dfd-45d8c2a87487
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249033(v=office.15)
ms:contentKeyID: 48543829
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 08d8a3d7b3d6012867a91aa306f45872bfebb2e1
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32290784"
---
# <a name="jumping-to-a-record"></a>跳到记录


**适用于**：Access 2013、Office 2013

使用 [Move](move-method-ado.md) 方法可以在 **Recordset** 中前后移动指定数量的记录，语法如下：

```vb 
 
oRs.Move NumRecords, Start
```

所有的 **Recordset** 对象都支持 **Move** 方法。

如果 *NumRecords* 参数大于零，则当前记录的位置会（朝着 **Recordset** 的末尾）向前移动；如果 *NumRecords* 小于零，则当前记录的位置会（朝着 **Recordset** 的开头）向后移动。

如果 **Move** 调用会将当前记录的位置移到第一个记录前面的某个点，则 ADO 会将当前的记录设置为 **Recordset** 中第一个记录前面的位置（**BOF** 为 **True**）。当 **BOF** 属性已经为 **True** 时，如果尝试向后移动，则会生成错误。

如果 **Move** 调用会将当前记录的位置移到最后一个记录后面的某个点，则 ADO 会将当前的记录设置为 **Recordset** 中最后一个记录后面的位置（**EOF** 为 **True**）。当 **EOF** 属性已经为 **True** 时，如果尝试向前移动，则会生成错误。

从空 **Recordset** 对象调用 **Move** 方法将生成错误。

如果在 *Start* 参数中传递一个书签，则将相对于具有该书签的记录进行移动，假定 **Recordset** 对象支持书签。可使用 [Bookmark](bookmark-property-ado.md) 属性来获取书签。如果未指定书签，则将相对于当前的记录进行移动。

如果要使用 **CacheSize** 属性在本地缓存提供程序的记录，而且所传递 *NumRecords* 参数会将当前记录的位置移到缓存记录的当前组外部，则会强制 ADO 检索一组新记录（从目标记录开始）。**CacheSize** 属性确定新检索组的大小，目标记录是检索到的第一个记录。

