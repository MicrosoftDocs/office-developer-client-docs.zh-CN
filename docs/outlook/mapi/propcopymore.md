---
title: PropCopyMore
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PropCopyMore
api_type:
- HeaderDef
ms.assetid: 133d47cf-3592-44f3-8cdd-be402d160ee4
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 827cdb919499a068f7932d8f1f7ec264ddc5b47c
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32328551"
---
# <a name="propcopymore"></a>PropCopyMore

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
将单个属性值从源位置复制到目标位置。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiutil  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供程序  <br/> |
   
```cpp
SCODE PropCopyMore(
  LPSPropValue lpSPropValueDest,
  LPSPropValue lpSPropValueSrc,
  ALLOCATEMORE * lpfAllocMore,
  LPVOID lpvObject
);
```

## <a name="parameters"></a>参数

 _lpSPropValueDest_
  
> 排除指向此函数将定义复制的属性值的[SPropValue](spropvalue.md)结构写入到的位置的指针。 
    
 _lpSPropValueSrc_
  
> 实时指向[SPropValue](spropvalue.md)结构的指针, 该结构包含要复制的属性值。 
    
 _lpfAllocMore_
  
> 实时指向[MAPIAllocateMore](mapiallocatemore.md)函数的指针, 该函数用于在目标位置的大小不足以容纳要复制的属性时分配更多内存。 
    
 _lpvObject_
  
> 实时指向**MAPIAllocateMore**将在必要时为其分配空间的对象的指针。 
    
## <a name="return-value"></a>返回值

S_OK
  
> 已成功复制单个属性值。
    
MAPI_E_NO_SUPPORT
  
> 遇到未知的属性类型。
    
## <a name="remarks"></a>注解

客户端应用程序或服务提供程序可以使用**PropCopyMore**函数复制即将释放的表的属性, 以便在其他位置使用该属性。 
  
 **PropCopyMore**不需要分配内存, 除非复制的属性值的类型 (如 PT_STRING8) 不能包含在[SPropValue](spropvalue.md)结构中。 对于这些大型属性, 函数使用在_lpfAllocMore_参数中传递指针的[MAPIAllocateMore](mapiallocatemore.md)函数分配内存。 
  
Injudicious 使用**PropCopyMore**分段内存;请考虑改用[ScCopyProps](sccopyprops.md)函数。 
  

