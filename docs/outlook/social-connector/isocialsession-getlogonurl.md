---
title: ISocialSessionGetLogonUrl
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: d61bab07-acb3-433b-8783-c3fe110a5582
description: 获取一个字符串，代表在 Web 身份验证期间用于向用户显示基于浏览器的表单的 URL。
ms.openlocfilehash: 83867282922ea136b9673609cc2ba2f1a206f6ab
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33427911"
---
# <a name="isocialsessiongetlogonurl"></a>ISocialSession::GetLogonUrl

获取一个字符串，代表在 Web 身份验证期间用于向用户显示基于浏览器的表单的 URL。
  
```cpp
HRESULT _stdcall GetLogonUrl([out, retval] BSTR* url);
```

## <a name="parameters"></a>参数

_url_
  
> [out]一个字符串，包含用于 Web 身份验证的表单的 URL。
    
## <a name="remarks"></a>备注

向用户显示表单后，使用 _connectIn_ 参数的空字符串调用 [ISocialSession：：LogonWeb](isocialsession-logonweb.md)方法。 
  
## <a name="see-also"></a>另请参阅

- [ISocialSession : IUnknown](isocialsessioniunknown.md)

