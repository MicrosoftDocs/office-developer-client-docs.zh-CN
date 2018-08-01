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
ms.openlocfilehash: c1da292943d6e4d9625c6ce37019c630471e200b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775403"
---
# <a name="imapiformcontainerresolvemultiplemessageclasses"></a>IMAPIFormContainer::ResolveMultipleMessageClasses

  
  
**适用于**： Outlook 
  
解析为其在窗体容器中的窗体的邮件类的一组，并返回这些表单的信息对象的窗体的数组。
  
```cpp
HRESULT ResolveMultipleMessageClasses(
  LPSMESSAGECLASSARRAY pMsgClassArray,
  ULONG ulFlags,
  LPSMAPIFORMINFOARRAY FAR * ppfrminfoarray
);
```

## <a name="parameters"></a>参数

 _pMsgClassArray_
  
> [in]一个指向数组，其中包含的邮件类来解析名称。 邮件类名称始终都是 ANSI 字符串，从不 Unicode。
    
 _ulFlags_
  
> [in]位掩码的标志的控制解析的邮件类的方式。 可以设置以下标记：
    
MAPIFORM_EXACTMATCH 
  
> 应解决仅邮件类的字符串完全匹配。
    
 _ppfrminfoarray_
  
> [输出]指向为数组表单信息对象的指针的指针。 如果客户端应用程序中的_pMsgClassArray_参数传递 NULL，则_ppfrminfoarray_参数包含容器中的所有窗体的窗体信息对象。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 呼叫成功或多个预期值返回。
    
## <a name="remarks"></a>说明

客户端应用程序调用**IMAPIFormContainer::ResolveMultipleMessageClasses**方法解析为窗体容器内的窗体的邮件类的组。 返回_ppfrminfoarray_参数中的窗体信息对象的数组进一步提供对每个窗体的属性的访问。 
  
## <a name="notes-to-callers"></a>给调用方的说明

若要解决窗体的邮件类的组，传递数组中的邮件类名称解析。 强制为完全的分辨率 (即，以防止对的邮件类的基类的分辨率)，可以_ulFlags_参数中传递 MAPIFORM_EXACTMATCH 标志。 
  
如果邮件类无法解析到窗体，窗体信息数组中的邮件类将返回 NULL。 因此，即使该方法返回 S_OK，不要假定已成功解析的所有邮件类。 相反，检查返回的数组中的值。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|FormContainerDlg.cpp  <br/> |CFormContainerDlg::OnResolveMultipleMessageClasses  <br/> |MFCMAPI 使用**IMAPIFormContainer::ResolveMultipleMessageClasses**方法查找与一组的邮件类关联的表单。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIFormContainer::ResolveMessageClass](imapiformcontainer-resolvemessageclass.md)
  
[IMAPIFormContainer : IUnknown](imapiformcontaineriunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

