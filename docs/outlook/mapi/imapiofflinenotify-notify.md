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
  
> 实时Outlook 发送到客户端的通知。 通知指示已更改的连接状态部分、旧的连接状态和新的连接状态。
    
## <a name="remarks"></a>说明

Outlook 使用此方法向客户端发送通知回调。 若要使此接口可用于 Microsoft outlook 2010 或 microsoft outlook 2013, 客户端必须实现此接口, 并在设置使用 IMAPIOfflineMgr:: 建议的回调时, 将指针作为**[MAPIOFFLINE_ADVISEINFO](mapioffline_adviseinfo.md)** 中的成员传递给该接口**[::!](imapiofflinemgr-advise.md)**. 
  
客户端还会传递给**MAPIOFFLINE_ADVISEINFO**一个客户端令牌, outlook 2010 或 outlook 2013 在 IMAPIOfflineNotify 中使用 **:: Notify**标识为通知回调注册的客户端。 
  
通常情况下, outlook 2010 和 outlook 2013 可以通知客户端的联机/脱机更改和其他连接状态更改, 但脱机状态 API 仅支持联机/脱机更改的通知。 客户端必须忽略所有其他通知。
  
## <a name="see-also"></a>另请参阅



[关于脱机状态 API](about-the-offline-state-api.md)
  
[MAPIOFFLINE_NOTIFY](mapioffline_notify.md)

