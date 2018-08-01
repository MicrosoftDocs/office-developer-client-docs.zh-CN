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
ms.openlocfilehash: 06590fe55cb02b1abf036156877fd308548436f7
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778733"
---
# <a name="screlocprops"></a>ScRelocProps

  
  
**适用于**： Outlook 
  
数组和其数据被复制或移动到新位置后，请调整[SPropValue](spropvalue.md)数组中的指针。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapidefs.h  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |客户端应用程序和服务提供商  <br/> |
   
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
  
> [in]Count 属性数组中的指向_rgprop_参数。 
    
 _rgprop_
  
> [in]为数组[SPropValue](spropvalue.md)结构要调整指针的指针。 
    
 _pvBaseOld_
  
> [in]指向原始基址数组_rgprop_参数指向的指针。 
    
 _pvBaseNew_
  
> [in]指向新的基址数组_rgprop_参数指向的指针。 
    
 _pcb_
  
> [传入、 传出]可选指向的大小，以字节为单位指示_pvBaseNew_参数的数组。 如果不为 NULL， _pcb_参数设置为_pvD_参数中存储的字节数。 
    
## <a name="return-value"></a>返回值

S_OK
  
> 已成功调整指针。
    
MAPI_E_INVALID_PARAMETER
  
> 一个或两个参数无效，或遇到未知的属性类型。
    
## <a name="remarks"></a>说明

**ScRelocProps**函数以为，属性值数组指针进行调整为其最初分配的类似于对**ScCopyProps**函数的调用一次调用的操作。 如果客户端应用程序或服务提供商使用的内存脱节块建立的属性值，它应使用[ScCopyProps](sccopyprops.md)改为复制属性。 
  
 **ScRelocProps**用于维护[SPropValue](spropvalue.md)数组中的指针的有效性。 若要写入到此类数组和从磁盘中读取时维护指针的有效性，执行以下操作： 
  
1. 数组和数据写入磁盘之前, 调用**ScRelocProps**阵列上与指向某些标准的值为零，例如_pvBaseNew_参数。 
    
2. 从磁盘读取的数组和数据之后, 调用**ScRelocProps** _pvBaseOld_参数数组等于标准值在步骤 1 中使用的相同。 数组和数据必须读入创建一个分配缓冲区。 
    
3. **ScRelocProps** _pcb_参数是可选的。 
    
## <a name="see-also"></a>另请参阅



[MAPIAllocateBuffer](mapiallocatebuffer.md)
  
[ScCountProps](sccountprops.md)
  
[ScDupPropset](scduppropset.md)
  
[ScRelocNotifications](screlocnotifications.md)

