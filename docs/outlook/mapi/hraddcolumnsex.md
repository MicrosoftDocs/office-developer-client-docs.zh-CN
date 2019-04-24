---
title: HrAddColumnsEx
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.HrAddColumnsEx
api_type:
- COM
ms.assetid: c0a65d2b-a9b8-4477-a1c7-18c8478126f6
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 9ca34fb2cce6e86c42e8e9525cd213f1008997d6
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32348368"
---
# <a name="hraddcolumnsex"></a>HrAddColumnsEx

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
将列添加或移动到现有表的开头。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiutil  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供程序  <br/> |
   
```cpp
HRESULT HrAddColumnsEx(
  LPMAPITABLE lptbl,
  LPSPropTagArray lpproptagColumnsNew,
  LPALLOCATEBUFFER lpAllocateBuffer,
  LPFREEBUFFER lpFreeBuffer,
  void (FAR * lpfnFilterColumns)(
  LPSPropTagArray ptaga)
);
```

## <a name="parameters"></a>参数

 _lptbl_
  
> 实时指向受影响的 MAPI 表的指针。 
    
 _lpproptagColumnsNew_
  
> 实时指向[SPropTagArray](sproptagarray.md)结构的指针, 该结构包含要添加或移动到表开头的属性的属性标记数组。 
    
 _lpAllocateBuffer_
  
> 实时指向用于分配内存的[MAPIAllocateBuffer](mapiallocatebuffer.md)函数的指针。 
    
 _lpFreeBuffer_
  
> 实时指向用于释放内存的[MAPIFreeBuffer](mapifreebuffer.md)函数的指针。 
    
 _lpfnFilterColumns_
  
> 实时指向由调用方提供的回调函数的指针。 如果将_lpfnFilterColumns_参数设置为 NULL, 则不会进行任何回调。 
    
 _ptaga_
  
> 实时指向[SPropTagArray](sproptagarray.md)结构的指针, 该结构包含在添加属性或将属性移到开头之前表中已存在的属性标记的数组。 **HrAddColumnsEx**将此指针作为参数传递给由_lpfnFilterColumns_指向的回调函数。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功, 并已移动或添加指定的列。
    
## <a name="remarks"></a>注解

使用_lpproptagColumnsNew_参数传递给**HrAddColumnsEx**的属性成为对[IMAPITable:: QueryRows](imapitable-queryrows.md)方法的后续调用中公开的第一个属性。 在表中先前未在_lpproptagColumnsNew_参数中指定的任何属性都将在所有添加和移动的属性之后公开。 
  
如果在调用**QueryRows**时未定义任何表属性, 则将使用属性类型 PT_NULL 和属性标识符 PROP_ID_NULL 返回它们。 
  
## <a name="notes-to-callers"></a>给调用方的说明

**HrAddColumnsEx**函数允许调用方提供一个回调函数, 以筛选表中已存在的列, 例如, 将字符串从属性类型 PT_UNICODE 转换为 PT_STRING8。 **HrAddColumnsEx**将一个指针传递给之前的现有列, 并将其设置为回调函数的参数。 回调函数可以更改属性标记数组中的数据, 但不能添加新标记。 
  
 **HrAddColumnsEx**首先调用回调函数 (如果提供了一个), 然后添加或移动指定的列, 最后调用[IMAPITable:: SetColumns](imapitable-setcolumns.md)。 
  
_lpAllocateBuffer_和_lpFreeBuffer_输入参数分别指向[MAPIAllocateBuffer](mapiallocatebuffer.md)和[MAPIFreeBuffer](mapifreebuffer.md)函数。 传递给**HrAddColumnsEx**的指针的确切值取决于调用方是客户端应用程序还是服务提供程序。 客户端将指向 MAPI 函数的指针传递给指定的名称。 服务提供程序在其初始化调用中传递接收到的指针, 或通过调用[IMAPISupport:: GetMemAllocRoutines](imapisupport-getmemallocroutines.md)方法来检索它们。 
  
## <a name="see-also"></a>另请参阅



[IMAPITable::QueryColumns](imapitable-querycolumns.md)

