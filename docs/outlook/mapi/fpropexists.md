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
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: ccfb503f62ef039700f79cd8852883685f329dfe
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774992"
---
# <a name="fpropexists"></a>FPropExists

  
  
**适用于**： Outlook 
  
从**IMAPIProp**，如[IMessage](imessageimapiprop.md)或[IMAPIFolder](imapifolderimapicontainer.md)派生给定的属性标记[IMAPIProp](imapipropiunknown.md)接口或接口中的搜索。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapiutil.h  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |客户端应用程序和服务提供商  <br/> |
   
```cpp
BOOL FPropExists(
  LPMAPIPROP pobj,
  ULONG ulPropTag
);
```

## <a name="parameters"></a>参数

 _pobj_
  
> [in]指向**IMAPIProp**接口或派生自**IMAPIProp**在其中搜索属性标记的接口的指针。 
    
 _ulPropTag_
  
> [in]要搜索的属性标记。
    
## <a name="return-value"></a>返回值

TRUE 
  
> 找到给定的属性标记匹配。 
    
FALSE 
  
> 找不到给定的属性标记匹配。
    
## <a name="remarks"></a>备注

如果_ulPropTag_参数中的属性标记具有类型 PT_UNSPECIFIED， **FPropExists**函数查找匹配仅根据属性标识符。 否则，匹配是整个属性标记，包括类型。 
  

