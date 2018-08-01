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
ms.openlocfilehash: 33351235db2a9a3f9d9b67f59e8356a0fa8abfa8
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775525"
---
# <a name="imapipropgetprops"></a>IMAPIProp::GetProps

  
  
**适用于**： Outlook 
  
检索一个或多个对象的属性的属性值。
  
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
  
> [in]一个指向数组属性标记来标识要检索其值的属性。 _LpPropTagArray_参数必须为或者是 NULL，表明对象的所有属性的值应返回，或指向[SPropTagArray](sproptagarray.md)结构，其中包含一个或多个属性标记。 
    
 _ulFlags_
  
> [in]位掩码的标志，指示具有 PT_UNSPECIFIED 类型的属性的格式。 可以设置以下标记：
    
MAPI_UNICODE 
  
> 这些属性的字符串值应为 Unicode 格式返回。 如果未设置 MAPI_UNICODE 标志，应以 ANSI 格式返回的字符串值。
    
 _lpcValues_
  
> [输出]一个指向_lppPropArray_参数指向的属性值的计数。 如果_lppPropArray_为 NULL，则_lpcValues_参数的内容为零。 
    
 _lppPropArray_
  
> [输出]指向检索的属性值的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功检索属性值。
    
MAPI_W_ERRORS_RETURNED 
  
> 调用成功总体上讲，但无法访问一个或多个属性。 不可用的每个属性的属性值的**aulPropTag**成员具有 PT_ERROR 和零的标识符的属性类型。 返回此警告时，应处理呼叫为成功。 若要测试此警告，请使用**HR_FAILED**宏。 有关详细信息，请参阅[使用宏的错误处理](using-macros-for-error-handling.md)。
    
MAPI_E_INVALID_PARAMETER 
  
> 在所指的_lpPropTagArray_ **SPropTagArray**结构的**cValues**成员传递零。
    
## <a name="remarks"></a>说明

**IMAPIProp::GetProps**方法获取对象的一个或多个属性的属性值。 
  
他们已请求将返回相同的顺序的属性值 （即，该属性标记数组中的属性的顺序所指的_lpPropTagArray_匹配项的属性值结构所指的_lppPropArray 数组中的顺序_). 
  
属性标记数组的**aulPropTag**成员中指定的属性类型指示应在每个属性值结构的**值**成员中返回的值的类型。 但是，如果呼叫者不知道属性的类型，在**aulPropTag**成员类型可以改为设置到 PT_UNSPECIFIED。 在检索值， **GetProps**属性的属性值结构的**aulPropTag**成员中设置正确的类型。 
  
如果**SPropTagArray**中_lpPropTagArray_中指定属性类型中**SPropValue** _lppPropArray_中返回, 的属性值将具有完全匹配的请求的类型的类型，除非返回错误值而是。 
  
字符串属性可以有两种属性类型之一： PT_UNICODE 表示 Unicode 格式和 PT_STRING8 来代表 ANSI 格式。 如果 MAPI_UNICODE 标记中设置_ulFlags_参数，只要**GetProps**无法确定适当的格式为字符串属性，则它将返回其值为 Unicode 格式。 **GetProps**无法确定在下列情况下的准确字符串属性类型： 
  
- _LpPropTagArray_参数设置为 NULL，请求的所有属性。 
    
- **AulPropTag**成员作为其属性类型属性标记数组中包含的值 PT_UNSPECIFIED。 
    
如果_lpPropTagArray_参数设置为 NULL，若要检索所有对象的属性，并且不存在任何属性， **GetProps**执行以下任务： 
  
- 返回 S_OK。
    
- 将数值设置为 0 的属性值结构的**cValues**成员中。 
    
- 将_lpcValues_的内容设置为 0。 
    
- 将_lppPropArray_设置为 NULL。 
    
 不能**GetProps**返回**cValues**多值属性设置为 0。 
  
## <a name="notes-to-implementers"></a>针对实施者的注释

调用[MAPIAllocateBuffer](mapiallocatebuffer.md)函数所指的_lpPropTagArray_; [SPropValue](spropvalue.md)结构最初分配内存调用[MAPIAllocateMore](mapiallocatemore.md)分配所需的结构的成员的任何其他内存。 
  
如果您无法检索一个或多个请求属性的值，则返回 MAPI_W_ERRORS_RETURNED。 在属性值结构中，设置为 PT_ERROR **aulPropTag**成员和描述错误状态代码**值**成员中的类型。 例如，如果已将字符串转换为 Unicode，并且不支持 Unicode，则可设置为 MAPI_E_BAD_CHARWIDTH**值**成员。 如果该属性是太大，则将其设置为 MAPI_E_NOT_ENOUGH_MEMORY。 如果对象不支持属性，则将其设置为 MAPI_E_NOT_FOUND。 
  
远程传输提供程序的方法的实现， **GetProps**必须返回请求的呼叫者的属性的文件夹的属性值。 实现必须执行以下操作： 
  
- 分配属性值数组返回到呼叫者，并将其地址存储在属性值指针参数中传递为实现此目的。
    
- 将从该文件夹的属性的属性标记复制到数组传递给**GetProps**属性标记根据属性值数组中的属性标记中。
    
- 确保属性类型为传递给**GetProps**的所有属性标记。 呼叫者可以传递的 PT_UNSPECIFIED，案例**GetProps**必须设置该属性标记的正确的属性类型的属性类型。 
    
- 设置属性值数组根据其标记中的每个属性的值。 例如，如果呼叫者请求的属性标记为**PR_OBJECT_TYPE** ([PidTagObjectType](pidtagobjecttype-canonical-property.md))， **GetProps**可以将值设置为 MAPI_FOLDER。 
    
- 如果呼叫者通过在您的实现并不处理任何属性标记中，可以设置该属性标记为 PT_ERROR 这些属性，并将该属性值设置为 MAPI_E_NOT_FOUND。
    
- 如果出现错误，则返回 S_OK 如果不出现任何错误或 MAPI_W_ERRORS_RETURNED。
    
远程传输提供程序的方法的实现， **GetProps**必须支持最少的以下属性： 
  
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

对于类型 PT_OBJECT 的属性，则调用而不是**GetProps** [IMAPIProp::OpenProperty](imapiprop-openproperty.md)方法。 
  
对于安全属性，不希望检索其调用**GetProps**不带_lppPropTagArray_参数设置为 NULL。 调用**GetProps**时，您必须显式设置其属性标记数组的**aulPropTag**成员中安全属性的标识符。 何时以及如何安全属性是可由服务提供商。 
  
通过**GetProps**返回 S_OK 或 MAPI_W_ERRORS_RETURNED 时，才调用[MAPIFreeBuffer](mapifreebuffer.md)函数释放返回的**SPropValue**结构。 
  
如果**GetProps**返回 MAPI_W_ERRORS_RETURNED，因为它无法访问一个或多个属性，则检查属性标记返回的属性。 失败的属性将具有设置其属性值结构中的以下值： 
  
- 在设置为 PT_ERROR **aulPropTag**成员属性类型。 
    
- **值**成员中的属性值设置为错误，例如 MAPI_E_NOT_FOUND 状态代码。 
    
失败，因为它们是太大，以方便地返回属性值结构中的属性已设置为 MAPI_E_NOT_ENOUGH_MEMORY 其**值**成员。 通常，这时发生类型的字符串或二进制属性与 PT_STRING8、 PT_UNICODE 或 PT_BINARY 属性的值为 4 KB 或更大。 调用**IMAPIProp::OpenProperty**检索大型属性。 
  
并非所有的**GetProps**实现支持的字符的字符串的 Unicode 和 ANSI 格式。 当特定属性需要字符串格式转换和**GetProps**无法支持它时，属性**值**成员设置为 MAPI_E_BAD_CHARWIDTH。 
  
若要检查 PST 是否 SharePoint PST，装入 PST 使用[IMAPISession::OpenMsgStore](imapisession-openmsgstore.md)，然后调用**GetProps**上请求此属性的消息存储对象。 如果存在，您可以假定 PST 已配置的 SharePoint;如果没有，作为 SharePoint PST 尚未配置太平洋标准时间。 
  
有关如何使用**GetProps**访问属性的详细信息，请参阅[检索 MAPI 属性](retrieving-mapi-properties.md)。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|MAPIFunctions.cpp  <br/> |GetPropsNULL  <br/> |MFCMAPI 使用**IMAPIProp::GetProps**方法通过传递 NULL 或_lpPropTagArray_参数中的[IMAPIProp::GetPropList](imapiprop-getproplist.md)方法返回的数组获取对象的所有属性。  <br/> |
   
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

