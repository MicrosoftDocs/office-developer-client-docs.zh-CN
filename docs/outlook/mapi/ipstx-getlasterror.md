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
ms.openlocfilehash: e061808c57f25f881cc17fa5251e46ed5d524acd
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776068"
---
# <a name="ipstxgetlasterror"></a>IPSTX::GetLastError

  
  
**适用于**： Outlook 
  
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

