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
ms.openlocfilehash: 5b93f84026cacd8568dc5ceec5574d144f6d1633
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778705"
---
# <a name="scduppropset"></a>ScDupPropset

  
  
**适用于**： Outlook 
  
复制一个独立的 MAPI 内存组合的[ScCopyProps](sccopyprops.md)和[ScCountProps](sccountprops.md)函数的操作块中的属性值数组。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapiutil.h  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |客户端应用程序和服务提供商  <br/> |
   
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
  
> [in]由_rgprop_参数指示在阵列中的属性值的计数。 
    
 _rgprop_
  
> [in]指向[SPropValue](spropvalue.md)结构定义要重复的属性值的数组。 
    
 _lpAllocateBuffer_
  
> [in]指向[MAPIAllocateBuffer](mapiallocatebuffer.md)函数，以用于重复数组分配内存。 
    
 _prgprop_
  
> [输出]为在内存中存储的**SPropValue**结构重复返回的数组的初始位置的指针。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 呼叫成功或多个预期值返回。
    

