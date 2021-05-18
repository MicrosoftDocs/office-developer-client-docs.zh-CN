---
title: IMAPIFormContainerResolveMultipleMessageClasses
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIFormContainer.ResolveMultipleMessageCla
api_type:
- COM
ms.assetid: f18c2dd1-366f-48b4-b335-ebbc0651f467
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 0730da9c3877985853e2cd0a55420e64fbd98e0c
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33412539"
---
# <a name="imapiformcontainerresolvemultiplemessageclasses"></a>IMAPIFormContainer::ResolveMultipleMessageClasses

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
将一组邮件类解析为表单容器中的窗体，并返回这些表单的表单信息对象的数组。
  
```cpp
HRESULT ResolveMultipleMessageClasses(
  LPSMESSAGECLASSARRAY pMsgClassArray,
  ULONG ulFlags,
  LPSMAPIFORMINFOARRAY FAR * ppfrminfoarray
);
```

## <a name="parameters"></a>参数

 _pMsgClassArray_
  
> [in]指向包含要解析的邮件类的名称的数组的指针。 邮件类名称始终是 ANSI 字符串，从不为 Unicode。
    
 _ulFlags_
  
> [in]控制邮件类解析方式的标志的位掩码。 可以设置以下标志：
    
MAPIFORM_EXACTMATCH 
  
> 仅应解析完全匹配的邮件类字符串。
    
 _ppfrminfoarray_
  
> [out]指向指向表单信息对象数组的指针的指针。 如果客户端应用程序在  _pMsgClassArray_ 参数中传递 NULL，  _则 ppfrminfoarray_ 参数包含容器中所有表单的表单信息对象。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功并返回了预期值。
    
## <a name="remarks"></a>备注

客户端应用程序调用 **IMAPIFormContainer：：ResolveMultipleMessageClasses** 方法，将一组邮件类解析为表单容器中的表单。 _ppfrminfoarray_ 参数中返回的表单信息对象数组提供对表单的每个属性的进一步访问。 
  
## <a name="notes-to-callers"></a>给调用方的说明

若要将一组邮件类解析为窗体，请传递要解析的邮件类名称数组。 若要强制使解析准确 (即，若要阻止解析到邮件类) 的基类，可以在  _ulFlags_ 参数中传递 MAPIFORM_EXACTMATCH 标志。 
  
如果无法将邮件类解析为窗体，将在窗体信息数组中为邮件类返回 NULL。 因此，即使该方法返回 S_OK，也不要假定已成功解析所有邮件类。 相反，请检查返回的数组中的值。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|FormContainerDlg.cpp  <br/> |CFormContainerDlg：：OnResolveMultipleMessageClasses  <br/> |MFCMAPI 使用 **IMAPIFormContainer：：ResolveMultipleMessageClasses** 方法来查找与一组邮件类关联的表单。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIFormContainer::ResolveMessageClass](imapiformcontainer-resolvemessageclass.md)
  
[IMAPIFormContainer : IUnknown](imapiformcontaineriunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

