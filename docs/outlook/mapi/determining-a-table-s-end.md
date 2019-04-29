---
title: 确定表的结尾
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: c879e972-05f4-4716-8fc2-db5b22f34ca8
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 28892e2d351b8dc9aa864c9eff52c94bb0f20e8f
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33420085"
---
# <a name="determining-a-tables-end"></a>确定表的结尾

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
 一个常见错误是, 在以下情况时, 假定已到达表的末尾: 
  
- [imapitable:: QueryRows](imapitable-queryrows.md)已在循环中调用, 并在循环结束时由[IMAPITable:: GetRowCount](imapitable-getrowcount.md)返回的行数确定。 **GetRowCount**返回的计数并不总是表示表中的确切行数;它是一个大概数。 
    
- 已使用固定的行数调用**QueryRows** , 并且返回的行数较少。 直到**QueryRows**返回行数等于零的行集时, 没有更多的行可供检索。 
    
> [!IMPORTANT]
> 呼叫者唯一的时间是将游标放置在表的末尾, 对于正数行计数或在表的开头, 如果返回值 S_OK 和零行, 则会出现这种情况。 从不返回值 MAPI_E_NOT_FOUND。 
  
## <a name="see-also"></a>另请参阅



[MAPI 表](mapi-tables.md)

