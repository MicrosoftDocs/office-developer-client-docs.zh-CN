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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: f6688afde9b36a7722eaaf768f091481c15b7308
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33423571"
---
# <a name="imapipropgetnamesfromids"></a>IMAPIProp::GetNamesFromIDs

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
提供与一个或多个属性标识符相对应的属性名称。
  
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
  
> [in, out]在输入时, 指向包含属性标记数组的[SPropTagArray](sproptagarray.md)结构的指针;否则为 NULL, 表示应返回所有名称。 属性标记数组的**cValues**成员不能为0。 如果_lppPropTags_是有效的输入指针, **GetNamesFromIDs**将返回数组中包含的每个属性标识符的名称。 
    
 _lpPropSetGuid_
  
> 实时指向标识属性集的 guid 或[guid](guid.md)结构的指针。 _lpPropSetGuid_参数可指向有效的属性集, 也可以为 NULL。 
    
 _ulFlags_
  
> 实时标志的位掩码, 指示要返回的名称的类型。 可以使用以下标志 (如果同时设置了这两个标志, 则不会返回任何名称):
    
MAPI_NO_IDS 
  
> 仅返回以 Unicode 字符串形式存储的名称的请求。 
    
MAPI_NO_STRINGS 
  
> 仅返回作为数字标识符存储的名称的请求。 
    
 _lpcPropNames_
  
> 排除一个指针, 指向由_lppPropNames_参数指向的数组中的属性名称指针的计数。 
    
 _lpppPropNames_
  
> 排除指向包含属性名称的[MAPINAMEID](mapinameid.md)结构的指针数组的指针。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 成功返回属性名称。 
    
MAPI_E_NO_SUPPORT 
  
> 对象不支持命名属性。 
    
MAPI_W_ERRORS_RETURNED 
  
> 呼叫全部成功, 但无法返回一个或多个属性的名称。 失败属性的属性标记的属性类型为**PT_ERROR**。 返回此警告时, 应以成功的方式处理该调用。 若要测试此警告, 请使用**HR_FAILED**宏。 有关详细信息, 请参阅[使用宏进行错误处理](using-macros-for-error-handling.md)。 
    
MAPI_E_INVALID_PARAMETER 
  
> 由_lppPropTags_指向的属性标记数组中的一个或多个条目的**cValues**成员设置为0。 
    
## <a name="remarks"></a>说明

虽然对大多数属性的访问都是通过属性标识符访问, 但某些属性可以通过名称访问。 可以调用**IMAPIProp:: GetNamesFromIDs**方法来执行以下操作: 
  
- 检索特定属性集中特定属性标识符的名称。
    
- 在任何属性集中检索特定属性标识符的名称。
    
- 检索对象映射中包含的所有命名属性的名称。
    
如果_lppPropTags_指向具有一个或多个属性标识符的有效属性标记数组, 并且_lpPropSetGuid_指向有效的属性集, 则**GetNamesFromIDs**将忽略该属性集和属性类型, 并返回所有名称。映射到指定标识符的。 
  
如果_lppPropTags_指向具有一个或多个属性标识符且_lpPropSetGuid_为 NULL 的有效属性标记数组, 则**GetNamesFromIDs**将返回映射到指定标识符的所有名称。 
  
如果指定的标识符没有名称, 则**GetNamesFromIDs**将在该标识符在_lpppPropNames_中返回的结构中的位置返回 NULL, 同时还返回 MAPI_W_ERRORS_RETURNED。 
  
如果_lpPropSetGuid_和_lppPropTags_都为 NULL, 则**GetNamesFromIDs**会分配一个新的属性标记数组, 并返回该对象的所有命名属性的所有名称。 
  
如果没有要返回的名称, 可能是因为请求的属性集中没有任何属性, 或者所有属性都不是由 flags 排除的类型, **GetNamesFromIDs**将执行以下操作: 
  
- 返回 S_OK。
    
- 分配一个新的**SPropTagArray**结构, 并将**cValues**成员设置为0。 
    
- 将_lpcPropNames_的内容设置为0。 
    
- 将_lpppPropNames_的内容设置为 NULL。 
    
## <a name="notes-to-implementers"></a>针对实现者的说明

如果_lpPropSetGuid_指向有效的属性集, 而_lppPropTags_为 NULL, 则结果是不确定的。 您可以使用以下策略之一: 
  
- 忽略属性集, 并在属性标记数组中返回标识符的名称。
    
- 仅返回属于指定属性集的属性标记数组中的标识符的名称。
    
- 使呼叫失败, 返回 MAPI_E_INVALID_PARAMETER。 
    
## <a name="notes-to-callers"></a>给调用方的说明

若要检索对象的所有命名属性, 必须先调用对象的[IMAPIProp:: GetPropList](imapiprop-getproplist.md)方法, 然后将大于0x8000 范围的返回标识符传递给**GetNamesFromIDs**。
  
如果传递的是有效的属性集, 而不是有效的属性标记数组, 则准备好实现不可预知的结果。 **GetNamesFromIDs**的某些实现将忽略该属性集, 并返回属性标记数组中的标识符的名称。 某些实现返回 MAPI_E_INVALID_PARAMETER。 此外, 其他实现将返回属性集中所有属性的标识符的名称。 如果属性集为 PS_PUBLIC_STRINGS, 则**GetNamesFromIDs**可以返回曾经创建的所有名称。 服务提供程序是否在与公共字符串关联的标识符下存储属性是 immaterial。 
  
使用完属性名称后, 请检查_lpcPropNames_参数的内容, 以确定是否返回任何名称。 如果是这样, 则调用[MAPIFreeBuffer](mapifreebuffer.md)函数, 以释放_lppPropTags_和_lpppPropNames_在返回成功的结果时指向的内存。 对每个参数的一次调用**MAPIFreeBuffer**是足够的;您不必遍历指针数组并单独释放每个**MAPINAMEID**结构。 
  
有关命名属性的详细信息, 请参阅[MAPI 命名属性](mapi-named-properties.md)。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|SingleMAPIPropListCtrl  <br/> |CSingleMAPIPropListCtrl:: FindAllNamedProps  <br/> |MFCMAPI 使用**IMAPIProp:: GetNamesFromIDs**方法来查找之前已映射的命名属性。  <br/> |
   
## <a name="see-also"></a>另请参阅



[GUID](guid.md)
  
[IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md)
  
[IMAPIProp::GetPropList](imapiprop-getproplist.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)
  
[MAPINAMEID](mapinameid.md)
  
[SPropTagArray](sproptagarray.md)
  
[IMAPIProp : IUnknown](imapipropiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)
  
[MAPI 命名属性](mapi-named-properties.md)
  
[使用宏进行错误处理](using-macros-for-error-handling.md)

