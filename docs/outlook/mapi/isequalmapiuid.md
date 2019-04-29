---
title: IsEqualMAPIUID
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.IsEqualMAPIUID
api_type:
- COM
ms.assetid: 85d71b73-0630-4c5d-b0e3-b48d27a300d0
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 44e3613338c8932bc80dd1150392033dfa3cd050
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33426931"
---
# <a name="isequalmapiuid"></a>IsEqualMAPIUID

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
测试两个[MAPIUID](mapiuid.md)结构以确定它们是否包含相同的标识符。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |mapidefs。h  <br/> |
|相关结构:  <br/> |**MAPIUID** <br/> |
   
```cpp
IsEqualMAPIUID(lpuid1, lpuid2)
```

## <a name="parameters"></a>参数

 _lpuid1_
  
> 指向要测试的第一个**MAPIUID**结构的指针。 
    
 _lpuid2_
  
> 指向要测试的第二个**MAPIUID**结构的指针。 
    
## <a name="remarks"></a>说明

如果两个**MAPIUID**结构包含相同的标识符, 则**IsEqualMAPIUID**宏返回 TRUE, 如果它们不包含, 则返回 FALSE。 
  
**IsEqualMAPIUID**宏要求包含头文件内存。 
  
## <a name="see-also"></a>另请参阅



[MAPIUID](mapiuid.md)


[与结构相关的宏](macros-related-to-structures.md)

