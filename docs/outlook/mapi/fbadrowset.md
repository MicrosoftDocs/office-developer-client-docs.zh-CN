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
ms.openlocfilehash: e6963fc373f771289e3dbff3a0b41857352b4b9a
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774936"
---
# <a name="fbadrowset"></a>FBadRowSet

  
  
**适用于**： Outlook 
  
验证一表格行中包含的所有表格行。
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapival.h  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |服务提供商  <br/> |
   
```cpp
BOOL FBadRowSet(
  LPSRowSet lpRowSet
);
```

## <a name="parameters"></a>参数

 _lpRowSet_
  
> [in]指向[SRowSet](srowset.md)结构标识设置要验证的行的指针。 如果将指针为 NULL，则结构无效。 
    
## <a name="return-value"></a>返回值

TRUE 
  
> 指定的行集的行无效，或行集本身无效。 
    
FALSE 
  
> 指定的行集的行和行集本身均有效。
    
## <a name="see-also"></a>另请参阅



[FBadRow](fbadrow.md)

