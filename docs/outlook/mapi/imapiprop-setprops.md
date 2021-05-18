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
  
> [in]  _lpPropArray_ 参数指向的属性值计数。 _cValues_ 参数不能为 0。 
    
 _lpPropArray_
  
> [in]指向包含要更新的属性值 [的 SPropValue](spropvalue.md) 结构的数组的指针。 
    
 _lppProblems_
  
> [in， out]在输入时，指向指向 [SPropProblemArray 结构的指针的](spropproblemarray.md) 指针;否则为 NULL，表示不需要错误信息。 如果  _lppProblems_ 是输入的有效指针 **，SetProps** 将返回有关更新一个或多个属性时错误的详细信息。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 属性已成功更新。
    
以下值可以在 **SPropProblemArray** 结构中返回，但不能作为 **SetProps 的返回值**：
  
MAPI_E_BAD_CHARWIDTH 
  
> 设置 MAPI_UNICODE 标志，而实现不支持 Unicode，或者MAPI_UNICODE未设置，并且实现仅支持 Unicode。
    
MAPI_E_COMPUTED 
  
> 属性无法更新，因为它是只读的，由负责对象的服务提供商计算。
    
MAPI_E_INVALID_TYPE 
  
> 属性类型无效。
    
MAPI_E_NO_ACCESS 
  
> 试图修改只读对象或访问用户权限不足的对象。
    
MAPI_E_NOT_ENOUGH_MEMORY 
  
> 属性无法更新，因为它大于远程过程调用 (RPC) 缓冲区大小。
    
MAPI_E_UNEXPECTED_TYPE 
  
> 属性类型不是调用实现预期的类型。
    
## <a name="notes-to-implementers"></a>针对实现者的说明

忽略 [PidTagNull PR_NULL (PidTagNull](pidtagnull-canonical-property.md)) 属性标记和类型为 PT_ERROR **的所有属性**。 不要对 **SPropProblemArray** 结构进行更改或报告问题。 
  
如果MAPI_E_INVALID_PARAMETER数组中包含类型 **PT_OBJECT，** 则返回值。 如果数组中包含多值属性，并且其 **cValues** 成员设置为 0，则也返回此错误。 
  
如果调用整体成功，但设置某些属性时出现问题，则返回 S_OK，将问题的信息放在 _lppProblems_ 参数指向的 **SPropProblemArray** 结构的适当条目中。 
  
## <a name="notes-to-callers"></a>给调用方的说明

根据服务提供商的不同，您还可以通过传递包含与之前用于给定属性标识符不同的类型的属性标记来更改属性类型。
  
如果包含对象不支持的属性的属性标记，并且 **SetProps** 的实现允许创建新属性，则该属性将添加到对象中。 将丢弃与用于新属性的属性标识符一起存储的任何以前的值。 
  
请注意，S_OK返回值并不能保证已成功更新所有属性。 某些提供程序缓存 **SetProps** 调用，直到收到需要提供程序干预的调用，例如 [IMAPIProp：：SaveChanges](imapiprop-savechanges.md) 或 [IMAPIProp：：GetProps](imapiprop-getprops.md)。 因此，可以接收与以后调用的 **SetProps** 调用相关的错误值。 
  
如果 **SetProps** S_OK，请检查 _lppProblems_ 指向的 **SPropProblemArray** 结构，以发现更新单个属性时出现问题。 如果 **SetProps** 返回错误，请不要检查属性问题数组。 相反，请调用对象的 [IMAPIProp：：GetLastError](imapiprop-getlasterror.md) 方法。 
  
更新大型属性时 **，SetProps** 可能会失败并返回MAPI_E_NOT_ENOUGH_MEMORY。 属性没有最大大小，不同对象可以有不同的限制。 如果你处理潜在的大型属性，请准备好调用 [IMAPIProp：：OpenProperty](imapiprop-openproperty.md) 方法，如果 **SetProps** 返回此错误值IID_IStream则使用 IID_IStream 作为接口标识符。 
  
调用 [MAPIFreeBuffer](mapifreebuffer.md) 函数以释放 **SPropProblemArray** 结构。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|PropertyEditor.cpp  <br/> |CPropertyEditor：：WriteSPropValueToObject  <br/> |MFCMAPI 使用 **IMAPIProp：：SetProps** 方法在编辑属性后将属性写回对象。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIProp::GetLastError](imapiprop-getlasterror.md)
  
[IMAPIProp::GetProps](imapiprop-getprops.md)
  
[IMAPIProp::OpenProperty](imapiprop-openproperty.md)
  
[IMAPIProp::SaveChanges](imapiprop-savechanges.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)
  
[SPropProblemArray](spropproblemarray.md)
  
[SPropValue](spropvalue.md)
  
[IMAPIProp : IUnknown](imapipropiunknown.md)

