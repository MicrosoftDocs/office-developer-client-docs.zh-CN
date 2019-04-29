---
title: ScRelocProps
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.ScRelocProps
api_type:
- COM
ms.assetid: 4aafb254-6074-4a7c-b915-d3d33304ac38
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: c73fb96c9620a90ab0505b394fcb9853d02dcde5
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33421086"
---
# <a name="screlocprops"></a>ScRelocProps

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
在将数组及其数据复制或移动到新位置之后, 调整[SPropValue](spropvalue.md)数组中的指针。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |mapidefs。h  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供程序  <br/> |
   
```cpp
SCODE ScRelocProps(
  int cprop,
  LPSPropValue rgprop,
  LPVOID pvBaseOld,
  LPVOID pvBaseNew,
  ULONG FAR * pcb
);
```

## <a name="parameters"></a>参数

 _cprop_
  
> 实时由_rgprop_参数指向的数组中的属性计数。 
    
 _rgprop_
  
> 实时指向要调整其指针的[SPropValue](spropvalue.md)结构的数组的指针。 
    
 _pvBaseOld_
  
> 实时指向由_rgprop_参数指向的数组的原始基址的指针。 
    
 _pvBaseNew_
  
> 实时指向_rgprop_参数指向的数组的新基址的指针。 
    
 _pcb_
  
> [in, out]可选指针, 指向由_pvBaseNew_参数指示的数组的大小 (以字节为单位)。 如果不为 NULL, 则将_pcb_参数设置为_pvD_参数中存储的字节数。 
    
## <a name="return-value"></a>返回值

S_OK
  
> 已成功调整指针。
    
MAPI_E_INVALID_PARAMETER
  
> 一个或两个参数无效, 或者遇到未知的属性类型。
    
## <a name="remarks"></a>说明

**ScRelocProps**函数在假设您对其调整指针的属性值数组进行操作时, 最初是在与**ScCopyProps**函数的调用类似的单个调用中分配的。 如果客户端应用程序或服务提供程序正在使用从脱节内存块生成的属性值, 则应改用[ScCopyProps](sccopyprops.md)复制属性。 
  
 **ScRelocProps**用于维护[SPropValue](spropvalue.md)数组中的指针的有效性。 若要在将此类数组写入和读取磁盘时保持指针的有效性, 请执行以下操作: 
  
1. 在将数组和数据写入磁盘之前, 请使用_pvBaseNew_参数指向某个标准值零对数组调用**ScRelocProps** , 例如。 
    
2. 在从磁盘读取数组和数据之后, 对阵列调用**ScRelocProps** , 将_pvBaseOld_参数等于与步骤1中使用的相同标准值。 必须将数组和数据读入单个分配中创建的缓冲区。 
    
3. **ScRelocProps**的_pcb_参数是可选的。 
    
## <a name="see-also"></a>另请参阅



[MAPIAllocateBuffer](mapiallocatebuffer.md)
  
[ScCountProps](sccountprops.md)
  
[ScDupPropset](scduppropset.md)
  
[ScRelocNotifications](screlocnotifications.md)

