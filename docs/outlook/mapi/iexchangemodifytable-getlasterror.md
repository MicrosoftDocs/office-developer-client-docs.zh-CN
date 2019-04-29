---
title: IExchangeModifyTableGetLastError
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IExchangeModifyTable.GetLastError
api_type:
- COM
ms.assetid: b850dc08-73c3-4b19-ae29-1892d6a2ff2f
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 8d5d4895e4440945896ee4f2212c5fca6da8610d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33424509"
---
# <a name="iexchangemodifytablegetlasterror"></a>IExchangeModifyTable::GetLastError

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
返回有关在 table 对象中发生的最后一个错误的信息。
  
```cpp
HRESULT GetLastError( 
  HRESULT hResult, 
  ULONG ulFlags, 
  LPMAPIERROR FAR * lppMAPIError 
); 
```

## <a name="parameters"></a>参数

 _hResult_
  
> 实时失败方法的返回值。
    
 _ulFlags_
  
> 实时未使用, 设置为 0 (零)。
    
 _lppMAPIError_
  
> 排除指向包含有关 table 对象的最后一个错误的信息的 MAPI [MAPIERROR](mapierror.md)结构。 
    
## <a name="see-also"></a>另请参阅



[IExchangeModifyTable : IUnknown](iexchangemodifytableiunknown.md)
  
[MAPIERROR](mapierror.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

