---
title: FBadPropTag
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- FBadPropTag
api_type:
- HeaderDef
ms.assetid: 143bd3c6-5a55-4122-8522-9c48473aa781
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 9764be2788db8d2649be8708cad4ec67a85af845
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33433645"
---
# <a name="fbadproptag"></a>FBadPropTag

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
验证指定的属性标记。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapival.h  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |服务提供程序  <br/> |
   
```cpp
ULONG FBadPropTag(
  ULONG ulPropTag
);
```

## <a name="parameters"></a>参数

 _ulPropTag_
  
> [in]要验证的属性标记。
    
## <a name="return-value"></a>返回值

TRUE 
  
> 指定的属性标记不是有效的 MAPI 属性标记。 
    
FALSE 
  
> 指定的属性标记是有效的 MAPI 属性标记。
    
## <a name="remarks"></a>备注

**FBadPropTag** 函数根据 MAPI 定义验证指定的属性标记。 它确保属性类型是由 MAPI 定义的类型之一，并且属性标识符定义为该类型。 
  
## <a name="see-also"></a>另请参阅



[FBadProp](fbadprop.md)

