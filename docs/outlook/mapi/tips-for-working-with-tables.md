---
title: 使用表的提示
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: adb4d589-7e03-4222-8717-898ef397c6b6
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 451bab57d4e2e8669a25d119f9ce28a8f78e628f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778968"
---
# <a name="tips-for-working-with-tables"></a>使用表的提示

  
  
**适用于**： Outlook 
  
使用 MAPI 表是一个小喜欢使用关系数据库表。 用户可以限制的行和视图中的列数，并指定它们的顺序。 行可以检索到的一个一次或组中。 可以将跟踪的当前位置光标移动到表中的特定位置。 
  
若要使用表，客户端使用的只读接口， [IMAPITable: IUnknown](imapitableiunknown.md)，而服务提供商，具体取决于他们所拥有的数据的表基于是否可以使用任一**IMAPITable**或[ITableData: IUnknown](itabledataiunknown.md)。 在这些接口定义的操作可分类为操作的表的所有用户执行操作或可以调用和尚未为广泛使用因为它们更高级的操作。 某些高级操作是实现; 起来较复杂其他人不更复杂，但对少数人的 MAPI 组件感兴趣。 
  
更常见操作包括：
  
- 列操作影响单个列。 包括指定要包含在列集和在其中他们应包含的顺序中的属性。
    
- 行操作会影响单个行。 数据检索和维护操作包括： 添加、 删除和修改单个一行或多行。
    
- 全局操作，影响整个表格。 包括事件通知，搜索和排序。
    
## <a name="see-also"></a>另请参阅



[MAPI 表](mapi-tables.md)

