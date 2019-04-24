---
title: ScDupPropset
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.ScDupPropset
api_type:
- COM
ms.assetid: 165ffbd0-54aa-4692-8bd1-09e6ff3762df
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 77a376bba8d65737be84e2af62e65e0419d20957
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32351266"
---
# <a name="scduppropset"></a>ScDupPropset

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
在单个 MAPI 内存块中复制属性值数组, 以组合[ScCopyProps](sccopyprops.md)和[ScCountProps](sccountprops.md)函数的操作。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiutil  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供程序  <br/> |
   
```cpp
SCODE ScDupPropset(
  int cprop,
  LPSPropValue rgprop,
  LPALLOCATEBUFFER lpAllocateBuffer,
  LPSPropValue FAR * prgprop
);
```

## <a name="parameters"></a>参数

 _cprop_
  
> 实时由_rgprop_参数指示的数组中的属性值的计数。 
    
 _rgprop_
  
> 实时指向定义要复制的属性值的[SPropValue](spropvalue.md)结构数组的指针。 
    
 _lpAllocateBuffer_
  
> 实时指向[MAPIAllocateBuffer](mapiallocatebuffer.md)函数的指针, 该函数用于为重复的数组分配内存。 
    
 _prgprop_
  
> 排除指向存储返回的**SPropValue**结构的重复数组的内存中的初始位置的指针。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功, 并返回了所需的值或值。
    

