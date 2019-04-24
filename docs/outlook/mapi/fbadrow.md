---
title: FBadRow
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.FBadRow
api_type:
- COM
ms.assetid: 205d00df-488d-4888-8782-a1f70f54d720
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 153bcbfd87ea9e85d834cba2fd9028e98fa25750
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32340955"
---
# <a name="fbadrow"></a>FBadRow

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
验证表中的行。
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapival.h  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |服务提供程序  <br/> |
   
```cpp
ULONG FBadRow(
  LPSRow lprow
);
```

## <a name="parameters"></a>参数

 _lprow_
  
> 实时指向标识要验证的行的[SRow](srow.md)结构的指针。 
    
## <a name="return-value"></a>返回值

TRUE 
  
> 指定的行无效。
    
FALSE 
  
> 指定的行有效。
    
## <a name="see-also"></a>另请参阅



[FBadRowSet](fbadrowset.md)

