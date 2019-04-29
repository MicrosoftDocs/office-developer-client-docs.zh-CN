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
  
> 实时指向标识要检索其值的属性的属性标记数组的指针。 _lpPropTagArray_参数必须是 NULL, 指示应返回对象的所有属性的值, 或指向包含一个或多个属性标记的[SPropTagArray](sproptagarray.md)结构。 
    
 _ulFlags_
  
> 实时标志的位掩码, 指示属性类型为 PT_UNSPECIFIED 的格式。 可以设置以下标志:
    
MAPI_UNICODE 
  
> 这些属性的字符串值应以 Unicode 格式返回。 如果未设置 MAPI_UNICODE 标志, 则字符串值应以 ANSI 格式返回。
    
 _lpcValues_
  
> 排除一个指针, 指向_lppPropArray_参数指向的属性值的计数。 如果_lppPropArray_为 NULL, 则_lpcValues_参数的内容为零。 
    
 _lppPropArray_
  
> 排除指向已检索的属性值的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功检索属性值。
    
MAPI_W_ERRORS_RETURNED 
  
> 呼叫全部成功, 但无法访问一个或多个属性。 每个不可用属性的属性值的**aulPropTag**成员的属性类型为 PT_ERROR, 标识符为零。 返回此警告时, 应以成功的方式处理该调用。 若要测试此警告, 请使用**HR_FAILED**宏。 有关详细信息, 请参阅[使用宏进行错误处理](using-macros-for-error-handling.md)。
    
MAPI_E_INVALID_PARAMETER 
  
> 在_lpPropTagArray_指向的**SPropTagArray**结构的**cValues**成员中传递了零。
    
## <a name="remarks"></a>说明

**IMAPIProp:: GetProps**方法获取对象的一个或多个属性的属性值。 
  
属性值按其请求的顺序返回 (即, 由_lpPropTagArray_指向的属性标记数组中属性的顺序与 lppPropArray 指向的属性值结构数组中的顺序匹配)。 __). 
  
在属性标记数组的**aulPropTag**成员中指定的属性类型指示应在每个属性值结构的**value**成员中返回的值的类型。 但是, 如果调用方不知道属性的类型, 则可以改为将**aulPropTag**成员中的类型设置为 PT_UNSPECIFIED。 在检索值时, **GetProps**会在属性的属性值结构的**aulPropTag**成员中设置正确的类型。 
  
如果在_lpPropTagArray_中的**SPropTagArray**中指定了属性类型, 则在_lppPropArray_中返回的**SPropValue**中的属性值的类型与请求的类型完全匹配, 除非返回错误值应当. 
  
字符串属性可以具有以下两种属性类型之一: PT_UNICODE 表示 UNICODE 格式和 PT_STRING8 来表示 ANSI 格式。 如果在_ulFlags_参数中设置了 MAPI_UNICODE 标志, 则只要**GetProps**无法确定字符串属性的相应格式, 它将以 UNICODE 格式返回其值。 在以下情况下, **GetProps**无法确定确切的字符串属性类型: 
  
- 将_lpPropTagArray_参数设置为 NULL 以请求所有属性。 
    
- **aulPropTag**成员将值 PT_UNSPECIFIED 作为其属性类型包含在属性标记数组中。 
    
如果将_lpPropTagArray_参数设置为 NULL 以检索对象的所有属性, 并且不存在任何属性, 则**GetProps**将执行以下操作: 
  
- 返回 S_OK。
    
- 将属性值结构的**cValues**成员中的 count 值设置为0。 
    
- 将_lpcValues_的内容设置为0。 
    
- 将_lppPropArray_设置为 NULL。 
    
 **GetProps**不能返回将**cValues**设置为0的多值属性。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

调用[MAPIAllocateBuffer](mapiallocatebuffer.md)函数, 以在_lpPropTagArray_指向的[SPropValue](spropvalue.md)结构中最初分配内存;调用[MAPIAllocateMore](mapiallocatemore.md)以分配结构成员所需的任何额外内存。 
  
如果无法检索一个或多个请求的属性的值, 则返回 MAPI_W_ERRORS_RETURNED。 在属性值结构中, 将**aulPropTag**成员中的 "类型" 设置为 "PT_ERROR", 并将 "**值**" 成员设置为描述错误的状态代码。 例如, 如果您必须将字符串转换为 unicode 且不支持 unicode, 请将**Value**成员设置为 MAPI_E_BAD_CHARWIDTH。 如果属性太大, 请将其设置为 MAPI_E_NOT_ENOUGH_MEMORY。 如果该对象不支持该属性, 请将其设置为 MAPI_E_NOT_FOUND。 
  
远程传输提供程序的**GetProps**方法的实现必须为调用方请求的属性返回文件夹的属性值。 您的实现必须执行以下操作: 
  
- 分配一个属性值数组以返回到调用方, 并将其地址存储在为该目的而传入的属性值指针参数中。
    
- 根据传递给**GetProps**的属性标记数组, 将文件夹属性中的属性标记复制到属性值数组中的属性标记中。
    
- 确保为传递到**GetProps**的所有属性标记设置了属性类型。 调用方可以传入 PT_UNSPECIFIED 的属性类型, 在这种情况下, **GetProps**必须为该属性标记设置正确的属性类型。 
    
- 根据其标记设置属性值数组中每个属性的值。 例如, 如果调用方请求的属性标记是**PR_OBJECT_TYPE** ([PidTagObjectType](pidtagobjecttype-canonical-property.md)), 则**GetProps**可以将该值设置为 MAPI_FOLDER。 
    
- 如果调用方传递到您的实现未处理的任何属性标记中, 则可以为这些属性将属性标记设置为 PT_ERROR, 并将属性值设置为 MAPI_E_NOT_FOUND。
    
- 如果没有错误发生, 则返回 S_OK; 如果有错误, 则返回 MAPI_W_ERRORS_RETURNED。
    
远程传输提供程序的**GetProps**方法实现必须至少支持以下属性: 
  
- **PR_ACCESS**([PidTagAccess](pidtagaccess-canonical-property.md))
    
- **PR_ACCESS_LEVEL**([PidTagAccessLevel](pidtagaccesslevel-canonical-property.md))
    
- **PR_ASSOC_CONTENT_COUNT**([PidTagAssociatedContentCount](pidtagassociatedcontentcount-canonical-property.md))
    
- **PR_CONTENT_COUNT**([PidTagContentCount](pidtagcontentcount-canonical-property.md))
    
- **PR_CREATION_TIME**([PidTagCreationTime](pidtagcreationtime-canonical-property.md))
    
- **PR_DISPLAY_NAME**([PidTagDisplayName](pidtagdisplayname-canonical-property.md))
    
- **PR_DISPLAY_TYPE**([PidTagDisplayType](pidtagdisplaytype-canonical-property.md))
    
- **PR_FOLDER_TYPE**([PidTagFolderType](pidtagfoldertype-canonical-property.md))
    
- **PR_OBJECT_TYPE**
    
- **PR_SUBFOLDERS**([PidTagSubfolders](pidtagsubfolders-canonical-property.md))
    
## <a name="notes-to-callers"></a>给调用方的说明

对于类型为 PT_OBJECT 的属性, 请调用[IMAPIProp:: OpenProperty](imapiprop-openproperty.md)方法, 而不是**GetProps**。 
  
对于安全属性, 不希望通过调用**GetProps**并将_lppPropTagArray_参数设置为 NULL 来检索这些属性。 调用**GetProps**时, 您必须在其属性标记数组的**aulPropTag**成员中显式设置安全属性的标识符。 安全属性可用的时间和方式由服务提供商负责。 
  
仅在**GetProps**返回 S_OK 或 MAPI_W_ERRORS_RETURNED 时调用[MAPIFreeBuffer](mapifreebuffer.md)函数, 从而释放返回的**SPropValue**结构。 
  
如果**GetProps**返回 MAPI_W_ERRORS_RETURNED, 因为它无法访问一个或多个属性, 请检查返回的属性的属性标记。 失败的属性将在其属性值结构中设置以下值: 
  
- **aulPropTag**成员集中的属性类型设置为 PT_ERROR。 
    
- **value**成员中的属性值设置为错误的状态代码, 如 MAPI_E_NOT_FOUND。 
    
由于在属性值结构中太大而无法轻松地返回的属性的**value**成员设置为 MAPI_E_NOT_ENOUGH_MEMORY, 因此这些属性会失败。 通常情况下, 当属性的值为 4 KB 或更大时, PT_STRING8、PT_UNICODE 或 PT_BINARY 类型的字符串或二进制属性会发生此情况。 调用**IMAPIProp:: OpenProperty**以检索大型属性。 
  
并非**GetProps**的所有实现都支持字符串的 Unicode 和 ANSI 格式。 当某个特定属性需要字符串格式转换且**GetProps**无法支持该属性时, 该属性的**值**成员将设置为 MAPI_E_BAD_CHARWIDTH。 
  
若要检查 pst 是否为 SharePoint pst, 请使用[IMAPISession:: OpenMsgStore](imapisession-openmsgstore.md)装入 pst, 然后对请求该属性的邮件存储对象调用**GetProps** 。 如果存在, 则可以假定已为 SharePoint 配置了 PST;如果不是, 则 PST 尚未配置为 SharePoint pst。 
  
有关如何使用**GetProps**访问属性的详细信息, 请参阅[检索 MAPI 属性](retrieving-mapi-properties.md)。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MAPIFunctions  <br/> |GetPropsNULL  <br/> |MFCMAPI 使用**IMAPIProp:: GetProps**方法获取对象的所有属性, 方法是在_GetPropList_参数中传递的[IMAPIProp:: lpPropTagArray](imapiprop-getproplist.md)方法返回的 NULL 或数组。  <br/> |
   
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
  
[使用宏进行错误处理](using-macros-for-error-handling.md)

