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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 699e77479e0d09e7549c0d2741d5ba54ecc8ce33
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22572030"
---
# <a name="imapiofflinegetcapabilities"></a>IMAPIOffline::GetCapabilities

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
获取为其脱机对象支持回调的条件。
  
```cpp
HRESULT GetCapabilities( 
    ULONG *pulCapabilities 
);
```

## <a name="parameters"></a>参数

 _pulCapablities_
  
> [输出]以下功能标志位掩码：
    
MAPIOFFLINE_CAPABILITY_OFFLINE
  
> 脱机对象是能够提供脱机通知。
    
MAPIOFFLINE_CAPABILITY_ONLINE
  
> 脱机对象是能够提供联机通知。
    
## <a name="remarks"></a>注解

在打开时使用**[HrOpenOfflineObj](hropenofflineobj.md)** 脱机对象，客户端可以查询[IMAPIOfflineMgr](imapiofflinemgrimapioffline.md)获取指向**IMAPIOffline**接口，并调用**IMAPIOffline::GetCapabilities**以找出回调支持由对象。 客户端然后可以选择使用**IMAPIOfflineMgr**设置回调。
  
请注意，具体取决于脱机对象的邮件服务器，用于联机支持回调的对象不一定支持回调的脱机。
  
此外，并脱机对象可能更改之外联机/脱机支持回调，脱机状态 API 支持仅联机/脱机更改，这样的功能必须检查客户端。
  
## <a name="see-also"></a>另请参阅



[IMAPIOffline::GetCurrentState](imapioffline-getcurrentstate.md)
  
[IMAPIOffline::SetCurrentState](imapioffline-setcurrentstate.md)
  
[IMAPIOfflineMgr : IMAPIOffline](imapiofflinemgrimapioffline.md)


[MAPI 常量](mapi-constants.md)
  
[HrOpenOfflineObj](hropenofflineobj.md)

