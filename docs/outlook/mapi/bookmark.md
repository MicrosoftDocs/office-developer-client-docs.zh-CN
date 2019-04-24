---
title: 书签
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
ms.openlocfilehash: 069cb41ceac70a2eaaa08440e43745605890f071
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32318037"
---
# <a name="bookmark"></a>书签

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
定义用于记住表中某个位置的书签数据。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |mapidefs。h  <br/> |
|相关方法:  <br/> |[IMAPITable:: CreateBookmark](imapitable-createbookmark.md)[IMAPITable:: FreeBookmark](imapitable-freebookmark.md) <br/> |
   
```cpp
typedef ULONG_PTR BOOKMARK;
```

## <a name="remarks"></a>注解

MAPI 定义了三个书签, 如下所示:
  
BOOKMARK_BEGINNING 
  
> 记住表的起始位置。 
    
BOOKMARK_CURRENT 
  
> 记住表的当前位置。
    
BOOKMARK_END 
  
> 记住表的结束位置。
    
客户端可以创建其他书签来记住其他表位置。 书签仅在表打开时有效。 客户端必须释放已创建的任何书签, 然后再关闭相关联的表。 
  
## <a name="see-also"></a>另请参阅



[IMAPITable::CreateBookmark](imapitable-createbookmark.md)
  
[IMAPITable::FindRow](imapitable-findrow.md)
  
[IMAPITable::FreeBookmark](imapitable-freebookmark.md)
  
[IMAPITable::SeekRow](imapitable-seekrow.md)


[MAPI 数据类型](mapi-data-types.md)

