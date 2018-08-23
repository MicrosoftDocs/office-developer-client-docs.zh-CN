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
ms.openlocfilehash: 23b4ed78f4b65a5af4c2f3e11fa770030fe4eeee
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22590160"
---
# <a name="fbadrow"></a>FBadRow

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
验证表中的行。
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapival.h  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |服务提供商  <br/> |
   
```cpp
ULONG FBadRow(
  LPSRow lprow
);
```

## <a name="parameters"></a>参数

 _lprow_
  
> [in]标识要验证的行[SRow](srow.md)结构的指针。 
    
## <a name="return-value"></a>返回值

TRUE 
  
> 指定的行无效。
    
FALSE 
  
> 指定的行是有效的。
    
## <a name="see-also"></a>另请参阅



[FBadRowSet](fbadrowset.md)

