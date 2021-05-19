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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33418783"
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
  
> [in]打开窗体时显示的进度指示器的父窗口的句柄。 除非  _在 ulFlags_ 参数中设置了 MAPI_DIALOG 标志，否则将忽略  _ulUIParam_ 参数。 
    
 _ulFlags_
  
> [in]控制表单打开方式的标志的位掩码。 可以设置以下标志：
    
MAPI_DIALOG 
  
> 显示用户界面以提供状态或提示用户输入详细信息。 如果未设置此标志，则不显示用户界面。
    
MAPIFORM_EXACTMATCH 
  
> 仅应解析完全匹配的邮件类字符串。
    
 _lpszMessageClass_
  
> [in]指向字符串的指针，用于命名要加载的邮件的邮件类。 如果在  _lpszMessageClass_ 参数中传递 NULL，则邮件类由  _pmsg_ 参数指向的消息确定。 
    
 _ulMessageStatus_
  
> [in]从邮件的 **PR_MSG_STATUS** ([PidTagMessageStatus](pidtagmessagestatus-canonical-property.md)) 属性复制的客户端定义或提供程序定义标志的位掩码，提供有关邮件状态的信息。 如果 _lpszMessageClass_ 为非 NULL，则必须设置 _ulMessageStatus_ 参数;否则，_将忽略 ulMessageStatus。_ 
    
 _ulMessageFlags_
  
> [in]指向从邮件的 **PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) 属性复制的标志的位掩码的指针，指示邮件的当前状态。 如果 _lpszMessageClass_ 为非 NULL，则必须设置 _ulMessageFlags_ 参数;否则，_将忽略 ulMessageFlags。_ 
    
 _pFolderFocus_
  
> [in]指向直接包含邮件的文件夹的指针。 如果  _不存在此类文件夹，pFolderFocus_ 参数可以是 NULL (例如，如果邮件嵌入另一个邮件) 。 
    
 _pMessageSite_
  
> [in]指向邮件消息网站的指针。
    
 _pmsg_
  
> [in]指向消息的指针。
    
 _pViewContext_
  
> [in]指向消息的视图上下文的指针。 _pViewContext_ 参数可以是 NULL。 
    
 _riid_
  
> [in]接口标识符 (IID) 返回的表单对象所使用的接口的 IID 标识符。 _riid_ 参数不能为 NULL。 
    
 _ppvObj_
  
> [out]指向返回接口的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功并返回了预期值。
    
MAPI_E_NO_INTERFACE 
  
> 表单不支持请求的接口。
    
MAPI_E_NOT_FOUND 
  
> 在  _lpszMessageClass_ 中传递的邮件类与表单库中任何窗体的邮件类不匹配。 
    
## <a name="remarks"></a>备注

表单查看器调用 **IMAPIFormMgr：：LoadForm** 方法来打开现有邮件的表单。 **LoadForm** 打开窗体对象，将邮件加载到窗体对象中，在必要时设置适当的视图上下文，并返回窗体对象请求的接口。 
  
_pFolderFocus_ 参数指向包含邮件的文件夹。 如果邮件嵌入到另一封邮件中，  _则 pFolderFocus_ 应为 NULL。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

如果在 _lpszMessageClass_ 中传递 NULL，则实现从邮件的 **PR_MESSAGE_CLASS** ([PidTagMessageClass](pidtagmessageclass-canonical-property.md)) 、PR_MSG_STATUS 和 **PR_MESSAGE_FLAGS** 属性获取邮件的邮件类、状态和标志。  如果在  _lpszMessageClass_ 中提供了消息类字符串，则实现必须使用  _ulMessageStatus_ 和  _ulMessageFlags 中的值_。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MAPIFormFunctions.cpp  <br/> |OpenMessageNonModal  <br/> |MFCMAPI 使用 **IMAPIFormMgr：：LoadForm** 方法在显示表单之前加载表单。  <br/> |
   
## <a name="see-also"></a>另请参阅



[PidTagMessageClass 规范属性](pidtagmessageclass-canonical-property.md)
  
[PidTagMessageFlags 规范属性](pidtagmessageflags-canonical-property.md)
  
[PidTagMessageStatus 规范属性](pidtagmessagestatus-canonical-property.md)
  
[IMAPIFormMgr : IUnknown](imapiformmgriunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

