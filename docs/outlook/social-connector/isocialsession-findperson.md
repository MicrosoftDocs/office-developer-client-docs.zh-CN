---
title: ISocialSessionFindPerson
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: a86cb847-5d49-44b8-b2bc-0e35e70395b4
description: 获取一个字符串，代表与 userID 参数匹配的一个或多个人员。
ms.openlocfilehash: 1aa6478126e509c8d707d6a8d11b2c8428177bbd
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33434793"
---
# <a name="isocialsessionfindperson"></a>ISocialSession::FindPerson

获取一个字符串，代表与 userID 参数匹配的  _一个或多个_ 人员。 
  
```cpp
HRESULT _stdcall FindPerson([in] BSTR userId, [out, retval] BSTR* result);
```

## <a name="parameters"></a>参数

_userId_
  
> [in]社交网络用户 ID、SMTP 地址或显示名称的地址。
    
_result_
  
> [out]一个 XML 字符串，表示与 userId 参数指定的标识信息匹配的  _一个或多个_ 人员。 
    
## <a name="remarks"></a>备注

如果一个或多个人员与 **FindPerson** 请求匹配，此方法在 result 参数中返回  _这些人员_ 的信息。 结果 XML 字符串必须符合好友的架构定义，如 Outlook Social Connector (OSC 提供程序扩展) 架构中定义。 
  
## <a name="see-also"></a>另请参阅

- [ISocialSession : IUnknown](isocialsessioniunknown.md)

