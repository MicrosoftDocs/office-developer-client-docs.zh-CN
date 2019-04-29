---
title: IMAPIPropSetProps
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIProp.SetProps
api_type:
- COM
ms.assetid: 49f007c9-42e5-4391-8b83-988c9b0ebdba
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 87709f8a77471637d7652982669bcba93ca2e1dd
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33412616"
---
# <a name="imapipropsetprops"></a>IMAPIProp::SetProps

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
更新一个或多个属性。
  
```cpp
HRESULT SetProps(
  ULONG cValues,
  LPSPropValue lpPropArray,
  LPSPropProblemArray FAR * lppProblems
);
```

## <a name="parameters"></a>参数

 _cValues_
  
> 实时由_lpPropArray_参数指向的属性值的计数。 _cValues_参数不得为0。 
    
 _lpPropArray_
  
> 实时指向[SPropValue](spropvalue.md)结构数组的指针, 该数组包含要更新的属性值。 
    
 _lppProblems_
  
> [in, out]在输入时, 指向指向[SPropProblemArray](spropproblemarray.md)结构的指针的指针;否则为 NULL, 表示无需错误信息。 如果_lppProblems_是有效的输入指针, **SetProps**将返回有关更新一个或多个属性中的错误的详细信息。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 属性已成功更新。
    
以下值可在**SPropProblemArray**结构中返回, 但不能在**SetProps**的返回值中返回:
  
MAPI_E_BAD_CHARWIDTH 
  
> 设置了 MAPI_UNICODE 标志, 且实现不支持 unicode, 或者未设置 MAPI_UNICODE, 且实现仅支持 UNICODE。
    
MAPI_E_COMPUTED 
  
> 属性不能更新, 因为它是只读的, 由负责该对象的服务提供程序进行计算。
    
MAPI_E_INVALID_TYPE 
  
> 属性类型无效。
    
MAPI_E_NO_ACCESS 
  
> 试图修改只读对象或访问用户拥有的对象权限不足的对象。
    
MAPI_E_NOT_ENOUGH_MEMORY 
  
> 属性不能更新, 因为它大于远程过程调用 (RPC) 缓冲区大小。
    
MAPI_E_UNEXPECTED_TYPE 
  
> 属性类型不是调用实现所需的类型。
    
## <a name="notes-to-implementers"></a>针对实现者的说明

忽略类型为**PT_ERROR**的**PR_NULL** ([PidTagNull](pidtagnull-canonical-property.md)) 属性标记和所有属性。 请勿在**SPropProblemArray**结构中进行更改或报告问题。 
  
如果属性值数组中包含**PT_OBJECT**类型的属性, 则返回 MAPI_E_INVALID_PARAMETER。 如果数组中包含多值属性, 并将其**cValues**成员设置为 0, 则也会返回此错误。 
  
如果调用成功, 但在设置某些属性时出现问题, 则返回 S_OK, 并将有关问题的信息放在_lppProblems_参数指向的**SPropProblemArray**结构的相应条目中。 
  
## <a name="notes-to-callers"></a>给调用方的说明

根据服务提供程序的不同, 您还可以通过传递包含与先前用于给定属性标识符的类型不同的属性标记来更改属性类型。
  
如果包含对象不支持的属性的属性标记, 且**SetProps**的实现允许创建新的属性, 则会将该属性添加到对象中。 以前与用于新属性的属性标识符一起存储的任何值都将被丢弃。 
  
请注意, S_OK 返回值并不保证已成功更新所有属性。 某些提供程序在收到需要提供程序干预的调用 (如[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)或[IMAPIProp:: GetProps](imapiprop-getprops.md)) 之前缓存**SetProps**调用。 因此, 可以接收与后续调用相关的**SetProps**调用的错误值。 
  
如果**SetProps**返回 S_OK, 请检查_lppProblems_针对更新各个属性的问题所指向的**SPropProblemArray**结构。 如果**SetProps**返回错误, 请勿检查属性问题数组。 而是调用对象的[IMAPIProp:: GetLastError](imapiprop-getlasterror.md)方法。 
  
更新大型属性时, **SetProps**可能会失败并返回 MAPI_E_NOT_ENOUGH_MEMORY。 属性没有最大大小, 不同的对象可以有不同的限制。 如果您处理可能的大型属性, 请准备好在**SetProps**返回此错误值时将[IMAPIProp:: OpenProperty](imapiprop-openproperty.md)方法用作接口标识符, 以将 IID_IStream 作为接口标识符进行调用。 
  
调用[MAPIFreeBuffer](mapifreebuffer.md)函数以释放**SPropProblemArray**结构。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|PropertyEditor  <br/> |CPropertyEditor:: WriteSPropValueToObject  <br/> |MFCMAPI 使用**IMAPIProp:: SetProps**方法在编辑属性后将属性写入对象。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIProp::GetLastError](imapiprop-getlasterror.md)
  
[IMAPIProp::GetProps](imapiprop-getprops.md)
  
[IMAPIProp::OpenProperty](imapiprop-openproperty.md)
  
[IMAPIProp::SaveChanges](imapiprop-savechanges.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)
  
[SPropProblemArray](spropproblemarray.md)
  
[SPropValue](spropvalue.md)
  
[IMAPIProp : IUnknown](imapipropiunknown.md)

