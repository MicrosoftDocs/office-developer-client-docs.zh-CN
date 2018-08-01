---
title: BOOKMARK
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.BOOKMARK
api_type:
- COM
ms.assetid: 678bdc52-3404-48b2-9154-64ce2a941555
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 8f5f3bc454e18b1dbab434fc1b7cc094b0d6a360
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774775"
---
# <a name="bookmark"></a>BOOKMARK

  
  
**适用于**： Outlook 
  
定义书签数据记住表中的位置。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapidefs.h  <br/> |
|相关的方法：  <br/> |[IMAPITable::CreateBookmark](imapitable-createbookmark.md)[IMAPITable::FreeBookmark](imapitable-freebookmark.md) <br/> |
   
```cpp
typedef ULONG_PTR BOOKMARK;
```

## <a name="remarks"></a>说明

MAPI 定义三个书签，列出，如下所示：
  
BOOKMARK_BEGINNING 
  
> 记住表的起始位置。 
    
BOOKMARK_CURRENT 
  
> 记住表的当前位置。
    
BOOKMARK_END 
  
> 记住表的结束位置。
    
客户端可以创建其他书签记忆其他表的位置。 书签是仅当打开表时才有效。 客户端必须释放他们关闭关联的表之前创建的所有书签。 
  
## <a name="see-also"></a>另请参阅



[IMAPITable::CreateBookmark](imapitable-createbookmark.md)
  
[IMAPITable::FindRow](imapitable-findrow.md)
  
[IMAPITable::FreeBookmark](imapitable-freebookmark.md)
  
[IMAPITable::SeekRow](imapitable-seekrow.md)


[MAPI 数据类型](mapi-data-types.md)

