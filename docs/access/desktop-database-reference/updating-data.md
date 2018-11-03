---
title: 更新数据 （访问桌面数据库参考 （英文）
TOCTitle: Updating Data
ms:assetid: 02e82066-77c8-cbb2-db28-98e2fc94404c
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248794(v=office.15)
ms:contentKeyID: 48542970
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 70ca34183d135c6907a185984b02b394776bfda4
ms.sourcegitcommit: 558d09fad81f8d80b5ad0edd21934fc09c098f2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25944219"
---
# <a name="updating-data"></a>更新数据


**适用于**： Access 2013、 Office 2013

更新行为和更新功能在很大程度上取决于更新模式（锁定类型）、游标类型和游标位置。

使用 **Update** 方法，可以保存在调用 **AddNew** 方法或更改现有记录中的任何字段值以来，对 **Recordset** 对象中的当前记录进行的任何更改。 **Recordset** 对象必须支持更新。

如果 **Recordset** 对象支持批更新，则在调用 **UpdateBatch** 方法前，可以在本地缓存对一个或多个记录所做的多次更改。如果在调用 **UpdateBatch** 方法时正在编辑当前记录或添加新记录，则 ADO 在将批更改传输到提供程序前，将自动调用 **Update** 方法将所有挂起的更改保存到当前记录。

在调用 **Update** 或 **UpdateBatch** 方法之后，当前的记录将保持最新。

本节包括下列主题：

- [立即模式](immediate-mode.md)
- [事务处理](transaction-processing.md)
- [批模式 (ADO)](batch-mode.md)

