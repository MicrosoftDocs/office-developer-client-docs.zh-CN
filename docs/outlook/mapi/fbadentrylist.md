---
title: FBadEntryList
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- FBadEntryList
api_type:
- HeaderDef
ms.assetid: 270c47c3-ae68-4995-b304-27f861b350d6
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 21ed5a23b96dabdd594547109ecb1e6c048a4844
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33427771"
---
# <a name="fbadentrylist"></a>FBadEntryList

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
验证 MAPI 项标识符的列表。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapival.h  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |服务提供程序  <br/> |
   
```cpp
BOOL FBadEntryList(
  LPENTRYLIST lpEntryList
);
```

## <a name="parameters"></a>参数

 _lpEntryList_
  
> 实时指向包含要验证的条目标识符数组的[ENTRYLIST](entrylist.md)结构的指针。 
    
## <a name="return-value"></a>返回值

TRUE 
  
> 一个或多个列出的条目标识符无效。 
    
FALSE 
  
> 所有列出的条目标识符都是有效的。
    
## <a name="remarks"></a>说明

**FBadEntryList**函数确定条目标识符列表是否已正确生成。 无效标识符的一个示例是内存分配不正确或标识符大小不正确的情况。 
  

