---
title: FBUser
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
localization_priority: Normal649b5400-8dc5-cc5c-3455-f462e2d31689
ms.assetid: ''
description: 标识可能或可能没有可用的忙/闲数据的用户。
ms.openlocfilehash: 2511a94678f9ef8f2cb6be868db4f718d92ecb6d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32317659"
---
# <a name="fbuser"></a>FBUser

标识可能或可能没有可用的忙/闲数据的用户。
  
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

## <a name="members"></a>成员

_m_cbEid_
  
> 由 [IMailUser](https://docs.microsoft.com/previous-versions/windows/desktop/wab/-wab-imailuser-deleteprops) 接口表示的邮件用户的条目 ID 的长度。 
    
_m_lpEid_
  
> 由 **IMailUser** 接口表示的邮件用户的条目 ID。 
    
_m_ulReserved_
  
> 此参数仅供Outlook内部使用，不受支持。
    
_m_pwszReserved_
  
> 此参数仅供Outlook内部使用，不受支持。
    
## <a name="see-also"></a>另请参阅

- [关于忙/闲 API](about-the-free-busy-api.md)  
- [IFreeBusySupport](ifreebusysupport.md)

