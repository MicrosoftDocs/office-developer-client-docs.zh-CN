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
ms.openlocfilehash: 8eb19f9a2d3458e153b0758b56c502ce612be0cc
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775536"
---
# <a name="imapipropdeleteprops"></a>IMAPIProp::DeleteProps

  
  
**适用于**： Outlook 
  
从对象中删除一个或多个属性。 
  
```cpp
HRESULT DeleteProps(
  LPSPropTagArray lpPropTagArray,
  LPSPropProblemArray FAR * lppProblems
);
```

## <a name="parameters"></a>参数

 _lpPropTagArray_
  
> [in]一个指向数组属性标记，指示要删除的属性。 指向_lpPropTagArray_ [SPropTagArray](sproptagarray.md)结构的**cValues**成员必须不为零，和_lpPropTagArray_参数本身不能为 NULL。 
    
 _lppProblems_
  
> [传入、 传出]在输入时，为[SPropProblemArray](spropproblemarray.md)结构; 指针的指针否则，为 NULL，指示存在错误信息不需要。 如果_lppProblems_上输入, 的有效指针**DeleteProps**将返回错误的详细的信息中删除一个或多个属性。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功删除属性。
    
MAPI_E_NO_ACCESS 
  
> 呼叫者具有权限不足，无法删除属性。
    
## <a name="remarks"></a>说明

**IMAPIProp::DeleteProps**方法删除当前对象的一个或多个属性。 
  
## <a name="notes-to-implementers"></a>针对实施者的注释

不需要允许从所有对象中删除的属性。 如果对象不是可修改， **DeleteProps**方法返回 MAPI_E_NO_ACCESS。 
  
## <a name="notes-to-callers"></a>给调用方的说明

您不必设置_lpPropTagArray_参数指向该属性标记数组中的每个属性标记的属性类型。 属性类型将被忽略;使用仅属性的标识符。 
  
请注意，某些对象不允许修改，这些对象从**DeleteProps**方法返回 MAPI_E_NO_ACCESS。 允许其他对象的某些属性被删除，但不是其他人。 当没有问题删除只将某些属性时， **DeleteProps** ，则返回 S_OK。 如果您具有_lppProblems_参数中传递有效的指针， **DeleteProps**将设置为**SPropProblemArray**结构，其中包含与每个属性的问题的详细的信息的指针。 例如，如果您要删除的所有邮件的属性，并且有一个或多个附件的问题， **SPropProblemArray**结构将包含的条目的**PR_MESSAGE_ATTACHMENTS** ([PidTagMessageAttachments](pidtagmessageattachments-canonical-property.md)) 属性。 
  
指向_lppProblems_结构才有效**DeleteProps** ，则返回 S_OK。 如果**DeleteProps**将返回错误，不尝试使用**SPropProblemArray**结构。 相反，调用对象的[IMAPIProp::GetLastError](imapiprop-getlasterror.md)方法以获取有关错误的详细信息。 
  
通过调用[MAPIFreeBuffer](mapifreebuffer.md)函数释放返回的**SPropProblemArray**结构。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|MAPIFunctions.cpp  <br/> |DeleteProperty  <br/> |MFCMAPI 使用**IMAPIProp::DeleteProps**方法从对象中删除属性。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIProp::GetLastError](imapiprop-getlasterror.md)
  
[IMAPIProp::GetProps](imapiprop-getprops.md)
  
[IMAPIProp::SaveChanges](imapiprop-savechanges.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)
  
[SPropProblemArray](spropproblemarray.md)
  
[SPropTagArray](sproptagarray.md)
  
[IMAPIProp : IUnknown](imapipropiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

