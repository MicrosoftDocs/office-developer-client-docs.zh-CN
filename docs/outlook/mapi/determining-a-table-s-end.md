---
title: 确定表末尾
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: c879e972-05f4-4716-8fc2-db5b22f34ca8
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 7cbf11f16948d582ba36a0b4d20411549b723b38
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774779"
---
# <a name="determining-a-tables-end"></a>确定表末尾

  
  
**适用于**： Outlook 
  
 常见错误是表的假定末尾已达到时： 
  
- 已在循环中，使用由[IMAPITable::GetRowCount](imapitable-getrowcount.md)返回的行计数循环结束调用[IMAPITable::QueryRows](imapitable-queryrows.md) 。 **GetRowCount**返回的计数不始终表示确切的表; 中的行数它是一个大概计数。 
    
- 已使用固定数量的行调用**QueryRows**和返回更少的行。 它是不是直到**QueryRows**返回的行集与等于零，没有要检索的多个行的行数。 
    
> [!IMPORTANT]
> 返回 S_OK 的值和零行时，呼叫者可以假定将光标定位末尾的正行计数的表或负数的行数的表的开头的唯一时间。 将 MAPI_E_NOT_FOUND 永远不会返回值。 
  
## <a name="see-also"></a>另请参阅



[MAPI 表](mapi-tables.md)

