---
title: IPersistMessageGetClassID
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IPersistMessage.GetClassID
api_type:
- COM
ms.assetid: 77eeb468-3432-4ccd-9c1e-1df9ce605193
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: c9d769e6a32fad22750a965debbbdce83e4de539
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22586453"
---
# <a name="ipersistmessagegetclassid"></a>IPersistMessage::GetClassID

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
返回表示可以管理窗体的窗体服务器的标识符。 
  
```cpp
HRESULT GetClassID(
  LPCLSID lpClassID
);
```

## <a name="parameters"></a>参数

 _lpClassID_
  
> [传入、 传出]指向该窗体的类标识符 (CLSID) 的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功返回的类标识符。
    
## <a name="remarks"></a>注解

**IPersistMessge::GetClassID**方法设置为窗体服务器的类标识符的_lpClassID_参数的内容，并返回 S_OK。 当窗体查看器调用**GetClassID**和它成功返回时，窗体处于[未初始化](uninitialized-state.md)状态。 
  
有关如何使用结构化的存储对象使用的类标识符的详细信息，请参阅[IPersist::GetClassID](http://msdn.microsoft.com/library/921a3b86-a240-454e-9411-8d653e02b90e.aspx)方法的文档。 
  
## <a name="see-also"></a>另请参阅



[IPersistMessage : IUnknown](ipersistmessageiunknown.md)

