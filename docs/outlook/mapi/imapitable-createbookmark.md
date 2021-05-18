---
title: IMAPITableCreateBookmark
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPITable.CreateBookmark
api_type:
- COM
ms.assetid: 320af2ff-c2a5-43b1-b3a1-76cb5ffd6a4f
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: c251dacce0d4e1743a74f1ba45e395b6e1c05064
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33408822"
---
# <a name="imapitablecreatebookmark"></a>IMAPITable::CreateBookmark

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
在表格的当前位置创建书签。
  
```cpp
HRESULT CreateBookmark(
BOOKMARK FAR * lpbkPosition
);
```

## <a name="parameters"></a>参数

 _lpbkPosition_
  
> [out]指向返回的 32 位书签值的指针。 此书签稍后可以在对 [IMAPITable：：SeekRow](imapitable-seekrow.md) 方法的调用中传递。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功并返回了预期值。
    
MAPI_E_UNABLE_TO_COMPLETE 
  
> 无法完成请求的操作。
    
## <a name="remarks"></a>备注

**IMAPITable：：CreateBookmark** 方法通过创建一个称为书签的值来标记表位置。 书签可用于返回书签标识的位置。 书签位置与表格中该行中的对象相关联。 
  
书签在附件表中不受支持，并且 **CreateBookmark** 返回标记的附件表MAPI_E_NO_SUPPORT。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

由于维护具有书签的游标位置的内存费用，请限制您可以创建的书签数。 当您达到该号码时，请返回MAPI_E_UNABLE_TO_COMPLETE调用 **CreateBookmark** 的所有结果。
  
有时，书签指向不再位于表视图中的行。 如果调用方使用此类书签，将光标移到下一个可见行并停止。 
  
当调用者试图使用由于已折叠而指向不可访问行的书签时，在MAPI_W_POSITION_CHANGED返回该书签。 此时或在 **SetCollapseState** 方法中折叠时，可以将书签重新定位到下一个可见行。 如果在折叠行时移动书签，则必须在书签中保留一个位，以准确指示书签移动的时间：自上次使用以来或自创建以来从未使用过它。 
  
## <a name="notes-to-callers"></a>给调用方的说明

 **CreateBookmark** 为其创建的书签分配内存。 通过调用 [IMAPITable：：FreeBookmark](imapitable-freebookmark.md) 方法释放书签的资源。 
  
## <a name="see-also"></a>另请参阅



[IMAPITable::FreeBookmark](imapitable-freebookmark.md)
  
[IMAPITable::SeekRow](imapitable-seekrow.md)
  
[IMAPITable : IUnknown](imapitableiunknown.md)

