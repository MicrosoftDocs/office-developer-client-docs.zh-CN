---
title: FBadRglpszW
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.FBadRglpszW
api_type:
- COM
ms.assetid: 880eb35d-7045-4fdd-bb33-0f14557a7316
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: da31da0ae0437e1578a681d9232b0693932b2aec
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774905"
---
# <a name="fbadrglpszw"></a>FBadRglpszW

  
  
**适用于**： Outlook 
  
验证的 Unicode 字符串数组中的所有字符串。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapival.h  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |服务提供商  <br/> |
   
```cpp
BOOL FBadRglpszW(
  LPWSTR FAR * lppszW,
  ULONG cStrings
);
```

## <a name="parameters"></a>参数

 _lppszW_
  
> [in]指向 null 结尾的 Unicode 字符串数组。 
    
 _Cstring_
  
> [in]由_lppszW_参数指向的字符串数组中的计数。 
    
## <a name="return-value"></a>返回值

TRUE 
  
> 一个或多个指定的数组中的字符串是无效。 
    
FALSE 
  
> 指定数组中的字符串是有效的。
    

