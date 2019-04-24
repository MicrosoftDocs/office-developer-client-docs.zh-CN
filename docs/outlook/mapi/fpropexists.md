---
title: FPropExists
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.FPropExists
api_type:
- COM
ms.assetid: 33c00752-cdc1-4cbe-8fca-6b06c78bd362
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7190065c687524302bae362a2e25d3848e17d1bc
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32327270"
---
# <a name="fpropexists"></a>FPropExists

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
在[IMAPIProp](imapipropiunknown.md)接口或从**IMAPIProp**派生的接口 (如[IMessage](imessageimapiprop.md)或[IMAPIFolder](imapifolderimapicontainer.md)) 中搜索给定的属性标记。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiutil  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供程序  <br/> |
   
```cpp
BOOL FPropExists(
  LPMAPIPROP pobj,
  ULONG ulPropTag
);
```

## <a name="parameters"></a>参数

 _pobj_
  
> 实时指向从**IMAPIProp**派生的**IMAPIProp**接口或接口的指针, 可在其中搜索属性标记。 
    
 _ulPropTag_
  
> 实时要搜索的属性标记。
    
## <a name="return-value"></a>返回值

TRUE 
  
> 找到给定属性标记的匹配项。 
    
FALSE 
  
> 找不到给定属性标记的匹配项。
    
## <a name="remarks"></a>注解

如果_ulPropTag_参数中的属性标记具有类型 PT_UNSPECIFIED, 则**FPropExists**函数将基于属性标识符查找匹配项。 否则, 将对整个属性标记 (包括类型) 进行匹配。 
  

