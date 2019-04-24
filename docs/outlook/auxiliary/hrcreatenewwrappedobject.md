---
title: HrCreateNewWrappedObject
manager: soliver
ms.date: 12/07/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 780ade1c-88d0-04d2-ba7e-251c19c43438
description: 创建一个客户端可以以首选字符格式访问的对象。
ms.openlocfilehash: 3f68e0f275bcc5df065b3113d3322d6957f76df0
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32317603"
---
# <a name="hrcreatenewwrappedobject"></a>HrCreateNewWrappedObject

创建一个客户端可以以首选字符格式访问的对象。
  
## <a name="quick-info"></a>快速信息

|||
|:-----|:-----|
|导出者:  <br/> |msmapi32  <br/> |
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
  
> 实时初始的已解包的 Outlook 对象。 必须实现以下接口之一:
    
   - [IMailUser: IMAPIProp](https://msdn.microsoft.com/library/74c25870-62d9-484a-9a99-4dc35c52479e%28Office.15%29.aspx), [IMAPIFolder: IMAPIContainer](https://msdn.microsoft.com/library/bc2e8d17-7687-43c2-8f01-b677703f7288%28Office.15%29.aspx), [IMessage: IMAPIProp](https://msdn.microsoft.com/library/7e244d40-595e-432c-aa8c-f9f62ca3c138%28Office.15%29.aspx), [IMsgStore: IMAPIProp](https://msdn.microsoft.com/library/20090114-b183-4767-8971-a304a9aa47e6%28Office.15%29.aspx), [IMSLogon: IUnknown](https://msdn.microsoft.com/library/d87093dc-f705-465f-ab3c-944ca0cd3e54%28Office.15%29.aspx), 或[IOSTX](https://msdn.microsoft.com/library/f374d8d9-be8e-2489-d5fe-8a92e0ecfc6f%28Office.15%29.aspx)。
    
_ulUnwrappedFlags_
  
> 实时用于表征已解开初始对象的标志。 必须是下列值中的一个或多个:
    
   - DDLWRAP_FLAG_ANSI —解包的对象是 ANSI。
    
   - DDLWRAP_FLAG_UNICODE —解包的对象是 UNICODE。
    
_ulWrappedFlags_
  
>  实时首选字符格式的标志。 必须是下列值中的一个或多个: 
    
   - DDLWRAP_FLAG_ANSI —包装的对象将作为 ANSI 公开。
    
   - DDLWRAP_FLAG_UNICODE —包装的对象将作为 UNICODE 公开。
    
_pIID_
  
>  实时已被解开的对象支持的接口的标识符;如果这是未知的, 则将其设置为 NULL。 
    
_pulReserved_
  
>  实时不使用此参数。 它必须为 NULL。 
    
_fCheckWrap_
  
>  实时如果在换行之前应检查_pvUnwrapped_的格式, 则将此参数设置为**true** ;如果不进行检查, 则将该对象设置为**false** 。 
    
_ppvWrapped_
  
>  排除指向请求的对象的指针, 以请求的字符格式封装。 
    
## <a name="return-values"></a>返回值

如果该调用成功，则返回 S_OK否则为一个错误代码。
  
## <a name="remarks"></a>注解

如果将_fCheckWrap_设置为**true** , 则传递给已包装的对象将生成一个已解包的对象。 无论返回的对象是否被包装, 客户端都要负责释放对返回的对象的引用。 
  
使用**GetProcAddress**在 msmapi32 中查找此函数的地址时, 请指定**HrCreateNewWrappedObject @ 28**作为过程名称。 
  
## <a name="see-also"></a>另请参阅

- [有关数据下降层 API](about-the-data-degradation-layer-api.md)
- [常量 (数据降级层 API)](constants-data-degradation-layer-api.md)

