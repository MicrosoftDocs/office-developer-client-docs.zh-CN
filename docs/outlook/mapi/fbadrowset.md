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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33411790"
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
  
> [in]指向标识要验证的行集的 [SRowSet](srowset.md) 结构的指针。 如果指针为 NULL，则结构无效。 
    
## <a name="return-value"></a>返回值

TRUE 
  
> 指定行集的行无效，或者行集本身无效。 
    
FALSE 
  
> 指定行集的行和行集本身均有效。
    
## <a name="see-also"></a>另请参阅



[FBadRow](fbadrow.md)

