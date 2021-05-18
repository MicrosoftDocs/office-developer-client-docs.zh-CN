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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33406015"
---
# <a name="scduppropset"></a>ScDupPropset

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
将 [ScCopyProps](sccopyprops.md) 和 [ScCountProps](sccountprops.md) 函数的操作合并在一个 MAPI 内存块中复制属性值数组。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiutil.h  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供商  <br/> |
   
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
  
> [in]  _rgprop_ 参数指示的数组中的属性值计数。 
    
 _rgprop_
  
> [in]指向定义要复制的属性值 [的 SPropValue](spropvalue.md) 结构的数组的指针。 
    
 _lpAllocateBuffer_
  
> [in]指向 [MAPIAllocateBuffer](mapiallocatebuffer.md) 函数的指针，用于为重复的数组分配内存。 
    
 _prgprop_
  
> [out]指向内存中存储返回的 **SPropValue** 结构的重复数组的初始位置的指针。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功并返回了预期值。
    

