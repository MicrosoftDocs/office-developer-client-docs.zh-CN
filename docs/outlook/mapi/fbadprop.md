---
title: FBadProp
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- FBadProp
api_type:
- HeaderDef
ms.assetid: 929330c8-e6f2-4adf-a36e-fba18fa055d4
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: d899c8af541da231b015f6178eb7bc8f0ffd86e0
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32341039"
---
# <a name="fbadprop"></a>FBadProp

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
验证指定的属性。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapival.h  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |服务提供程序  <br/> |
   
```cpp
ULONG FBadProp(
  LPSPropValue lpprop
);
```

## <a name="parameters"></a>参数

 _lpprop_
  
> [in] 用于定义要验证的属性的 [SPropValue](spropvalue.md) 结构。 
    
## <a name="return-value"></a>返回值

TRUE 
  
> 指定的属性无效。 
    
FALSE 
  
> 指定的属性有效。
    
## <a name="remarks"></a>备注

服务提供程序可以出于多种原因调用 **FBadProp** 函数，例如，准备调用 [IMAPIProp::SetProps](imapiprop-setprops.md) 方法设置属性。 **FBadProp** 根据属性类型验证指定属性。 例如，如果属性为布尔，则 **FBadProp** 确定其值为 TRUE 或 FALSE。 如果属性为二进制，则 **FBadProp** 检查其指针和大小，并确保其得以正确分配。 
  
## <a name="see-also"></a>另请参阅



[FBadPropTag](fbadproptag.md)

