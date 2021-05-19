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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33427477"
---
# <a name="hraddcolumnsex"></a>HrAddColumnsEx

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
向现有表格的开头添加或移动列。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiutil.h  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供商  <br/> |
   
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
  
> [in]指向受影响的 MAPI 表的指针。 
    
 _lpproptagColumnsNew_
  
> [in]指向 [SPropTagArray](sproptagarray.md) 结构的指针，其中包含要添加或移动到表开头的属性的属性标记数组。 
    
 _lpAllocateBuffer_
  
> [in]指向 [MAPIAllocateBuffer](mapiallocatebuffer.md) 函数的指针，用于分配内存。 
    
 _lpFreeBuffer_
  
> [in]指向 [MAPIFreeBuffer](mapifreebuffer.md) 函数的指针，用于释放内存。 
    
 _lpfnFilterColumns_
  
> [in]指向调用方提供回调函数的指针。 如果  _lpfnFilterColumns_ 参数设置为 NULL，则不进行回调。 
    
 _ptaga_
  
> [in]指向 [SPropTagArray](sproptagarray.md) 结构的指针，其中包含属性添加或移动到开头之前表中已存在的属性标记数组。 **HrAddColumnsEx** 将此指针作为参数传递给  _lpfnFilterColumns 指向的回调函数_。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功，并移动或添加指定的列。
    
## <a name="remarks"></a>备注

使用 _lpproptagColumnsNew_ 参数传递给 **HrAddColumnsEx** 的属性将成为后续调用 [IMAPITable：：QueryRows](imapitable-queryrows.md)方法时公开的第一个属性。 表中以前未在  _lpproptagColumnsNew_ 参数中指定的任何属性都在所有添加和移动的属性之后公开。 
  
如果在调用 **QueryRows** 时未定义任何表属性，则返回这些属性时将返回属性类型PT_NULL属性标识符PROP_ID_NULL。 
  
## <a name="notes-to-callers"></a>给调用方的说明

**HrAddColumnsEx** 函数允许调用方提供回调函数来筛选表中已有的列，例如，将字符串从属性类型 PT_UNICODE 转换为 PT_STRING8。 **HrAddColumnsEx** 将指向以前存在的列集的指针作为参数传递给回调函数。 回调函数可以更改属性标记数组中的数据，但不能添加新标记。 
  
 **HrAddColumnsEx** 首先在提供回调函数时调用回调函数，然后添加或移动指定的列，最后调用 [IMAPITable：：SetColumns](imapitable-setcolumns.md)。 
  
_lpAllocateBuffer_ 和 _lpFreeBuffer_ 输入参数分别指向 [MAPIAllocateBuffer](mapiallocatebuffer.md)和 [MAPIFreeBuffer](mapifreebuffer.md)函数。 传递给 **HrAddColumnsEx** 的指针的确切值取决于调用方是客户端应用程序还是服务提供商。 客户端将指针传递给具有指定名称的 MAPI 函数。 服务提供商传递其在其初始化调用中收到的指针，或通过调用 [IMAPISupport：：GetMemAllocRoutines](imapisupport-getmemallocroutines.md) 方法检索的指针。 
  
## <a name="see-also"></a>另请参阅



[IMAPITable::QueryColumns](imapitable-querycolumns.md)

