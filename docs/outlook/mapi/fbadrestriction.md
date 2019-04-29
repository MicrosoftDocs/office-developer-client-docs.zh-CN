---
title: FBadRestriction
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- FBadRestriction
api_type:
- HeaderDef
ms.assetid: 6ad3638c-d088-4a89-9b0d-f5b672162203
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: eb3e0d5a96121f63166da2025743b7ef89f4ecf6
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33432238"
---
# <a name="fbadrestriction"></a>FBadRestriction

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
验证用于限制表视图的限制。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapival.h  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |服务提供程序  <br/> |
   
```cpp
ULONG FBadRestriction(
  LPSRestriction lpres
);
```

## <a name="parameters"></a>参数

 _lpres_
  
> 实时定义要验证的限制的[SRestriction](srestriction.md)结构。 
    
## <a name="return-value"></a>返回值

TRUE 
  
> 指定的限制, 或其 subrestrictions 的一个或多个无效。 
    
FALSE 
  
> 指定的限制及其所有 subrestrictions 都是有效的。
    
## <a name="remarks"></a>说明

在验证限制后, 可以将其传递给[imapitable:: Restrict](imapitable-restrict.md)方法, 以将表限制到某些行、用于查找表行的[imapitable:: FindRow](imapitable-findrow.md)方法, 以及[IMAPIContainer](imapicontainerimapiprop.md)的方法。用于对容器对象执行限制的接口。 
  

