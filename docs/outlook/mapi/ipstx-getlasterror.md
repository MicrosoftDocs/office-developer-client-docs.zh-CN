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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: f45b070464fe1b3c177088ff6aa3295f961d45f6
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22592589"
---
# <a name="ipstxgetlasterror"></a>IPSTX::GetLastError

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
获取有关扩展的信息的最后一个错误。
  
```cpp
HRESULT GetLastError( 
    HRESULT hResult, 
    ULONG ulFlags, 
    LPMAPIERROR *lppMAPIError 
);
```

## <a name="parameters"></a>参数

 _hResult_
  
>  [in]错误代码。 
    
 _ulFlags_
  
>  [] in若要修改行为的标志。 这必须是 0。 
    
 _lppMAPIError_
  
>  [输出]指向包含错误的扩展的信息**MAPIERROR**结构。 请参阅 mapidefs.h **LPMAPIERROR**的类型定义。 
    
## <a name="see-also"></a>另请参阅



[IPSTX::EmulateSpooler](ipstx-emulatespooler.md)
  
[IPSTX::GetSyncObject](ipstx-getsyncobject.md)

