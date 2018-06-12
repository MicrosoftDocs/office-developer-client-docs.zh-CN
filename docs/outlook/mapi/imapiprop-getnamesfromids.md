---
title: IMAPIPropGetNamesFromIDs
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIProp.GetNamesFromIDs
api_type:
- COM
ms.assetid: 3efa4731-cf32-4a6c-9ba8-d059e58b0d98
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: a2ec6def319b1f4686a61e9f97a936bfeba0d410
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775531"
---
# <a name="imapipropgetnamesfromids"></a>IMAPIProp::GetNamesFromIDs

  
  
**适用于**： Outlook 
  
提供对应于一个或多个属性标识符的属性名称。
  
```cpp
HRESULT GetNamesFromIDs(
  LPSPropTagArray FAR * lppPropTags,
  LPGUID lpPropSetGuid,
  ULONG ulFlags,
  ULONG FAR * lpcPropNames,
  LPMAPINAMEID FAR * FAR * lpppPropNames
);
```

## <a name="parameters"></a>参数

 _lppPropTags_
  
> [传入、 传出]在输入指向包含属性的数组[SPropTagArray](sproptagarray.md)结构的标签;否则，为 NULL，指示应返回所有名称。 属性标记数组的**cValues**成员不能为 0。 如果_lppPropTags_上输入, 的有效指针**GetNamesFromIDs**返回包含数组中每个属性标识符的名称。 
    
 _lpPropSetGuid_
  
> [in]指向的 GUID 或[GUID](guid.md)的结构，标识属性集。 _LpPropSetGuid_参数可以指向有效的属性集，也可以是 NULL。 
    
 _ulFlags_
  
> [in]位掩码的标志，指示要返回的名称的类型。 可使用以下标志 （如果设置两个标志，没有将返回名称）：
    
MAPI_NO_IDS 
  
> 返回仅存储为 Unicode 字符串的名称的请求。 
    
MAPI_NO_STRINGS 
  
> 返回仅存储为数字标识符的名称的请求。 
    
 _lpcPropNames_
  
> [输出]指向数目_lppPropNames_参数指向该数组中的属性名称指针的指针。 
    
 _lpppPropNames_
  
> [输出]指向包含属性名称数组指向[MAPINAMEID](mapinameid.md)结构的指针的指针。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功返回的属性名称。 
    
MAPI_E_NO_SUPPORT 
  
> 对象不支持命名的属性。 
    
MAPI_W_ERRORS_RETURNED 
  
> 调用成功总体上讲，但不是会返回一个或多个属性的名称。 属性标记为失败属性有**PT_ERROR**属性类型。 返回此警告时，应处理呼叫为成功。 若要测试此警告，请使用**HR_FAILED**宏。 有关详细信息，请参阅[使用宏的错误处理](using-macros-for-error-handling.md)。 
    
MAPI_E_INVALID_PARAMETER 
  
> 一个或多个所指的_lppPropTags_属性标记数组中的条目的**cValues**成员设置为 0。 
    
## <a name="remarks"></a>备注

按属性标识符对大多数属性的访问时，可以通过名称访问某些属性。 **IMAPIProp::GetNamesFromIDs**方法可调用它以执行下列操作： 
  
- 检索特定的属性集内的特定属性标识符的名称。
    
- 检索设置的任何属性中的特定属性标识符的名称。
    
- 检索的对象映射中包含的所有命名属性的名称。
    
如果具有一个或多个属性标识符的有效属性标记数组的_lppPropTags_指向和_lpPropSetGuid_指向有效属性设置， **GetNamesFromIDs**忽略属性集和属性类型，并返回的所有名称映射到指定的标识符。 
  
如果_lppPropTags_指向与一个或多个属性标识符和_lpPropSetGuid_有效属性标记数组为 NULL， **GetNamesFromIDs**返回所有将映射到指定标识符的名称。 
  
如果指定的标识符不具有一个名称， **GetNamesFromIDs** _lpppPropNames_中返回的结构中的该标识符就地返回 NULL，并返回 MAPI_W_ERRORS_RETURNED。 
  
如果_lpPropSetGuid_和_lppPropTags_均为空， **GetNamesFromIDs**分配新的属性标记数组，并返回所有的所有对象的命名属性的名称。 
  
当没有要返回的名称时，可能是因为请求的属性集合中没有任何属性或由标志，排除类型的所有属性都**GetNamesFromIDs**执行以下任务： 
  
- 返回 S_OK。
    
- 分配新的**SPropTagArray**结构，并将**cValues**成员设置为 0。 
    
- 将_lpcPropNames_的内容设置为 0。 
    
- 将_lpppPropNames_的内容设置为 NULL。 
    
## <a name="notes-to-implementers"></a>针对实施者的注释

如果_lpPropSetGuid_指向有效的属性集和_lppPropTags_为 NULL，则结果是未定义。 您可以使用以下策略之一： 
  
- 忽略属性集，该属性标记数组中返回标识符的名称。
    
- 属于指定的属性集属性标记数组中返回仅的标识符的名称。
    
- 呼叫，返回 MAPI_E_INVALID_PARAMETER 将失败。 
    
## <a name="notes-to-callers"></a>给调用方的说明

若要检索所有对象的命名属性，必须首先调用该对象的[IMAPIProp::GetPropList](imapiprop-getproplist.md)方法，然后传递到**GetNamesFromIDs**0x8000 范围之上的返回的标识符。
  
如果传递有效的属性集，而不是有效属性标记数组，准备无法预料的结果。 **GetNamesFromIDs**某些实现忽略属性集，该属性标记数组中返回标识符的名称。 某些实现返回 MAPI_E_INVALID_PARAMETER。 仍其他实现设置的属性中返回的所有属性的标识符的名称。 如果属性集，PS_PUBLIC_STRINGS **GetNamesFromIDs**可以返回已创建的所有名称。 服务提供商是否存储在与公共字符串关联的标识符的属性并不重要。 
  
完后，属性名称，则检查_lpcPropNames_参数，以确定是否返回任何名称的内容。 如果是这样，呼叫[MAPIFreeBuffer](mapifreebuffer.md)函数以释放内存指向_lppPropTags_和_lpppPropNames_时返回一个成功的结果。 一次调用**MAPIFreeBuffer**就足以为每个参数;您不必遍历的指针数组和单独释放每个**MAPINAMEID**结构。 
  
有关命名属性的详细信息，请参阅[MAPI 命名属性](mapi-named-properties.md)。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|SingleMAPIPropListCtrl.cpp  <br/> |CSingleMAPIPropListCtrl::FindAllNamedProps  <br/> |MFCMAPI 使用**IMAPIProp::GetNamesFromIDs**方法查找以前未映射的命名属性。  <br/> |
   
## <a name="see-also"></a>另请参阅



[GUID](guid.md)
  
[IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md)
  
[IMAPIProp::GetPropList](imapiprop-getproplist.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)
  
[MAPINAMEID](mapinameid.md)
  
[SPropTagArray](sproptagarray.md)
  
[IMAPIProp: IUnknown](imapipropiunknown.md)


[MFCMAPI 作为的代码示例](mfcmapi-as-a-code-sample.md)
  
[MAPI 命名属性](mapi-named-properties.md)
  
[用于错误处理的宏](using-macros-for-error-handling.md)

