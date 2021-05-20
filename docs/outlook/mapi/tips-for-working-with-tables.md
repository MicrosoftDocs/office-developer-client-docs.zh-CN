---
title: 使用技巧表的索引
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: adb4d589-7e03-4222-8717-898ef397c6b6
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 8f310c6331df941d3093b276b6dec47f740412e1
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33439735"
---
# <a name="tips-for-working-with-tables"></a>使用技巧表的索引

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
使用 MAPI 表与使用 MAPI 表关系数据库类似。 用户可以限制视图中的行数和列数并指定其顺序。 可以一次检索一行，也可以成组检索行。 跟踪当前位置的游标可以移动到表中的特定位置。 
  
为了使用表，客户端使用只读接口 [IMAPITable ： IUnknown](imapitableiunknown.md)，而服务提供商可以使用 **IMAPITable** 或 [ITableData ：IUnknown，](itabledataiunknown.md)具体取决于它们是否拥有该表所基于的数据。 这些接口中定义的操作可以归类为表的所有用户都执行的操作，也可以调用和由于更高级而未广泛使用的操作。 某些高级操作要实施得更复杂;其他不复杂，但对少数 MAPI 组件感兴趣。 
  
更常见的操作包括：
  
- 列操作，影响单个列。 这些属性包括指定列集中包含的属性以及这些属性的包含顺序。
    
- 行操作，影响单行。 其中包括数据检索和维护操作：添加、删除和修改一行或多行。
    
- 影响整个表的全局操作。 其中包括事件通知、搜索和排序。
    
## <a name="see-also"></a>另请参阅



[MAPI 表](mapi-tables.md)

