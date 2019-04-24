---
title: IMAPIFormMgrLoadForm
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIFormMgr.LoadForm
api_type:
- COM
ms.assetid: 5ca500c3-c737-45a5-b0fc-473b75c1d68d
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7e445646477ad1fc56b41141b541358d9b9f9616
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32321689"
---
# <a name="imapiformmgrloadform"></a>IMAPIFormMgr::LoadForm

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
启动窗体以打开现有邮件。
  
```cpp
HRESULT LoadForm(
  ULONG_PTR ulUIParam,
  ULONG ulFlags,
  LPCSTR lpszMessageClass,
  ULONG ulMessageStatus,
  ULONG ulMessageFlags,
  LPMAPIFOLDER pFolderFocus,
  LPMAPIMESSAGESITE pMessageSite,
  LPMESSAGE pmsg,
  LPMAPIVIEWCONTEXT pViewContext,
  REFIID riid,
  LPVOID FAR * ppvObj
);
```

## <a name="parameters"></a>参数

 _ulUIParam_
  
> 实时进度指示器的父窗口的句柄, 在打开窗体时显示。 除非在_ulFlags_参数中设置了 MAPI_DIALOG 标志, 否则将忽略_ulUIParam_参数。 
    
 _ulFlags_
  
> 实时用于控制表单打开方式的标志的位掩码。 可以设置以下标志:
    
MAPI_DIALOG 
  
> 显示一个用户界面, 以提供状态或提示用户详细信息。 如果未设置此标志, 则不会显示任何用户界面。
    
MAPIFORM_EXACTMATCH 
  
> 应解析完全匹配的邮件类字符串。
    
 _lpszMessageClass_
  
> 实时指向一个字符串的指针, 该字符串命名要加载的邮件的邮件类。 如果在_lpszMessageClass_参数中传递 NULL, 则邮件类由_pmsg_参数所指向的邮件确定。 
    
 _ulMessageStatus_
  
> 实时从邮件的**PR_MSG_STATUS** ([PidTagMessageStatus](pidtagmessagestatus-canonical-property.md)) 属性中复制的客户端定义或提供程序定义的标志的位掩码, 它提供有关邮件状态的信息。 如果_lpszMessageClass_为非 NULL, 则必须设置_ulMessageStatus_参数;否则, _ulMessageStatus_将被忽略。 
    
 _ulMessageFlags_
  
> 实时指向从消息的**PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) 属性复制的标志位掩码的指针, 该消息指示邮件的当前状态。 如果_lpszMessageClass_为非 NULL, 则必须设置_ulMessageFlags_参数;否则, _ulMessageFlags_将被忽略。 
    
 _pFolderFocus_
  
> 实时指向直接包含邮件的文件夹的指针。 如果不存在这样的文件夹 (例如, 如果邮件嵌入在另一封邮件中), _pFolderFocus_参数可以为 NULL。 
    
 _pMessageSite_
  
> 实时指向邮件的邮件网站的指针。
    
 _pmsg_
  
> 实时指向邮件的指针。
    
 _pViewContext_
  
> 实时指向邮件的视图上下文的指针。 _pViewContext_参数可以为 NULL。 
    
 _riid_
  
> 实时要用于返回的 form 对象的接口的接口标识符 (IID)。 _riid_参数不得为 NULL。 
    
 _ppvObj_
  
> 排除指向指向返回的接口的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功, 并返回了所需的值或值。
    
MAPI_E_NO_INTERFACE 
  
> 表单不支持所请求的界面。
    
MAPI_E_NOT_FOUND 
  
> _lpszMessageClass_中传递的邮件类与表单库中任何表单的邮件类都不匹配。 
    
## <a name="remarks"></a>注解

表单查看者调用**IMAPIFormMgr:: LoadForm**方法打开现有邮件的表单。 **LoadForm**打开 form 对象, 将邮件加载到 form 对象中, 并设置适当的视图上下文 (如有必要), 并返回窗体对象所请求的接口。 
  
_pFolderFocus_参数指向包含邮件的文件夹。 如果邮件嵌入在另一封邮件中, 则_pFolderFocus_应为 NULL。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

如果在_lpszMessageClass_中传递 NULL, 则实现将从邮件的**PR_MESSAGE_CLASS** ([PidTagMessageClass](pidtagmessageclass-canonical-property.md))、 **PR_MSG_STATUS**和 PR_MESSAGE_FLAGS 中获取邮件的邮件类、状态和标志。 **** 属性。 如果在_lpszMessageClass_中提供了邮件类字符串, 则该实现必须使用_ulMessageStatus_和_ulMessageFlags_中的值。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MAPIFormFunctions  <br/> |OpenMessageNonModal  <br/> |MFCMAPI 使用**IMAPIFormMgr:: LoadForm**方法在显示窗体之前加载它。  <br/> |
   
## <a name="see-also"></a>另请参阅



[PidTagMessageClass 规范属性](pidtagmessageclass-canonical-property.md)
  
[PidTagMessageFlags 规范属性](pidtagmessageflags-canonical-property.md)
  
[PidTagMessageStatus 规范属性](pidtagmessagestatus-canonical-property.md)
  
[IMAPIFormMgr : IUnknown](imapiformmgriunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

