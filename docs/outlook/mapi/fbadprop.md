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
ms.openlocfilehash: 2fbff399e088edaf3ad864f0ec7fecda3af6bc8e
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22578848"
---
# <a name="fbadprop"></a>FBadProp

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
验证指定的属性。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapival.h  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |服务提供商  <br/> |
   
```cpp
ULONG FBadProp(
  LPSPropValue lpprop
);
```

## <a name="parameters"></a>参数

 _lpprop_
  
> [in]定义要验证的属性[SPropValue](spropvalue.md)结构。 
    
## <a name="return-value"></a>返回值

TRUE 
  
> 指定的属性无效。 
    
FALSE 
  
> 指定的属性才有效。
    
## <a name="remarks"></a>注解

服务提供商可以调用**FBadProp**函数原因，例如，若要准备设置属性的[IMAPIProp::SetProps](imapiprop-setprops.md)方法调用。 **FBadProp**验证指定的属性，具体取决于属性类型。 例如，如果属性为布尔值， **FBadProp**使 sures 其值是否为 TRUE 或 FALSE。 如果该属性是二进制， **FBadProp**检查其指针和大小，并确保正确地分配。 
  
## <a name="see-also"></a>另请参阅



[FBadPropTag](fbadproptag.md)

