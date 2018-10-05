---
title: FBUser
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
localization_priority: Normal649b5400-8dc5-cc5c-3455-f462e2d31689
ms.assetid: ''
description: 标识用户可能也可能没有可用的忙/闲数据。
ms.openlocfilehash: 2511a94678f9ef8f2cb6be868db4f718d92ecb6d
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25387900"
---
# <a name="fbuser"></a>FBUser

标识用户可能也可能没有可用的忙/闲数据。
  
## <a name="quick-info"></a>快速信息

```cpp
typedef struct tagFBUser 
{ 
   ULONG m_cbEid; 
   LPENTRYID m_lpEid; 
   ULONG m_ulReserved; 
   LPWSTR m_pwszReserved; 
} FBUser;

```

## <a name="members"></a>Members

_m_cbEid_
  
> 邮件用户表示[IMailUser](https://docs.microsoft.com/previous-versions/windows/desktop/wab/-wab-imailuser-deleteprops)接口的条目 ID 的长度。 
    
_m_lpEid_
  
> 邮件用户表示**IMailUser**接口的条目 ID。 
    
_m_ulReserved_
  
> 此参数仅供 Outlook 内部使用，不支持。
    
_m_pwszReserved_
  
> 此参数仅供 Outlook 内部使用，不支持。
    
## <a name="see-also"></a>另请参阅

- [关于忙/闲 API](about-the-free-busy-api.md)  
- [IFreeBusySupport](ifreebusysupport.md)

