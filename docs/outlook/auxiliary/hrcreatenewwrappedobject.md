---
title: HrCreateNewWrappedObject
manager: soliver
ms.date: 12/07/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 780ade1c-88d0-04d2-ba7e-251c19c43438
description: 在首选的字符格式中创建客户端可以访问的对象。
ms.openlocfilehash: 3f68e0f275bcc5df065b3113d3322d6957f76df0
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25384190"
---
# <a name="hrcreatenewwrappedobject"></a>HrCreateNewWrappedObject

在首选的字符格式中创建客户端可以访问的对象。
  
## <a name="quick-info"></a>快速信息

|||
|:-----|:-----|
|导出：  <br/> |msmapi32.dll  <br/> |
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
  
> [in]初始打开的 Outlook 对象。 必须实现以下接口之一：
    
   - [IMailUser: IMAPIProp](https://msdn.microsoft.com/library/74c25870-62d9-484a-9a99-4dc35c52479e%28Office.15%29.aspx)， [IMAPIFolder: IMAPIContainer](https://msdn.microsoft.com/library/bc2e8d17-7687-43c2-8f01-b677703f7288%28Office.15%29.aspx)， [IMessage: IMAPIProp](https://msdn.microsoft.com/library/7e244d40-595e-432c-aa8c-f9f62ca3c138%28Office.15%29.aspx)， [IMsgStore: IMAPIProp](https://msdn.microsoft.com/library/20090114-b183-4767-8971-a304a9aa47e6%28Office.15%29.aspx)， [IMSLogon: IUnknown](https://msdn.microsoft.com/library/d87093dc-f705-465f-ab3c-944ca0cd3e54%28Office.15%29.aspx)，或[IOSTX](https://msdn.microsoft.com/library/f374d8d9-be8e-2489-d5fe-8a92e0ecfc6f%28Office.15%29.aspx)。
    
_ulUnwrappedFlags_
  
> [in]代表已打开的初始对象的标志。 必须是一个或多个下列值：
    
   - DDLWRAP_FLAG_ANSI — Unwrapped 对象是 ANSI。
    
   - DDLWRAP_FLAG_UNICODE — Unwrapped 对象是 UNICODE。
    
_ulWrappedFlags_
  
>  [in]首选的字符格式的标志。 必须是一个或多个下列值： 
    
   - DDLWRAP_FLAG_ANSI — 将作为 ANSI 公开 Wrapped 对象。
    
   - DDLWRAP_FLAG_UNICODE — Wrapped 对象将公开为 UNICODE。
    
_pIID_
  
>  [in]已打开的对象; 所支持的接口的标识符将其设置为 NULL 如果这是未知。 
    
_pulReserved_
  
>  [in]不使用此参数。 它必须为 NULL。 
    
_fCheckWrap_
  
>  [in]将此参数设置为**true** ，如果_pvUnwrapped_应检查有之前换行; 其格式将其设置为**false**如果对象应自动换行不检查。 
    
_ppvWrapped_
  
>  [输出]指向请求的对象，以请求的字符格式包装的指针。 
    
## <a name="return-values"></a>返回值

如果该调用成功，则返回 S_OK否则为一个错误代码。
  
## <a name="remarks"></a>注释

传入_fCheckWrap_将设置为**true**的被环绕对象将导致打开的对象。 无论返回的对象自动换行，客户端负责释放在返回的对象的引用。 
  
当使用**GetProcAddress**查找 msmapi32.dll 中此函数的地址，指定**HrCreateNewWrappedObject@28**作为过程名称。 
  
## <a name="see-also"></a>另请参阅

- [有关数据下降层 API](about-the-data-degradation-layer-api.md)
- [常量 （数据降级层 API）](constants-data-degradation-layer-api.md)

