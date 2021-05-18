---
title: HrCreateNewWrappedObject
manager: soliver
ms.date: 12/07/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 780ade1c-88d0-04d2-ba7e-251c19c43438
description: 创建客户端可以使用首选字符格式访问的对象。
ms.openlocfilehash: 3f68e0f275bcc5df065b3113d3322d6957f76df0
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32317603"
---
# <a name="hrcreatenewwrappedobject"></a>HrCreateNewWrappedObject

创建客户端可以使用首选字符格式访问的对象。
  
## <a name="quick-info"></a>快速信息

|||
|:-----|:-----|
|导出者：  <br/> |msmapi32.dll  <br/> |
|调用者：  <br/> |客户端  <br/> |
|实现者：  <br/> |Outlook  <br/> |
   
```cpp
HRESULT HrCreateNewWrappedObject( 
    LPVOID        pvUnwrapped, 
    ULONG         ulUnwrappedFlags, 
    ULONG         ulWrappedFlags, 
    const IID     *pIID, 
    const ULONG   *pulReserved, 
    BOOL          fCheckWrap, 
    LPVOID       *ppvWrapped 
);

```

## <a name="parameters"></a>参数

_pvUnwrapped_
  
> [in]初始未包Outlook对象。 必须实现以下接口之一：
    
   - [IMailUser ： IMAPIProp](https://msdn.microsoft.com/library/74c25870-62d9-484a-9a99-4dc35c52479e%28Office.15%29.aspx)， [IMAPIFolder ： IMAPIContainer](https://msdn.microsoft.com/library/bc2e8d17-7687-43c2-8f01-b677703f7288%28Office.15%29.aspx)， [IMessage ： IMAPIProp](https://msdn.microsoft.com/library/7e244d40-595e-432c-aa8c-f9f62ca3c138%28Office.15%29.aspx)， [IMsgStore ： IMAPIProp](https://msdn.microsoft.com/library/20090114-b183-4767-8971-a304a9aa47e6%28Office.15%29.aspx)， [IMSLogon ： IUnknown](https://msdn.microsoft.com/library/d87093dc-f705-465f-ab3c-944ca0cd3e54%28Office.15%29.aspx)， or [IOSTX](https://msdn.microsoft.com/library/f374d8d9-be8e-2489-d5fe-8a92e0ecfc6f%28Office.15%29.aspx).
    
_ulUnwrappedFlags_
  
> [in]表示未包装的初始对象特征的标志。 必须为以下一个或多个值：
    
   - DDLWRAP_FLAG_ANSI —Unwrapped 对象是 ANSI。
    
   - DDLWRAP_FLAG_UNICODE —Unwrapped 对象是 UNICODE。
    
_ulWrappedFlags_
  
>  [in]首选字符格式的标志。 必须为以下一个或多个值： 
    
   - DDLWRAP_FLAG_ANSI封装对象将公开为 ANSI。
    
   - DDLWRAP_FLAG_UNICODE封装对象将公开为 UNICODE。
    
_pIID_
  
>  [in]未包对象支持的接口的标识符;如果未知，则设置为 NULL。 
    
_将保留_
  
>  [in]此参数未使用。 它必须为 NULL。 
    
_fCheckWrap_
  
>  [in]如果应在换行前检查 _pvUnwrapped_ 的格式，则此参数设置为 **true;** 如果应在不检查的情况下封装对象，则设置为 **false。** 
    
_ppvWrapped_
  
>  [out]一个指向所请求对象的指针，包装在请求的字符格式中。 
    
## <a name="return-values"></a>返回值

如果该调用成功，则返回 S_OK否则为一个错误代码。
  
## <a name="remarks"></a>备注

在  _fCheckWrap_ 设置为 **true** 的封装对象中传递将导致未封装的对象。 无论返回的对象是否被封装，客户端都负责释放对返回对象的引用。 
  
使用 **GetProcAddress** 在 msmapi32.dll 中查找此函数的地址时，HrCreateNewWrappedObject@28指定为 **过程** 名称。 
  
## <a name="see-also"></a>另请参阅

- [有关数据下降层 API](about-the-data-degradation-layer-api.md)
- [数据 (层 API) ](constants-data-degradation-layer-api.md)

