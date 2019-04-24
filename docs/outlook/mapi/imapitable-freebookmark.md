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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: a1ad209ff127a34d7da5ca8dbe1f4a6656d32876
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32328924"
---
# <a name="imapitablefreebookmark"></a>IMAPITable::FreeBookmark

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
释放与书签关联的内存。
  
```cpp
HRESULT FreeBookmark(
BOOKMARK bkPosition
);
```

## <a name="parameters"></a>参数

 _bkPosition_
  
> 实时要释放的书签, 通过调用[IMAPITable:: CreateBookmark](imapitable-createbookmark.md)方法创建。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功释放该书签。
    
MAPI_E_INVALID_BOOKMARK 
  
> 指定的书签不存在。
    
## <a name="remarks"></a>注解

**IMAPITable:: FreeBookmark**方法释放不再需要的书签。 该书签在此调用后不再有效。 每当从内存释放表时, 也会释放其所有关联的书签。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

如果调用方在_bkPosition_参数中传递了三个预定义书签之一, 则忽略该请求并返回 S_OK。 
  
## <a name="see-also"></a>另请参阅



[IMAPITable::CreateBookmark](imapitable-createbookmark.md)
  
[IMAPITable : IUnknown](imapitableiunknown.md)

