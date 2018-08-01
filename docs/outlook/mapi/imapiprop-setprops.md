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
ms.openlocfilehash: 304295e3ac77fb67ec5875620a7a269377b542c1
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775527"
---
# <a name="imapipropsetprops"></a>IMAPIProp::SetProps

  
  
**适用于**： Outlook 
  
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
  
> [in]_LpPropArray_参数指向的属性值的计数。 _CValues_参数不能 0。 
    
 _lpPropArray_
  
> [in]一个指向一个[SPropValue](spropvalue.md)结构包含要更新的属性值的数组。 
    
 _lppProblems_
  
> [传入、 传出]在输入时，为[SPropProblemArray](spropproblemarray.md)结构; 指针的指针否则，为 NULL，表明错误信息不需要。 如果_lppProblems_上输入, 的有效指针**SetProps**更新一个或多个属性的返回有关错误的详细的信息。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 属性已成功更新。
    
可以为**SetProps**中返回在**SPropProblemArray**结构中，但不是返回值是以下值：
  
MAPI_E_BAD_CHARWIDTH 
  
> 既设置了 MAPI_UNICODE 标志实现不支持 Unicode，或未设置 MAPI_UNICODE 并实现支持仅 Unicode。
    
MAPI_E_COMPUTED 
  
> 无法更新属性，因为它是只读的计算负责对象的服务提供商。
    
MAPI_E_INVALID_TYPE 
  
> 属性类型无效。
    
MAPI_E_NO_ACCESS 
  
> 尝试修改只读对象或访问其用户没有足够的权限的对象。
    
MAPI_E_NOT_ENOUGH_MEMORY 
  
> 无法更新属性，因为它是大于远程过程调用 (RPC) 缓冲区大小。
    
MAPI_E_UNEXPECTED_TYPE 
  
> 属性类型不需要调用实现的类型。
    
## <a name="notes-to-implementers"></a>针对实施者的注释

忽略**PR_NULL** ([PidTagNull](pidtagnull-canonical-property.md)) 属性标记和**PT_ERROR**类型的所有属性。 不进行更改或报告问题**SPropProblemArray**结构中。 
  
如果类型**PT_OBJECT**的属性包含属性值数组中，返回 MAPI_E_INVALID_PARAMETER。 也返回此错误，则多值属性包含数组和其**cValues**成员中设置为 0。 
  
如果调用成功总体，但有问题设置的一些属性，返回 S_OK 和问题的信息置于_lppProblems_参数指向的**SPropProblemArray**结构中的相应项。 
  
## <a name="notes-to-callers"></a>给调用方的说明

根据服务提供程序，您可能还能够通过传递比以前使用的给定的属性标识符具有包含不同类型的属性标记更改的属性类型。
  
如果包括属性标记为不支持的对象的属性和**SetProps**的实现允许创建的新属性，则将属性添加到对象。 存储用于新属性的属性标识符与以前的任何值将被丢弃。 
  
请注意，不保证 S_OK 返回值的所有属性已成功更新。 某些提供程序直到其接收呼叫，需要提供程序干预，如[IMAPIProp::SaveChanges](imapiprop-savechanges.md)或[IMAPIProp::GetProps](imapiprop-getprops.md)缓存**SetProps**呼叫。 因此，很可能收到与更高版本的呼叫的**SetProps**呼叫相关的错误值。 
  
如果**SetProps** ，则返回 S_OK，检查所指的_lppProblems_更新各个属性的问题的**SPropProblemArray**结构。 如果**SetProps**返回一个错误，则不会检查属性问题数组。 相反，呼叫对象的[IMAPIProp::GetLastError](imapiprop-getlasterror.md)方法。 
  
更新时大型属性， **SetProps**可以失败并返回 MAPI_E_NOT_ENOUGH_MEMORY。 没有属性，最大大小和不同的对象可以具有不同的限制。 如果您处理可能很大的属性，准备接口标识调用与 IID_IStream [IMAPIProp::OpenProperty](imapiprop-openproperty.md)方法，如果**SetProps**返回此错误值。 
  
调用[MAPIFreeBuffer](mapifreebuffer.md)函数以释放**SPropProblemArray**结构。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|PropertyEditor.cpp  <br/> |CPropertyEditor::WriteSPropValueToObject  <br/> |MFCMAPI 使用**IMAPIProp::SetProps**方法后，已编辑属性回写到对象的属性。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIProp::GetLastError](imapiprop-getlasterror.md)
  
[IMAPIProp::GetProps](imapiprop-getprops.md)
  
[IMAPIProp::OpenProperty](imapiprop-openproperty.md)
  
[IMAPIProp::SaveChanges](imapiprop-savechanges.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)
  
[SPropProblemArray](spropproblemarray.md)
  
[SPropValue](spropvalue.md)
  
[IMAPIProp : IUnknown](imapipropiunknown.md)

