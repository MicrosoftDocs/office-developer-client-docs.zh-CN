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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 3b3b6b5ca0b06fc55a60e035ffd9118391cab8f9
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22565912"
---
# <a name="fbadrglpszw"></a>FBadRglpszW

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
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
    

