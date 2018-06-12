---
title: ISocialSessionFindPerson
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: a86cb847-5d49-44b8-b2bc-0e35e70395b4
description: 获取一个值，该值代表一个或多个人员 userID 参数匹配的字符串。
ms.openlocfilehash: 0b7525f853f7d97a991e2996a4e715cc53756d4a
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779229"
---
# <a name="isocialsessionfindperson"></a>ISocialSession::FindPerson

获取一个值，该值代表一个或多个人员_userID_参数匹配的字符串。 
  
```cpp
HRESULT _stdcall FindPerson([in] BSTR userId, [out, retval] BSTR* result);
```

## <a name="parameters"></a>参数

_userId_
  
> [in]社交网络用户 ID，SMTP 地址或某个人的显示名称。
    
_result_
  
> [输出]一个 XML 字符串值，该值代表一个或多个人员匹配_userId_参数指定的标识信息。 
    
## <a name="remarks"></a>备注

如果一个或多个人员匹配**FindPerson**请求，此方法将返回_结果_参数中的人员的信息。 Outlook Social Connector (OSC) 提供程序扩展性的架构中定义，_结果_XML 字符串必须符合**朋友**架构定义。 
  
## <a name="see-also"></a>另请参阅

- [ISocialSession: IUnknown](isocialsessioniunknown.md)

