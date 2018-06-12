---
title: FBUser
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
localization_priority: Normal649b5400-8dc5-cc5c-3455-f462e2d31689
ms.assetid: ''
description: 标识用户可能也可能没有可用的忙/闲数据。
ms.openlocfilehash: e83689e28f5fb6e1eae28d760bb57f5ad3796f8e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774176"
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

## <a name="members"></a>成员

_m_cbEid_
  
> 邮件用户表示[IMailUser](http://msdn.microsoft.com/library/wab._wab_IMailUser%28Office.15%29.aspx)接口的条目 ID 的长度。 
    
_m_lpEid_
  
> 邮件用户表示**IMailUser**接口的条目 ID。 
    
_m_ulReserved_
  
> 此参数仅供 Outlook 内部使用，不支持。
    
_m_pwszReserved_
  
> 此参数仅供 Outlook 内部使用，不支持。
    
## <a name="see-also"></a>另请参阅

- [有关的忙/闲的 API](about-the-free-busy-api.md)  
- [IFreeBusySupport](ifreebusysupport.md)

