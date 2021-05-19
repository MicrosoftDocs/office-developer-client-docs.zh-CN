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
  
在数组及其数据被复制或移动到新位置之后，调整 [SPropValue](spropvalue.md) 数组中的指针。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapidefs.h  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供商  <br/> |
   
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
  
> [in]  _rgprop_ 参数指向的数组中的属性计数。 
    
 _rgprop_
  
> [in]指向要调整指针 [的 SPropValue](spropvalue.md) 结构的数组的指针。 
    
 _pvBaseOld_
  
> [in]指向 rgprop 参数指向的数组的原始  _基地址的_ 指针。 
    
 _pvBaseNew_
  
> [in]指向  _rgprop_ 参数指向的数组的新基地址的指针。 
    
 _这些_
  
> [in， out]指向  _pvBaseNew_ 参数指示的数组大小的可选指针（以字节为单位）。 如果不为 NULL，  _则将 pv_ 参数设置为  _pvD_ 参数中存储的字节数。 
    
## <a name="return-value"></a>返回值

S_OK
  
> 指针已成功调整。
    
MAPI_E_INVALID_PARAMETER
  
> 一个或两个参数无效，或遇到未知属性类型。
    
## <a name="remarks"></a>备注

**ScRelocProps** 函数的运行假设是最初在类似于 **对 ScCopyProps** 函数的调用的单个调用中分配了调整指针的属性值数组。 如果客户端应用程序或服务提供商使用从脱节的内存块构建的属性值，则它应改为使用 [ScCopyProps](sccopyprops.md) 复制属性。 
  
 **ScRelocProps** 用于维护 [SPropValue](spropvalue.md) 数组中指针的有效性。 若要在将此类数组写入磁盘并读取磁盘时保持指针的有效性，请执行下列操作： 
  
1. 在将数组和数据写入磁盘之前，请对数组调用 **ScRelocProps，** 其中  _pvBaseNew_ 参数指向一些标准值零，例如。 
    
2. 从磁盘读取数组和数据后，对 _pvBaseOld_ 参数等于步骤 1 中使用的相同标准值的数组调用 **ScRelocProps。** 必须将数组和数据读取到通过单个分配创建的缓冲区中。 
    
3. **ScRelocProps** 的 _为可选_ 参数。 
    
## <a name="see-also"></a>另请参阅



[MAPIAllocateBuffer](mapiallocatebuffer.md)
  
[ScCountProps](sccountprops.md)
  
[ScDupPropset](scduppropset.md)
  
[ScRelocNotifications](screlocnotifications.md)

