---
title: IMAPIGetSessionGetMAPISession
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIGetSession.GetMAPISession
api_type:
- COM
ms.assetid: 581db5d9-35f7-43ad-aef3-a5d5da310150
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 7176f3547c18ec72e4bfc0a749b3814d1e906b7b
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22577035"
---
# <a name="imapigetsessiongetmapisession"></a>IMAPIGetSession::GetMAPISession

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
返回到与 MAPI 支持对象关联的 MAPI 会话的指针。
  
```cpp
HRESULT GetMAPISession(
  LPUNKNOWN *  lppSession
);
```

## <a name="parameters"></a>参数

 _lppSession_
  
> [输出]一个指向当前的 MAPI 会话。
    
## <a name="see-also"></a>另请参阅



[IMAPIGetSession : IUnknown](imapigetsessioniunknown.md)


[支持对象概述](support-object-overview.md)

