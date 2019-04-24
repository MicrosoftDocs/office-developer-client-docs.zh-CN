---
title: FBadRowSet
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.FBadRowSet
api_type:
- COM
ms.assetid: 3890dd50-e6ca-4859-bada-f6752ab61d41
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 49e6c8254cbd527635685c3f974da57ee3ac82a5
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32341018"
---
# <a name="fbadrowset"></a>FBadRowSet

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
验证包含在一组表行中的所有表行。
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapival.h  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |服务提供程序  <br/> |
   
```cpp
BOOL FBadRowSet(
  LPSRowSet lpRowSet
);
```

## <a name="parameters"></a>参数

 _lpRowSet_
  
> 实时指向标识要验证的行集的[SRowSet](srowset.md)结构的指针。 如果指针为 NULL, 则结构无效。 
    
## <a name="return-value"></a>返回值

TRUE 
  
> 指定的行集的行无效, 或行集本身无效。 
    
FALSE 
  
> 指定的行集和行集本身的行都是有效的。
    
## <a name="see-also"></a>另请参阅



[FBadRow](fbadrow.md)

