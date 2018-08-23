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
ms.openlocfilehash: 3d729e2a12ee19ee3aa4ded71263697eb739f154
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22566304"
---
# <a name="fbadrestriction"></a>FBadRestriction

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
验证用于限制表视图的限制。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapival.h  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |服务提供商  <br/> |
   
```cpp
ULONG FBadRestriction(
  LPSRestriction lpres
);
```

## <a name="parameters"></a>参数

 _lpres_
  
> [in]定义要验证的限制[SRestriction](srestriction.md)结构。 
    
## <a name="return-value"></a>返回值

TRUE 
  
> 指定的限制，或一个或多个其 subrestrictions，无效。 
    
FALSE 
  
> 指定的限制和所有 subrestrictions 有效。
    
## <a name="remarks"></a>注解

一旦限制进行验证后，可以传递给[IMAPITable::Restrict](imapitable-restrict.md)方法的呼叫来为特定行、 [IMAPITable::FindRow](imapitable-findrow.md)方法查找表行和[IMAPIContainer](imapicontainerimapiprop.md)的方法限制表中对 container 对象执行限制的接口。 
  

