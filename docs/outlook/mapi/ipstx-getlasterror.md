---
title: IPSTXGetLastError
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IPSTX.GetLastError
api_type:
- COM
ms.assetid: 68dc0ecc-881e-de69-faaa-90acb9857031
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 1d0fb16ba63548a44dba3920670c0e65f8c700a1
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33414975"
---
# <a name="ipstxgetlasterror"></a>IPSTX::GetLastError

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
获取有关上一个错误的扩展信息。
  
```cpp
HRESULT GetLastError( 
    HRESULT hResult, 
    ULONG ulFlags, 
    LPMAPIERROR *lppMAPIError 
);
```

## <a name="parameters"></a>参数

 _hResult_
  
>  实时错误代码。 
    
 _ulFlags_
  
>  [] in若要修改行为的标志。 该值必须为0。 
    
 _lppMAPIError_
  
>  排除指向包含错误的扩展信息的**MAPIERROR**结构的指针。 有关**LPMAPIERROR**的类型定义, 请参阅 mapidefs.h。 
    
## <a name="see-also"></a>另请参阅



[IPSTX::EmulateSpooler](ipstx-emulatespooler.md)
  
[IPSTX::GetSyncObject](ipstx-getsyncobject.md)

