---
title: 记录集定位
TOCTitle: Recordset positioning
ms:assetid: 1b8b08d5-a11c-ec6e-201c-1405171a1264
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248955(v=office.15)
ms:contentKeyID: 48543546
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 5116adbf68e4e98c7fbda8285348e00638465742
ms.sourcegitcommit: 558d09fad81f8d80b5ad0edd21934fc09c098f2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25946270"
---
# <a name="recordset-positioning"></a>记录集定位


**适用于**： Access 2013、 Office 2013

使用 **AbsolutePosition** 属性，可以根据记录在 **Recordset** 对象中的序号位置移动到记录，或确定当前记录的序号位置。提供程序必须支持相应的功能，此属性才可用。

**AbsolutePosition** 从 1 开始，如果当前的记录就 **Recordset** 中的第一个记录，此属性将等于 1。前面提到，可以从 **RecordCount** 属性获取 **Recordset** 对象中的总记录数。

设置 **AbsolutePosition** 属性时，即使设置为当前缓存中的记录，ADO 也会向缓存中重新加载从指定的记录开始的一组新记录。 **CacheSize** 属性将确定此组的大小。


> [!NOTE]
> <P>[!注释] 不应当将 <STRONG>AbsolutePosition</STRONG> 属性用作代理记录号。当删除给定记录前面的记录时，给定记录的位置会发生变化。同样，如果重新查询或重新打开 <STRONG>Recordset</STRONG> 对象，将无法保证给定的记录会具有相同的 <STRONG>AbsolutePosition</STRONG> 。建议使用书签来返回或保留给定位置，而且这是在各种类型的 <STRONG>Recordset</STRONG> 对象之间定位的唯一方法。</P>


