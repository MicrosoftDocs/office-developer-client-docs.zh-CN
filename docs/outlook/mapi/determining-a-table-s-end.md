---
title: 确定表的结束
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
# <a name="determining-a-tables-end"></a>确定表的结束

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
 一个常见错误是假定在出现以下错误时已到达表的末尾： 
  
- [IMAPITable：：QueryRows](imapitable-queryrows.md) 已在循环中调用，循环的结束由 [IMAPITable：：GetRowCount](imapitable-getrowcount.md)返回的行数确定。 **GetRowCount** 返回的计数并不总是表示表格中确切的行数;它是近似计数。 
    
- **QueryRows** 的行数已固定，返回的行数较少。 直到 **QueryRows** 返回行计数等于零的行集，才没有要检索的行。 
    
> [!IMPORTANT]
> 调用方只能假定游标位于表末尾的正行数或负行数的表的开头时返回值 S_OK 和零行。 绝不会MAPI_E_NOT_FOUND值。 
  
## <a name="see-also"></a>另请参阅



[MAPI 表](mapi-tables.md)

