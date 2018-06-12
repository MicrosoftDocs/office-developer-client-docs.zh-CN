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
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 750d8b8d50acb9cf7340e6553062412667398665
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778562"
---
# <a name="propcopymore"></a>PropCopyMore

  
  
**适用于**： Outlook 
  
将单个属性值从源位置复制到目标位置。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapiutil.h  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |客户端应用程序和服务提供商  <br/> |
   
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
  
> [输出]此函数向其中写入定义复制的属性值的[SPropValue](spropvalue.md)结构的位置的指针。 
    
 _lpSPropValueSrc_
  
> [in]指向包含属性值将复制的[SPropValue](spropvalue.md)结构的指针。 
    
 _lpfAllocMore_
  
> [in]指向[MAPIAllocateMore](mapiallocatemore.md)函数，以用于分配更多内存，如果目标位置没有足够容纳要复制的属性。 
    
 _lpvObject_
  
> [in]指向其**MAPIAllocateMore**将分配空间必要对象的指针。 
    
## <a name="return-value"></a>返回值

S_OK
  
> 已成功复制单个属性值。
    
MAPI_E_NO_SUPPORT
  
> 遇到了未知的属性类型。
    
## <a name="remarks"></a>备注

客户端应用程序或服务提供商可以使用**PropCopyMore**函数复制超出将释放才能在其他地方使用它的表的属性。 
  
 **PropCopyMore**不需要除非复制该属性值的类型，如 PT_STRING8，不适合[SPropValue](spropvalue.md)结构中的分配内存。 对于这些大型属性，该函数分配内存使用指将指针传递_lpfAllocMore_参数中的[MAPIAllocateMore](mapiallocatemore.md)函数。 
  
Injudicious 利用**PropCopyMore**片段内存;考虑使用[ScCopyProps](sccopyprops.md)函数。 
  

