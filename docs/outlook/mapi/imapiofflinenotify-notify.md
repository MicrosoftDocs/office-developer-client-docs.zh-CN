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
description: 上次修改时间：2012 年 6 月 25 日
ms.openlocfilehash: 4440df4b8e4a46e13748cf47d599e16599aaf858
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33410691"
---
# <a name="imapiofflinenotifynotify"></a>IMAPIOfflineNotify::Notify

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
向客户端发送有关连接状态更改的通知。
  
```cpp
void STDMETHODCALLTYPE Notify(  
    const MAPIOFFLINE_NOTIFY * pNotifyInfo 
);
```

## <a name="parameters"></a>参数

 _pNotifyInfo_
  
> [in]客户端Outlook发送的通知。 通知指示已更改的连接状态部分、旧连接状态和新连接状态。
    
## <a name="remarks"></a>备注

Outlook使用此方法向客户端发送通知回调。 若要使此接口对 Microsoft Outlook 2010 或 Microsoft Outlook 2013 可用，客户端必须在使用 **[IMAPIOfflineMgr：：Advise](imapiofflinemgr-advise.md)** 设置回调时，实现此接口，并作为 **[MAPIOFFLINE_ADVISEINFO](mapioffline_adviseinfo.md)** 中的成员传递指向该接口的指针。 
  
客户端还会 **向** MAPIOFFLINE_ADVISEINFO传递一个客户端令牌，Outlook 2010 或 Outlook 2013 使用 **IMAPIOfflineNotify：：Notify** 标识为通知回调注册的客户端。 
  
通常，Outlook 2010 和 Outlook 2013 可以通知客户端联机/脱机更改和其他连接状态更改，但脱机状态 API 仅支持联机/脱机更改通知。 客户端必须忽略所有其他通知。
  
## <a name="see-also"></a>另请参阅



[关于脱机状态 API](about-the-offline-state-api.md)
  
[MAPIOFFLINE_NOTIFY](mapioffline_notify.md)

