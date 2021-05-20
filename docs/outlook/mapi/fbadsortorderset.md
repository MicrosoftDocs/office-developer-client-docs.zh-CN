---
title: FBadSortOrderSet
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.FBadSortOrderSet
api_type:
- COM
ms.assetid: b7f80e0a-8ddd-4b24-ab63-2078a8152058
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 31840923e24cddd0dc3dfa9cc67b610d0dcd7e47
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33428457"
---
# <a name="fbadsortorderset"></a>FBadSortOrderSet

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
通过验证排序顺序集的内存分配来验证其排序顺序。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapival.h  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |服务提供程序  <br/> |
   
```cpp
ULONG FBadSortOrderSet(
  LPSSortOrderSet lpsos
);
```

## <a name="parameters"></a>参数

 _lpsos_
  
> [in]指向标识要验证的排序顺序设置的 [SSortOrderSet](ssortorderset.md) 结构的指针。 
    
## <a name="return-value"></a>返回值

TRUE 
  
> 指定的排序顺序集无效。 
    
FALSE 
  
> 指定的排序顺序集有效。
    
## <a name="remarks"></a>备注

**FBadSortOrderSet** 函数可用于准备对排序方法（如 [IMAPITable：：SortTable](imapitable-sorttable.md)方法）的调用。 
  

