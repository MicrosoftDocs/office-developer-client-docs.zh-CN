---
title: MAPIOFFLINE_NOTIFY_TYPE
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: a111d7b7-6e87-4958-8f9b-0f2adbeb8b63
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: e7120b843eae8df70cb2c4f9cbf581dcf0e09c11
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22566885"
---
# <a name="mapiofflinenotifytype"></a>MAPIOFFLINE_NOTIFY_TYPE

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
通知的 MAPIOFFLINE_NOTIFY_TYPE 标识如果处于连接状态更改为举行、 正在进行，或已完成。 
  
## <a name="quick-info"></a>快速信息

请参阅**[IMAPIOfflineNotify](imapiofflinenotifyiunknown.md)**。 
  
```cpp
typedef enum { 
    MAPIOFFLINE_NOTIFY_TYPE_STATECHANGE_START = 1,  
    MAPIOFFLINE_NOTIFY_TYPE_STATECHANGE = 2,  
    MAPIOFFLINE_NOTIFY_TYPE_STATECHANGE_DONE = 3  
} MAPIOFFLINE_NOTIFY_TYPE;
```

## <a name="see-also"></a>另请参阅



[关于脱机状态 API](about-the-offline-state-api.md)
  
[MAPI 常量](mapi-constants.md)
  
[MAPIOFFLINE_NOTIFY](mapioffline_notify.md)

