---
title: ScCopyProps
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.ScCopyProps
api_type:
- COM
ms.assetid: 08bc256c-9706-4f3e-9a12-3e9cca5e4caa
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 979415f1d792f92e593a7073cc84cfd6ba832b6c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778683"
---
# <a name="sccopyprops"></a>ScCopyProps

  
  
**适用于**： Outlook 
  
复制到新目标[SPropValue](spropvalue.md)结构的数组定义的属性。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapiutil.h  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |客户端应用程序和服务提供商  <br/> |
   
```cpp
SCODE ScCopyProps(
  int cprop,
  LPSPropValue rgprop,
  LPVOID pvDst,
  ULONG FAR * pcb
);
```

## <a name="parameters"></a>参数

 _cprop_
  
> [in]要复制的属性的计数。 
    
 _rgprop_
  
> [in]为数组定义要复制的属性的[SPropValue](spropvalue.md)结构的指针。 _Rgprop_参数没有为指向开始的数组，但它必须指向某数组中的**SPropValue**结构开始处。 
    
 _pvDst_
  
> [in]指向此函数将属性复制到内存中的初始位置的指针。 
    
 _pcb_
  
> [输出]指向的大小，以字节为单位的内存_pvDst_参数指向的块的可选指针。 
    
## <a name="return-value"></a>返回值

S_OK
  
> 已成功复制属性。
    
MAPI_E_INVALID_PARAMETER
  
> 遇到了未知的属性类型。
    
## <a name="remarks"></a>说明

新的数组和其数据驻留在创建一个分配，与缓冲区和[ScRelocProps](screlocprops.md)函数可用于调整中的单个[SPropValue](spropvalue.md)结构的指针。 在此调整之前, 指针是有效。 
  
 **ScCopyProps**维持复制的属性数组的原始属性顺序。 
  
_Pcb_参数是可选的。如果不为 NULL，则将其设置为_pvDst_参数中存储的字节数。 
  
## <a name="see-also"></a>另请参阅



[ScDupPropset](scduppropset.md)

