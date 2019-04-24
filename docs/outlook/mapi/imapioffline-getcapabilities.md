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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32321313"
---
# <a name="imapiofflinegetcapabilities"></a>IMAPIOffline::GetCapabilities

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
获取脱机对象支持的回调的条件。
  
```cpp
HRESULT GetCapabilities( 
    ULONG *pulCapabilities 
);
```

## <a name="parameters"></a>参数

 _pulCapablities_
  
> 排除以下功能标志的位掩码:
    
MAPIOFFLINE_CAPABILITY_OFFLINE
  
> 脱机对象能够提供脱机通知。
    
MAPIOFFLINE_CAPABILITY_ONLINE
  
> 脱机对象能够提供联机通知。
    
## <a name="remarks"></a>注解

在使用**[HrOpenOfflineObj](hropenofflineobj.md)** 打开脱机对象时, 客户端可以查询[IMAPIOfflineMgr](imapiofflinemgrimapioffline.md)以获取指向**IMAPIOffline**接口的指针, 并调用**IMAPIOffline:: GetCapabilities**以查找支持的回调对象。 然后, 客户端可以选择使用**IMAPIOfflineMgr**设置回调。
  
请注意, 根据脱机对象的邮件服务器, 支持联机的回调的对象不一定支持要脱机的回调。
  
另请注意, 尽管脱机对象可能支持非联机/脱机更改的回调, 但脱机状态 API 仅支持联机/脱机更改, 并且客户端必须仅检查此类功能。
  
## <a name="see-also"></a>另请参阅



[IMAPIOffline::GetCurrentState](imapioffline-getcurrentstate.md)
  
[IMAPIOffline::SetCurrentState](imapioffline-setcurrentstate.md)
  
[IMAPIOfflineMgr : IMAPIOffline](imapiofflinemgrimapioffline.md)


[MAPI 常量](mapi-constants.md)
  
[HrOpenOfflineObj](hropenofflineobj.md)

