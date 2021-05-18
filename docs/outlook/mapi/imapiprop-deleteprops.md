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
  
> [in]指向指示要删除的属性的属性标记数组的指针。 _lpPropTagArray_ 指向 [的 SPropTagArray](sproptagarray.md)结构的 **cValues** 成员不能为零，并且 _lpPropTagArray_ 参数本身不能为 NULL。 
    
 _lppProblems_
  
> [in， out]在输入时，指向指向 [SPropProblemArray 结构的指针的](spropproblemarray.md) 指针;否则为 NULL，这表示不需要错误信息。 如果  _lppProblems_ 是输入的有效指针 **，DeleteProps** 将返回有关删除一个或多个属性时错误的详细信息。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 属性已成功删除。
    
MAPI_E_NO_ACCESS 
  
> 调用方没有足够的权限来删除属性。
    
## <a name="remarks"></a>备注

**IMAPIProp：:D eleteProps** 方法从当前对象中删除一个或多个属性。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

不需要允许从所有对象中删除属性。 如果对象不可修改，则从 **DeleteProps** MAPI_E_NO_ACCESS返回值。 
  
## <a name="notes-to-callers"></a>给调用方的说明

在  _lpPropTagArray_ 参数指向的属性标记数组中，不需要设置每个属性标记的属性类型。 忽略属性类型;仅使用属性标识符。 
  
请注意，某些对象不允许修改，并且这些对象从 **DeleteProps** MAPI_E_NO_ACCESS返回值。 其他对象允许删除某些属性，但不允许删除其他属性。 如果仅删除某些属性时出现问题 **，DeleteProps** 将返回S_OK。 如果在  _lppProblems_ 参数中传递了一个有效的指针 **，DeleteProps** 将设置指向 **SPropProblemArray** 结构的指针，其中包含有关每个属性的问题的详细信息。 例如，如果要删除邮件的所有属性，并且其一个或多个附件出现问题， **则 SPropProblemArray** 结构将包含 **PR_MESSAGE_ATTACHMENTS** ([PidTagMessageAttachments](pidtagmessageattachments-canonical-property.md)) 属性的条目。 
  
_lppProblems_ 指向的结构仅在 **DeleteProps** 返回值时S_OK。 如果 **DeleteProps** 返回错误，请不要尝试使用 **SPropProblemArray** 结构。 相反，请调用对象的 [IMAPIProp：：GetLastError](imapiprop-getlasterror.md) 方法来获取有关错误的详细信息。 
  
通过调用 [MAPIFreeBuffer](mapifreebuffer.md)函数释放返回的 **SPropProblemArray** 结构。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MAPIFunctions.cpp  <br/> |DeleteProperty  <br/> |MFCMAPI 使用 **IMAPIProp：:D eleteProps** 方法从对象中删除属性。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIProp::GetLastError](imapiprop-getlasterror.md)
  
[IMAPIProp::GetProps](imapiprop-getprops.md)
  
[IMAPIProp::SaveChanges](imapiprop-savechanges.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)
  
[SPropProblemArray](spropproblemarray.md)
  
[SPropTagArray](sproptagarray.md)
  
[IMAPIProp : IUnknown](imapipropiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

