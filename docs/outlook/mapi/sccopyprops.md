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
ms.openlocfilehash: 1afd922459be2ec4bbbd27a61fdf6fcb425548c9
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33411006"
---
# <a name="sccopyprops"></a>ScCopyProps

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
将由[SPropValue](spropvalue.md)结构数组定义的属性复制到新目标。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiutil  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供程序  <br/> |
   
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
  
> 实时要复制的属性的计数。 
    
 _rgprop_
  
> 实时指向定义要复制的属性的[SPropValue](spropvalue.md)结构数组的指针。 _rgprop_参数不必指向数组的开头, 但它必须指向数组中的一个**SPropValue**结构的开始位置。 
    
 _pvDst_
  
> 实时指向此函数将在其中复制属性的内存中的初始位置的指针。 
    
 _pcb_
  
> 排除可选指针, 指向由_pvDst_参数指向的内存块的大小 (以字节为单位)。 
    
## <a name="return-value"></a>返回值

S_OK
  
> 已成功复制属性。
    
MAPI_E_INVALID_PARAMETER
  
> 遇到未知的属性类型。
    
## <a name="remarks"></a>说明

新数组及其数据驻留在通过单个分配创建的缓冲区中, [ScRelocProps](screlocprops.md)函数可用于调整各个[SPropValue](spropvalue.md)结构中的指针。 在此调整之前, 指针有效。 
  
 **ScCopyProps**维护复制的属性数组的原始属性顺序。 
  
_pcb_参数是可选的;如果不为 NULL, 则将其设置为_pvDst_参数中存储的字节数。 
  
## <a name="see-also"></a>另请参阅



[ScDupPropset](scduppropset.md)

