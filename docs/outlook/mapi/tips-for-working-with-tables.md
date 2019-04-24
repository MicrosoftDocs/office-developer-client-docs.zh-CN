---
title: 使用表格的提示
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: adb4d589-7e03-4222-8717-898ef397c6b6
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 8f310c6331df941d3093b276b6dec47f740412e1
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32339646"
---
# <a name="tips-for-working-with-tables"></a>使用表格的提示

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
使用 MAPI 表与处理关系数据库表有点相似。 用户可以限制视图中的行数和列数, 并指定它们的顺序。 可以一次检索一个行, 也可以按组检索行。 可以将当前位置跟踪的游标移到表中的特定位置。 
  
若要使用表, 客户端将使用只读接口 ( [imapitable: IUnknown](imapitableiunknown.md), 而服务提供程序), 这取决于其是否拥有表所基于的数据, 可以使用**IMAPITable**或[ITableData: IUnknown](itabledataiunknown.md)。 可以将这些接口中定义的操作作为所有表的用户执行或可以调用的操作和由于更高级而不会被广泛使用的操作进行分类的操作。 某些高级操作更复杂, 可以实现;有些不复杂, 但对少数 MAPI 组件很有意义。 
  
更常见的操作是:
  
- 影响单个列的列操作。 这些属性包括指定要包含在列集中的属性以及应包含的属性顺序。
    
- 行操作, 它会影响单个行。 其中包括数据检索和维护操作: 添加、删除和修改单个行或行。
    
- 全局操作, 这将影响整个表。 其中包括事件通知、搜索和排序。
    
## <a name="see-also"></a>另请参阅



[MAPI 表](mapi-tables.md)

