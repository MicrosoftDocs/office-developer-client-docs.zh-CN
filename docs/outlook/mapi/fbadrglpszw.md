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
ms.openlocfilehash: ca436bc83d5170d55475c1dd9702a9d54e4b9d5a
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33436438"
---
# <a name="fbadrglpszw"></a>FBadRglpszW

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
验证 Unicode 字符串数组中的所有字符串。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapival.h  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |服务提供程序  <br/> |
   
```cpp
BOOL FBadRglpszW(
  LPWSTR FAR * lppszW,
  ULONG cStrings
);
```

## <a name="parameters"></a>参数

 _lppszW_
  
> [in]指向以 null 结束的 Unicode 字符串数组的指针。 
    
 _cStrings_
  
> [in]  _lppszW_ 参数指向的数组中的字符串计数。 
    
## <a name="return-value"></a>返回值

TRUE 
  
> 指定数组中的一个或多个字符串无效。 
    
FALSE 
  
> 指定数组中的字符串有效。
    

