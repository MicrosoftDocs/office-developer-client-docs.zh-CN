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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33404468"
---
# <a name="propcopymore"></a>PropCopyMore

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
将单个属性值从源位置复制到目标位置。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiutil.h  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供商  <br/> |
   
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
  
> [out]指向此函数写入定义复制属性值 [的 SPropValue](spropvalue.md) 结构的位置的指针。 
    
 _lpSPropValueSrc_
  
> [in]指向包含要复制的属性值的 [SPropValue](spropvalue.md) 结构的指针。 
    
 _lpfAllocMore_
  
> [in]指向 [MAPIAllocateMore](mapiallocatemore.md) 函数的指针，当目标位置不足以容纳要复制的属性时，用于分配额外的内存。 
    
 _lpvObject_
  
> [in]指向 **MAPIAllocateMore** 将在必要时为其分配空间的对象的指针。 
    
## <a name="return-value"></a>返回值

S_OK
  
> 已成功复制单个属性值。
    
MAPI_E_NO_SUPPORT
  
> 遇到未知属性类型。
    
## <a name="remarks"></a>备注

客户端应用程序或服务提供商可以使用 **PropCopyMore** 函数从即将释放的表中复制属性，以便将其用于其他位置。 
  
 **PropCopyMore** 不需要分配内存，除非复制的属性值的类型（如 PT_STRING8）不适合 [SPropValue](spropvalue.md) 结构。 对于这些大型属性，该函数使用 [MAPIAllocateMore](mapiallocatemore.md) 函数分配内存，其中一个指针将传递到  _lpfAllocMore_ 参数中。 
  
不等同地使用 **PropCopyMore** 片段内存;请考虑改为使用 [ScCopyProps](sccopyprops.md) 函数。 
  

