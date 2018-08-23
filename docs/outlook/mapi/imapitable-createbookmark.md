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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 5e9135a52c15c18b70116aaf52e1ee63af413673
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22563847"
---
# <a name="imapitablecreatebookmark"></a>IMAPITable::CreateBookmark

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
在表的当前位置创建一个书签。
  
```cpp
HRESULT CreateBookmark(
BOOKMARK FAR * lpbkPosition
);
```

## <a name="parameters"></a>参数

 _lpbkPosition_
  
> [输出]返回的 32 位书签值的指针。 更高版本可以对[IMAPITable::SeekRow](imapitable-seekrow.md)方法的调用中传递该书签。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 呼叫成功或多个预期值返回。
    
MAPI_E_UNABLE_TO_COMPLETE 
  
> 无法完成所请求的操作。
    
## <a name="remarks"></a>注解

**IMAPITable::CreateBookmark**方法通过创建值调用书签标记的表的位置。 可以使用书签以返回到书签标识的位置。 与在表中的行对象相关联的书签的位置。 
  
附件表上不支持书签和附件的**CreateBookmark**的表实现返回 MAPI_E_NO_SUPPORT。 
  
## <a name="notes-to-implementers"></a>针对实施者的注释

由于内存费用的维护光标位置的书签，限制可以创建的书签的数目。 如果看到该号码，返回从所有后续呼叫到**CreateBookmark**MAPI_E_UNABLE_TO_COMPLETE。
  
有时书签指向不再在表视图中的行。 如果呼叫者使用如书签，将光标移到下一个可见的行和存在停止。 
  
当呼叫者尝试使用书签，因为它已被折叠指向不可见的行时，则移动书签后返回 MAPI_W_POSITION_CHANGED。 此时或折叠发生在**SetCollapseState**方法时，可以重新定位到的下一个可见行的书签。 如果将书签移动折叠行时，您必须保留有点指示完全书签已移动时在书签： 由于其上次使用或其从未使用过创建后。 
  
## <a name="notes-to-callers"></a>给调用方的说明

 **CreateBookmark**为其创建的书签分配内存。 通过调用[IMAPITable::FreeBookmark](imapitable-freebookmark.md)方法释放书签的资源。 
  
## <a name="see-also"></a>另请参阅



[IMAPITable::FreeBookmark](imapitable-freebookmark.md)
  
[IMAPITable::SeekRow](imapitable-seekrow.md)
  
[IMAPITable : IUnknown](imapitableiunknown.md)

