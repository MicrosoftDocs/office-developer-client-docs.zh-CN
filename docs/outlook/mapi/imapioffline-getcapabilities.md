---
title: IMAPIOfflineGetCapabilities
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIOffline.GetCapabilities
api_type:
- COM
ms.assetid: aa8dc48b-9e1c-8da0-9579-10b7174e99de
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 48d59d17d81da2ae78348a57ad8b1cb75486b1a0
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33433372"
---
# <a name="imapiofflinegetcapabilities"></a>IMAPIOffline::GetCapabilities

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
获取脱机对象支持回调的条件。
  
```cpp
HRESULT GetCapabilities( 
    ULONG *pulCapabilities 
);
```

## <a name="parameters"></a>参数

 _将capablities_
  
> [out]以下功能标志的位掩码：
    
MAPIOFFLINE_CAPABILITY_OFFLINE
  
> 脱机对象能够提供脱机通知。
    
MAPIOFFLINE_CAPABILITY_ONLINE
  
> 脱机对象能够提供联机通知。
    
## <a name="remarks"></a>备注

使用 **[HrOpenOfflineObj](hropenofflineobj.md)** 打开脱机对象后，客户端可以查询 [IMAPIOfflineMgr](imapiofflinemgrimapioffline.md) 以获取 **指向 IMAPIOffline** 接口的指针，并调用 **IMAPIOffline：：GetCapabilities** 以找出对象支持的回调。 然后，客户端可以选择使用 **IMAPIOfflineMgr** 设置回调。
  
请注意，根据脱机对象的邮件服务器，支持联机的回调的对象不一定支持脱机的回调。
  
另请注意，虽然脱机对象可能支持对联机/脱机的更改的回调，但脱机状态 API 仅支持联机/脱机更改，客户端必须仅检查这些功能。
  
## <a name="see-also"></a>另请参阅



[IMAPIOffline::GetCurrentState](imapioffline-getcurrentstate.md)
  
[IMAPIOffline::SetCurrentState](imapioffline-setcurrentstate.md)
  
[IMAPIOfflineMgr : IMAPIOffline](imapiofflinemgrimapioffline.md)


[MAPI 常量](mapi-constants.md)
  
[HrOpenOfflineObj](hropenofflineobj.md)

