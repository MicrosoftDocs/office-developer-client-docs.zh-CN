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
ms.openlocfilehash: c79d9ebb5be1d8af6c9136514d8a2b695513f755
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775142"
---
# <a name="hraddcolumnsex"></a>HrAddColumnsEx

  
  
**适用于**： Outlook 
  
添加或移到现有表的起点的列。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapiutil.h  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |客户端应用程序和服务提供商  <br/> |
   
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
  
> [in]指向受影响的 MAPI 表。 
    
 _lpproptagColumnsNew_
  
> [in]指向[SPropTagArray](sproptagarray.md)结构，其中包含要添加或移至表格的开头的属性的属性标记的数组。 
    
 _lpAllocateBuffer_
  
> [in]指向[MAPIAllocateBuffer](mapiallocatebuffer.md)函数，以用于分配内存。 
    
 _lpFreeBuffer_
  
> [in]指向[MAPIFreeBuffer](mapifreebuffer.md)函数，以用于释放内存。 
    
 _lpfnFilterColumns_
  
> [in]指向提供呼叫者的回调函数的指针。 如果_lpfnFilterColumns_参数设置为 NULL，则进行不回拨。 
    
 _ptaga_
  
> [in]指向包含属性标记之前添加或移至开头属性表中已存在数组[SPropTagArray](sproptagarray.md)结构。 **HrAddColumnsEx**传递给回调函数的参数为此指针指向_lpfnFilterColumns_。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功，并指定的列已移动或添加。
    
## <a name="remarks"></a>说明

传递给**HrAddColumnsEx**使用_lpproptagColumnsNew_参数的属性将成为公开上后续调用[IMAPITable::QueryRows](imapitable-queryrows.md)方法的第一个属性。 前面的表的_lpproptagColumnsNew_参数中未指定任何属性公开后的添加和移动的所有属性。 
  
如果调用**QueryRows**时未定义任何表属性，也会返回与属性类型 PT_NULL 属性标识符 PROP_ID_NULL。 
  
## <a name="notes-to-callers"></a>给调用方的说明

**HrAddColumnsEx**函数允许呼叫者提供了一个回调函数来筛选表中，例如将字符串转换为 PT_STRING8 属性类型 PT_UNICODE 中已存在的列。 **HrAddColumnsEx**将指针传递到以前的现有列将作为参数设置为的回调函数中。 回调函数可以更改属性标记数组中的数据，但不能添加新的标签。 
  
 如果一个提供，然后添加或移动指定的列，并且最后调用[IMAPITable::SetColumns](imapitable-setcolumns.md)， **HrAddColumnsEx**首先调用的回调函数。 
  
_LpAllocateBuffer_和_lpFreeBuffer_输入的参数分别指向[MAPIAllocateBuffer](mapiallocatebuffer.md)和[MAPIFreeBuffer](mapifreebuffer.md)函数。 传递给**HrAddColumnsEx**的指针的确切值取决于呼叫者是否位于客户端应用程序或服务提供商。 客户端将指针传递到具有指定名称的 MAPI 功能。 服务提供商将传递它在其初始化呼叫中收到或通过调用[IMAPISupport::GetMemAllocRoutines](imapisupport-getmemallocroutines.md)方法检索的指针。 
  
## <a name="see-also"></a>另请参阅



[IMAPITable::QueryColumns](imapitable-querycolumns.md)

