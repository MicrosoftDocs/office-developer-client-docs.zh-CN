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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33429486"
---
# <a name="fpropexists"></a>FPropExists

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
在 [IMAPIProp](imapipropiunknown.md) 接口或派生自 **IMAPIProp** 的接口（如 [IMessage](imessageimapiprop.md) 或 [IMAPIFolder）](imapifolderimapicontainer.md)中搜索给定的属性标记。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiutil.h  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供商  <br/> |
   
```cpp
BOOL FPropExists(
  LPMAPIPROP pobj,
  ULONG ulPropTag
);
```

## <a name="parameters"></a>参数

 _pobj_
  
> [in]指向从 **IMAPIProp** 派生的 **IMAPIProp** 接口的指针，用于搜索属性标记。 
    
 _ulPropTag_
  
> [in]要搜索的属性标记。
    
## <a name="return-value"></a>返回值

TRUE 
  
> 找到给定属性标记的匹配项。 
    
FALSE 
  
> 未找到给定属性标记的匹配项。
    
## <a name="remarks"></a>备注

如果  _ulPropTag_ 参数中的属性标记的类型为 PT_UNSPECIFIED， **则 FPropExists** 函数将仅基于属性标识符查找匹配项。 否则，匹配适用于整个属性标记，包括 类型。 
  

