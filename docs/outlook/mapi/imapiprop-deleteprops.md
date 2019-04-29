---
title: IMAPIPropDeleteProps
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIProp.DeleteProps
api_type:
- COM
ms.assetid: 5cc642de-21f0-4826-bf21-aac4bcfc1328
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 5bfef87baa2dffa4605f9a7afa3833024f514430
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33409235"
---
# <a name="imapipropdeleteprops"></a>IMAPIProp::DeleteProps

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
从对象中删除一个或多个属性。 
  
```cpp
HRESULT DeleteProps(
  LPSPropTagArray lpPropTagArray,
  LPSPropProblemArray FAR * lppProblems
);
```

## <a name="parameters"></a>参数

 _lpPropTagArray_
  
> 实时指向指明要删除的属性的属性标记数组的指针。 由_lpPropTagArray_指向的[SPropTagArray](sproptagarray.md)结构的**cValues**成员不得为零, 并且_lpPropTagArray_参数本身不能为 NULL。 
    
 _lppProblems_
  
> [in, out]在输入时, 指向指向[SPropProblemArray](spropproblemarray.md)结构的指针的指针;否则为 NULL, 表示无需提供错误信息。 如果_lppProblems_是有效的输入指针, **DeleteProps**将返回有关删除一个或多个属性中的错误的详细信息。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功删除属性。
    
MAPI_E_NO_ACCESS 
  
> 调用方权限不足, 无法删除属性。
    
## <a name="remarks"></a>说明

**IMAPIProp::D eleteprops**方法从当前对象中删除一个或多个属性。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

您无需允许从所有对象中删除属性。 如果对象是不可修改的, 请从**DeleteProps**方法返回 MAPI_E_NO_ACCESS。 
  
## <a name="notes-to-callers"></a>给调用方的说明

您不必为由_lpPropTagArray_参数指向的属性标记数组中的每个属性标记设置属性类型。 忽略属性类型;仅使用属性标识符。 
  
请注意, 某些对象不允许进行修改, 并且这些对象从**DeleteProps**方法返回 MAPI_E_NO_ACCESS。 其他对象允许删除某些属性, 但不允许删除其他属性。 如果删除某些属性时出现问题, **DeleteProps**将返回 S_OK。 如果您在_lppProblems_参数中传递了一个有效的指针, 则**DeleteProps**会将指针设置为包含有关每个属性的问题的详细信息的**SPropProblemArray**结构。 例如, 如果您要删除邮件的所有属性, 并且其中一个或多个附件存在问题, 则**SPropProblemArray**结构将包含**PR_MESSAGE_ATTACHMENTS**的一个条目 ([PidTagMessageAttachments](pidtagmessageattachments-canonical-property.md)) 属性。 
  
_lppProblems_所指向的结构仅当**DeleteProps**返回 S_OK 时才有效。 如果**DeleteProps**返回错误, 则不要尝试使用**SPropProblemArray**结构。 相反, 请调用对象的[IMAPIProp:: GetLastError](imapiprop-getlasterror.md)方法以获取有关错误的详细信息。 
  
通过调用[MAPIFreeBuffer](mapifreebuffer.md)函数释放返回的**SPropProblemArray**结构。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MAPIFunctions  <br/> |DeleteProperty  <br/> |MFCMAPI 使用**IMAPIProp::D eleteprops**方法从对象中删除属性。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIProp::GetLastError](imapiprop-getlasterror.md)
  
[IMAPIProp::GetProps](imapiprop-getprops.md)
  
[IMAPIProp::SaveChanges](imapiprop-savechanges.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)
  
[SPropProblemArray](spropproblemarray.md)
  
[SPropTagArray](sproptagarray.md)
  
[IMAPIProp : IUnknown](imapipropiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

