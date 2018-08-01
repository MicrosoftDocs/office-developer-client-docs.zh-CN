---
title: IMAPITableFreeBookmark
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPITable.FreeBookmark
api_type:
- COM
ms.assetid: 797833f7-8295-41bc-8980-977e5f5e05e8
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: d6621e2bcd7831016efd7ac43f93ef83aaf41c29
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775707"
---
# <a name="imapitablefreebookmark"></a>IMAPITable::FreeBookmark

  
  
**适用于**： Outlook 
  
释放与一个书签关联的内存。
  
```cpp
HRESULT FreeBookmark(
BOOKMARK bkPosition
);
```

## <a name="parameters"></a>参数

 _bkPosition_
  
> [in]通过调用[IMAPITable::CreateBookmark](imapitable-createbookmark.md)方法创建可以释放，该书签。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功释放该书签。
    
MAPI_E_INVALID_BOOKMARK 
  
> 不存在指定的书签。
    
## <a name="remarks"></a>说明

**IMAPITable::FreeBookmark**方法释放不再需要的书签。 此呼叫后，该书签不再有效。 从内存中发布一个表时，所有及其关联的书签也将被释放。 
  
## <a name="notes-to-implementers"></a>针对实施者的注释

如果呼叫者中_bkPosition_参数传递的三个预定义书签之一，忽略的请求，并返回 S_OK。 
  
## <a name="see-also"></a>另请参阅



[IMAPITable::CreateBookmark](imapitable-createbookmark.md)
  
[IMAPITable : IUnknown](imapitableiunknown.md)

