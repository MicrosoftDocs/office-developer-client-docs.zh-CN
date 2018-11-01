---
title: 跳转到记录
TOCTitle: Jumping to a Record
ms:assetid: 27177bbe-066c-aeb0-6dfd-45d8c2a87487
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249033(v=office.15)
ms:contentKeyID: 48543829
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: c88c7c5643559dabf3304863417c526a9fd15354
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25873269"
---
# <a name="jumping-to-a-record"></a>跳转到记录


**适用于**： Access 2013、 Office 2013

使用 [Move](move-method-ado.md) 方法可以在 **Recordset** 中前后移动指定数量的记录，语法如下：

```vb 
 
oRs.Move NumRecords, Start
```

所有的 **Recordset** 对象都支持 **Move** 方法。

如果 *NumRecords* 参数大于零，则当前记录的位置会（朝着 **Recordset** 的末尾）向前移动；如果 *NumRecords* 小于零，则当前记录的位置会（朝着 **Recordset** 的开头）向后移动。

如果 **Move** 调用会将当前记录的位置移到第一个记录前面的某个点，则 ADO 会将当前的记录设置为 **Recordset** 中第一个记录前面的位置（**BOF** 为 **True**）。当 **BOF** 属性已经为 **True** 时，如果尝试向后移动，则会生成错误。

如果 **Move** 调用会将当前记录的位置移到最后一个记录后面的某个点，则 ADO 会将当前的记录设置为 **Recordset** 中最后一个记录后面的位置（**EOF** 为 **True**）。当 **EOF** 属性已经为 **True** 时，如果尝试向前移动，则会生成错误。

从空 **Recordset** 对象调用 **Move** 方法将生成错误。

如果*Start*参数中传递一个书签，移动是相对于包含该书签，假定**Recordset**对象支持书签记录。 可使用 [Bookmark](bookmark-property-ado.md) 属性来获取书签。 如果未指定书签，则将相对于当前的记录进行移动。

如果您正在从提供程序，将移动外部的缓存记录当前的组的当前记录位置*NumRecords*参数传递到本地缓存记录使用**CacheSize**属性强制 ADO 检索一组新记录，从目标记录开始。 **CacheSize** 属性确定新检索组的大小，目标记录是检索到的第一个记录。

