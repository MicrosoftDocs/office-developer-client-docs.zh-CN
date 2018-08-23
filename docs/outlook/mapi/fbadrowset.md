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
ms.openlocfilehash: e86e9fbf4901b5944775886f38db1ba12c4b122d
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22590958"
---
# <a name="fbadrowset"></a>FBadRowSet

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
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

