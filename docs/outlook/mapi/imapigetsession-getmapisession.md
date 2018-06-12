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
ms.openlocfilehash: 8090d9b1a1f7fb571532cf32d7a2412261aee1fc
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775442"
---
# <a name="imapigetsessiongetmapisession"></a>IMAPIGetSession::GetMAPISession

  
  
**适用于**： Outlook 
  
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



[IMAPIGetSession: IUnknown](imapigetsessioniunknown.md)


[支持对象概述](support-object-overview.md)

