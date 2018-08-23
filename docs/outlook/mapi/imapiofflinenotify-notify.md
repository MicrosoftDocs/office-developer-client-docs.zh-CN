---
title: IMAPIOfflineNotifyNotify
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIOfflineNotify.Notify
api_type:
- COM
ms.assetid: 10c7cb9d-2e9d-72eb-6b07-31eed892e646
description: 上次修改时间： 2012 年 6 月 25 日
ms.openlocfilehash: a84114a3363f9cbcd9455bce12d3171843bd18a4
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22571113"
---
# <a name="imapiofflinenotifynotify"></a>IMAPIOfflineNotify::Notify

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
将通知发送到客户端有关连接状态的变化。
  
```cpp
void STDMETHODCALLTYPE Notify(  
    const MAPIOFFLINE_NOTIFY * pNotifyInfo 
);
```

## <a name="parameters"></a>参数

 _pNotifyInfo_
  
> [in]在 Outlook 发送到客户端的通知。 通知指示已更改的连接状态、 旧的连接状态和新的连接状态的一部分。
    
## <a name="remarks"></a>注解

Outlook 使用此方法向客户发送通知回调。 若要使此接口可供 Microsoft Outlook 2010 或 Microsoft Outlook 2013，客户端必须实现此接口并将指针传递给它为**[MAPIOFFLINE_ADVISEINFO](mapioffline_adviseinfo.md)** 中的成员设置使用**[IMAPIOfflineMgr::Advise 回调时](imapiofflinemgr-advise.md)**. 
  
客户端也将传递给**MAPIOFFLINE_ADVISEINFO**客户端令牌的 Outlook 2010 或 Outlook 2013 使用**IMAPIOfflineNotify::Notify**中标识为通知回调注册的客户端。 
  
一般情况下，Outlook 2010 和 Outlook 2013 可以通知的联机/脱机更改客户端和其他连接的状态更改，但脱机状态 API 支持仅通知联机/脱机的更改。 客户端必须忽略所有其他通知。
  
## <a name="see-also"></a>另请参阅



[关于脱机状态 API](about-the-offline-state-api.md)
  
[MAPIOFFLINE_NOTIFY](mapioffline_notify.md)

