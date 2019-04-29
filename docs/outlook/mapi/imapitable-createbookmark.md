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
  
> 排除指向返回的32位书签值的指针。 稍后可在对[IMAPITable:: SeekRow](imapitable-seekrow.md)方法的调用中传递此书签。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功, 并返回了所需的值或值。
    
MAPI_E_UNABLE_TO_COMPLETE 
  
> 无法完成请求的操作。
    
## <a name="remarks"></a>说明

**IMAPITable:: CreateBookmark**方法通过创建一个称为书签的值来标记表位置。 书签可用于返回到由书签标识的位置。 加书签的位置与表中该行的对象相关联。 
  
**CreateBookmark**返回 MAPI_E_NO_SUPPORT 的附件表和附件表实现不支持书签。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

由于使用书签维护光标位置的内存开销, 限制您可以创建的书签的数目。 当您达到该数目时, 将从对**CreateBookmark**的所有后续调用返回 MAPI_E_UNABLE_TO_COMPLETE。
  
有时, 书签指向的行在表视图中不再存在。 如果呼叫者使用此类书签, 请将光标移到下一个可见的行, 并将其停止。 
  
当呼叫者尝试使用指向 nonvisible 行的书签, 因为它已被折叠, 请在移动书签后返回 MAPI_W_POSITION_CHANGED。 此时, 可以将该书签重新定位到下一个可见的行, 也可以重新定位在**SetCollapseState**方法中发生折叠的时间。 如果在折叠行时移动书签, 则必须在书签中保留一个指示移动书签的确切时间的位: 自上次使用后, 或者如果自创建以来从未使用过该书签。 
  
## <a name="notes-to-callers"></a>给调用方的说明

 **CreateBookmark**为其创建的书签分配内存。 通过调用[IMAPITable:: FreeBookmark](imapitable-freebookmark.md)方法释放书签的资源。 
  
## <a name="see-also"></a>另请参阅



[IMAPITable::FreeBookmark](imapitable-freebookmark.md)
  
[IMAPITable::SeekRow](imapitable-seekrow.md)
  
[IMAPITable : IUnknown](imapitableiunknown.md)

