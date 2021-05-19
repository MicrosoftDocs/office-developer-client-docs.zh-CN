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
  
> [in， out]在输入时，指向包含属性标记数组 [的 SPropTagArray](sproptagarray.md) 结构的指针;否则为 NULL，指示应返回所有名称。 属性标记数组的 **cValues** 成员不能为 0。 如果  _lppPropTags_ 是输入上的有效指针 **，GetNamesFromIDs** 将返回数组中包含的每个属性标识符的名称。 
    
 _lpPropSetGuid_
  
> [in]指向标识属性集的 GUID 或 [GUID](guid.md) 结构的指针。 _lpPropSetGuid_ 参数可以指向有效的属性集，也可以为 NULL。 
    
 _ulFlags_
  
> [in]指示要返回的名称类型的标志的位掩码。 如果设置了这两个标志 (，则系统不会返回任何名称，) ：
    
MAPI_NO_IDS 
  
> 仅返回存储为 Unicode 字符串的名称的请求。 
    
MAPI_NO_STRINGS 
  
> 仅返回存储为数字标识符的名称的请求。 
    
 _lpcPropNames_
  
> [out]指向  _lppPropNames_ 参数指向的数组中的属性名称指针计数的指针。 
    
 _lpppPropNames_
  
> [out]指向指向包含属性名称 [的 MAPINAMEID](mapinameid.md) 结构的指针数组的指针。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 属性名称已成功返回。 
    
MAPI_E_NO_SUPPORT 
  
> 对象不支持命名属性。 
    
MAPI_W_ERRORS_RETURNED 
  
> 调用整体成功，但无法返回一个或多个属性的名称。 失败属性的属性标记的属性类型为 **PT_ERROR**。 返回此警告时，应成功处理呼叫。 若要测试此警告，请使用 **HR_FAILED** 宏。 有关详细信息，请参阅使用 [宏处理错误](using-macros-for-error-handling.md)。 
    
MAPI_E_INVALID_PARAMETER 
  
> _lppPropTags_ 指向的属性标记数组中一个或多个条目的 **cValues** 成员设置为 0。 
    
## <a name="remarks"></a>备注

虽然通过属性标识符访问大多数属性，但某些属性可以通过名称访问。 可以 **调用 IMAPIProp：：GetNamesFromIDs** 方法来执行以下操作： 
  
- 检索特定属性集内特定属性标识符的名称。
    
- 检索任何属性集内特定属性标识符的名称。
    
- 检索对象映射中包含的所有命名属性的名称。
    
如果  _lppPropTags_ 指向具有一个或多个属性标识符的有效属性标记数组，  _并且 lpPropSetGuid_ 指向有效的属性集，则 **GetNamesFromIDs** 将忽略属性集和属性类型，并返回映射到指定标识符的所有名称。 
  
如果  _lppPropTags_ 指向具有一个或多个属性标识符的有效属性标记数组，并且  _lpPropSetGuid_ 为 NULL， **则 GetNamesFromIDs** 将返回映射到指定标识符的所有名称。 
  
如果指定的标识符没有名称 **，GetNamesFromIDs** 将返回 NULL，该标识符的位置在  _lpppPropNames_ 中返回的结构中，并返回MAPI_W_ERRORS_RETURNED。 
  
如果  _lpPropSetGuid_ 和  _lppPropTags_ 都为 NULL， **则 GetNamesFromIDs** 将分配一个新的属性标记数组，并返回对象的所有命名属性的所有名称。 
  
如果没有要返回的名称，可能是因为请求的属性集没有属性，或者所有属性的类型都由标志排除 **，GetNamesFromIDs** 将执行以下操作： 
  
- 返回S_OK。
    
- 分配新的 **SPropTagArray** 结构，将 **cValues** 成员设置为 0。 
    
- 将  _lpcPropNames 的内容设置_ 为 0。 
    
- 将  _lpppPropNames 的内容设置_ 为 NULL。 
    
## <a name="notes-to-implementers"></a>针对实现者的说明

如果  _lpPropSetGuid_ 指向有效的属性集，  _而 lppPropTags_ 为 NULL，则结果为 undefined。 可以使用以下策略之一： 
  
- 忽略属性集并返回属性标记数组中标识符的名称。
    
- 仅返回属于指定属性集的属性标记数组中的标识符的名称。
    
- 呼叫失败，返回MAPI_E_INVALID_PARAMETER。 
    
## <a name="notes-to-callers"></a>给调用方的说明

若要检索对象的所有命名属性，必须先调用对象的 [IMAPIProp：：GetPropList](imapiprop-getproplist.md) 方法，然后将 0x8000 范围之上的返回标识符传递到 **GetNamesFromIDs**。
  
如果传递的有效属性集不是有效的属性标记数组，请为不可预知的结果做好准备。 **GetNamesFromIDs** 的一些实现将忽略属性集，并返回属性标记数组中标识符的名称。 某些实现返回MAPI_E_INVALID_PARAMETER。 其他实现返回属性集内所有属性的标识符的名称。 如果属性集已 **PS_PUBLIC_STRINGS，GetNamesFromIDs** 可以返回以前创建过的所有名称。 服务提供程序是否将属性存储在与公共字符串关联的标识符下并不重要。 
  
使用完属性名称后，请检查  _lpcPropNames_ 参数的内容以确定是否返回了任何名称。 如果是这样，请调用 [MAPIFreeBuffer](mapifreebuffer.md) 函数以在返回成功结果时释放  _lppPropTags_ 和  _lpppPropNames_ 指向的内存。 一次 **对 MAPIFreeBuffer** 的调用足以满足每个参数;你不需要遍历指针数组并单独释放每个 **MAPINAMEID** 结构。 
  
有关命名属性的信息，请参阅 [MAPI Named Properties](mapi-named-properties.md)。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|SingleMAPIPropListCtrl.cpp  <br/> |CSingleMAPIPropListCtrl：：FindAllNamedProps  <br/> |MFCMAPI 使用 **IMAPIProp：：GetNamesFromIDs** 方法来查找之前已映射的命名属性。  <br/> |
   
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
  
[使用宏处理错误](using-macros-for-error-handling.md)

