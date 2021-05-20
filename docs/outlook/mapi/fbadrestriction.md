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
  
> [in] [定义要验证的限制的 SRestriction](srestriction.md) 结构。 
    
## <a name="return-value"></a>返回值

TRUE 
  
> 指定的限制（或它的一个或多个子限制）无效。 
    
FALSE 
  
> 指定的限制及其所有子范围均有效。
    
## <a name="remarks"></a>备注

验证限制后，可以传入 [对 IMAPITable：：Restrict](imapitable-restrict.md) 方法的调用，以将表限制为特定行、将表限制为查找表行的 [IMAPITable：：FindRow](imapitable-findrow.md) 方法，以及 [IMAPIContainer](imapicontainerimapiprop.md) 接口的方法，以对容器对象执行限制。 
  

