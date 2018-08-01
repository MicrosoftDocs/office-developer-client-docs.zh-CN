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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 1c817f7ec02e79b956cdd0090ea54ea4528022ad
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775306"
---
# <a name="iexchangemodifytablegetlasterror"></a>IExchangeModifyTable::GetLastError

  
  
**适用于**： Outlook 
  
返回一个 table 对象中上次发生的错误有关的信息。
  
```cpp
HRESULT GetLastError( 
  HRESULT hResult, 
  ULONG ulFlags, 
  LPMAPIERROR FAR * lppMAPIError 
); 
```

## <a name="parameters"></a>参数

 _hResult_
  
> [in]从失败的方法返回的值。
    
 _ulFlags_
  
> [in]未使用，设置为 0 （零）。
    
 _lppMAPIError_
  
> [输出]指向 MAPI [MAPIERROR](mapierror.md)结构，其中包含有关最后一个 table 对象发生的错误的信息。 
    
## <a name="see-also"></a>另请参阅



[IExchangeModifyTable : IUnknown](iexchangemodifytableiunknown.md)
  
[MAPIERROR](mapierror.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

