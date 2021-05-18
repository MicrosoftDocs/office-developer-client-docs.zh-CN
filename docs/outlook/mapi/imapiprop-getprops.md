---
title: IMAPIPropGetProps
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIProp.GetProps
api_type:
- COM
ms.assetid: 1c7a9cd2-d765-4218-9aee-52df1a2aae6c
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 9b03775d495f7d1f51142eb0ed06fc9ecdf6d1a3
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33412455"
---
# <a name="imapipropgetprops"></a>IMAPIProp::GetProps

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
检索对象的一个或多个属性的属性值。
  
```cpp
HRESULT GetProps(
  LPSPropTagArray lpPropTagArray,
  ULONG ulFlags,
  ULONG FAR * lpcValues,
  LPSPropValue FAR * lppPropArray
);
```

## <a name="parameters"></a>参数

 _lpPropTagArray_
  
> [in]指向属性标记数组的指针，用于标识要检索其值的属性。 _lpPropTagArray_ 参数必须为 NULL，指示应返回对象的所有属性的值，或指向包含一个或多个属性标记的 [SPropTagArray](sproptagarray.md)结构。 
    
 _ulFlags_
  
> [in]指示类型为 PT_UNSPECIFIED 的属性的格式的标志位掩码。 可以设置以下标志：
    
MAPI_UNICODE 
  
> 这些属性的字符串值应该以 Unicode 格式返回。 如果未MAPI_UNICODE，则应该以 ANSI 格式返回字符串值。
    
 _lpcValues_
  
> [out]指向  _lppPropArray_ 参数指向的属性值计数的指针。 如果  _lppPropArray_ 为 NULL，  _则 lpcValues 参数_ 的内容为零。 
    
 _lppPropArray_
  
> [out]指向指向检索的属性值的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功检索属性值。
    
MAPI_W_ERRORS_RETURNED 
  
> 调用整体成功，但无法访问一个或多个属性。 每个不可用属性的属性值的 **aulPropTag** 成员的属性类型为 PT_ERROR，标识符为零。 返回此警告时，应成功处理呼叫。 若要测试此警告，请使用 **HR_FAILED** 宏。 有关详细信息，请参阅使用 [宏处理错误](using-macros-for-error-handling.md)。
    
MAPI_E_INVALID_PARAMETER 
  
> 零在 _lpPropTagArray_ 指向 **的 SPropTagArray** 结构的 **cValues** 成员中传递。
    
## <a name="remarks"></a>备注

**IMAPIProp：：GetProps** 方法获取对象的一个或多个属性的属性值。 
  
属性值的返回顺序与请求的属性值相同 (也就是说  _，lpPropTagArray_ 指向的属性标记数组中的属性顺序与  _lppPropArray_) 指向的属性值结构数组中的顺序相匹配。 
  
属性标记数组的 **aulPropTag** 成员中指定的属性类型指示应在每个属性值结构的 **Value** 成员中返回的值的类型。 但是，如果调用方不知道属性的类型，可以改为将 **aulPropTag** 成员中的类型设置为 PT_UNSPECIFIED。 在检索值时 **，GetProps** 在属性值结构的 **aulPropTag** 成员中设置正确的类型。 
  
如果在 _lpPropTagArray_ 的 **SPropTagArray** 中指定了属性类型，则 _lppPropArray_ 中返回 **的 SPropValue** 中的属性值的类型与请求的类型完全匹配，除非改为返回错误值。 
  
字符串属性可以有两种属性类型之一：PT_UNICODE Unicode 格式，PT_STRING8表示 ANSI 格式。 如果在  _ulFlags_ 参数中设置了 MAPI_UNICODE 标志，则 **只要 GetProps** 无法确定字符串属性的适当格式，它就会以 Unicode 格式返回其值。 **在下列情况下，GetProps** 无法确定确切的字符串属性类型： 
  
- _lpPropTagArray_ 参数设置为 NULL 以请求所有属性。 
    
- **aulPropTag** 成员包括值PT_UNSPECIFIED属性标记数组中用作其属性类型的值。 
    
如果  _lpPropTagArray_ 参数设置为 NULL 以检索对象的所有属性，并且不存在属性， **则 GetProps** 将执行以下操作： 
  
- 返回S_OK。
    
- 将属性值结构的 **cValues** 成员中的计数值设置为 0。 
    
- 将  _lpcValues 的内容设置_ 为 0。 
    
- 将  _lppPropArray 设置_ 为 NULL。 
    
 **GetProps** 不得返回 **cValues** 设置为 0 的多个值属性。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

调用 [MAPIAllocateBuffer](mapiallocatebuffer.md)函数，最初为 _lpPropTagArray_ 指向的 [SPropValue](spropvalue.md)结构分配内存;调用 [MAPIAllocateMore](mapiallocatemore.md)以分配结构成员所需的任何其他内存。 
  
如果您MAPI_W_ERRORS_RETURNED一个或多个请求属性的值，则返回值。 在属性值结构中，将 **aulPropTag** 成员中的类型设置为 PT_ERROR **Value** 成员设置为描述错误的状态代码。 例如，如果必须将字符串转换为 Unicode 但不支持 Unicode，请将 **Value** 成员设置为 MAPI_E_BAD_CHARWIDTH。 如果属性太大，请设置为MAPI_E_NOT_ENOUGH_MEMORY。 如果对象不支持该属性，则设置为 MAPI_E_NOT_FOUND。 
  
远程传输提供程序的 **GetProps** 方法实现必须返回呼叫者请求的属性的文件夹属性值。 你的实现必须执行以下操作： 
  
- 分配一个属性值数组以返回到调用方，并存储其地址在为此目的传入的属性值指针参数中。
    
- 根据传递给 **GetProps** 的属性标记数组，将属性标记从文件夹的属性复制到属性值数组中的属性标记中。
    
- 确保为传递给 **GetProps** 的所有属性标记设置属性类型。 调用方可以传递属性类型的 PT_UNSPECIFIED，在这种情况下 **，GetProps** 必须为该属性标记设置正确的属性类型。 
    
- 根据属性值数组的标记设置每个属性的值。 例如，如果调用方请求的属性标记PR_OBJECT_TYPE ([PidTagObjectType](pidtagobjecttype-canonical-property.md)) ，**则 GetProps** 可以将该值设置为 MAPI_FOLDER。  
    
- 如果调用方传递您的实现未处理的任何属性标记，您可以将这些属性的属性标记设置为 PT_ERROR，将属性值设置为 MAPI_E_NOT_FOUND。
    
- 如果未S_OK错误，或返回MAPI_W_ERRORS_RETURNED错误时返回值。
    
远程传输提供程序的 **GetProps** 方法实现至少必须支持以下属性： 
  
- **PR_ACCESS (** [PidTagAccess)](pidtagaccess-canonical-property.md)
    
- **PR_ACCESS_LEVEL (** [PidTagAccessLevel](pidtagaccesslevel-canonical-property.md)) 
    
- **PR_ASSOC_CONTENT_COUNT (** [PidTagAssociatedContentCount](pidtagassociatedcontentcount-canonical-property.md)) 
    
- **PR_CONTENT_COUNT (** [PidTagContentCount](pidtagcontentcount-canonical-property.md)) 
    
- **PR_CREATION_TIME (** [PidTagCreationTime](pidtagcreationtime-canonical-property.md)) 
    
- **PR_DISPLAY_NAME (** [PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 
    
- **PR_DISPLAY_TYPE (** [PidTagDisplayType](pidtagdisplaytype-canonical-property.md)) 
    
- **PR_FOLDER_TYPE (** [PidTagFolderType)](pidtagfoldertype-canonical-property.md)
    
- **PR_OBJECT_TYPE**
    
- **PR_SUBFOLDERS (** [PidTagSubfolders](pidtagsubfolders-canonical-property.md)) 
    
## <a name="notes-to-callers"></a>给调用方的说明

对于类型为 PT_OBJECT，请调用 [IMAPIProp：：OpenProperty](imapiprop-openproperty.md) 方法，而不是 **GetProps**。 
  
对于安全属性，不要期望通过调用 _lppPropTagArray_ 参数设置为 NULL 的 **GetProps** 来检索它们。 调用 GetProps 时，必须在其属性标记数组的 **aulPropTag** 成员中显式设置 **安全属性的标识符**。 何时以及如何提供安全属性由服务提供商决定。 
  
仅在 **GetProps** 返回 S_OK 或 MAPI_W_ERRORS_RETURNED 时，通过调用 [MAPIFreeBuffer](mapifreebuffer.md)函数释放返回的 **SPropValue** MAPI_W_ERRORS_RETURNED。 
  
如果 **GetProps** 返回MAPI_W_ERRORS_RETURNED，因为它无法访问一个或多个属性，请检查返回的属性的属性标记。 失败的属性将在属性值结构中设置以下值： 
  
- **aulPropTag** 中的属性成员集PT_ERROR。 
    
- **Value** 中的属性值成员集错误的状态代码，如MAPI_E_NOT_FOUND。 
    
由于过大而失败的属性无法方便地在属性值结构中返回，因此其 **Value** 成员集MAPI_E_NOT_ENOUGH_MEMORY。 通常，当属性值为 4 KB 或更大时，PT_STRING8、PT_UNICODE 或 PT_BINARY 类型的字符串或二进制属性会出现此情况。 调用 **IMAPIProp：：OpenProperty** 以检索大型属性。 
  
并非所有 **GetProps** 实现都支持字符串的 Unicode 和 ANSI 格式。 当特定属性需要字符串格式转换而 **GetProps** 不支持它时，该属性的 **Value** 成员将设置为 MAPI_E_BAD_CHARWIDTH。 
  
若要检查 PST 是否SharePoint PST，使用 [IMAPISession：：OpenMsgStore](imapisession-openmsgstore.md)装载 PST，然后对请求此属性的邮件存储对象调用 **GetProps。** 如果存在，您可以假定 PST 已配置为用于SharePoint;如果没有，则 PST 尚未配置为 pst SharePoint PST。 
  
有关如何使用 **GetProps** 访问属性的信息，请参阅 [检索 MAPI 属性](retrieving-mapi-properties.md)。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MAPIFunctions.cpp  <br/> |GetPropsNULL  <br/> |MFCMAPI 使用 **IMAPIProp：：GetProps** 方法获取对象的所有属性，方法是在 _lpPropTagArray_ 参数中传递 NULL 或 [IMAPIProp：：GetPropList](imapiprop-getproplist.md)方法返回的数组。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIProp::GetPropList](imapiprop-getproplist.md)
  
[IMAPIProp::OpenProperty](imapiprop-openproperty.md)
  
[MAPIAllocateBuffer](mapiallocatebuffer.md)
  
[MAPIAllocateMore](mapiallocatemore.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)
  
[SPropTagArray](sproptagarray.md)
  
[SPropValue](spropvalue.md)
  
[IMAPIProp : IUnknown](imapipropiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)
  
[检索 MAPI 属性](retrieving-mapi-properties.md)
  
[使用宏处理错误](using-macros-for-error-handling.md)

