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
ms.openlocfilehash: 1f3a876269868c30df48e0a0b62036cfdc199955
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775418"
---
# <a name="imapiformmgrloadform"></a>IMAPIFormMgr::LoadForm

  
  
**适用于**： Outlook 
  
启动打开现有邮件窗体。
  
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
  
> [in]打开表单时显示进度指示器的父窗口句柄。 除非 MAPI_DIALOG 标志设置_ulFlags_参数中，将忽略该_ulUIParam_参数。 
    
 _ulFlags_
  
> [in]位掩码的标志，控制如何打开表单。 可以设置以下标志：
    
MAPI_DIALOG 
  
> 显示用户界面，以提供状态或提示用户输入的详细信息。 如果未设置此标志，将显示没有用户界面。
    
MAPIFORM_EXACTMATCH 
  
> 应解决仅邮件类的字符串完全匹配。
    
 _lpszMessageClass_
  
> [in]一个指向命名要加载的邮件的邮件类的字符串。 如果_lpszMessageClass_参数中传递 NULL，则邮件类由_pmsg_参数指向的邮件。 
    
 _ulMessageStatus_
  
> [in]复制邮件的**PR_MSG_STATUS** ([PidTagMessageStatus](pidtagmessagestatus-canonical-property.md)) 属性中的客户端或提供程序定义标志的位掩码，提供有关状态的消息的信息。 如果_lpszMessageClass_为非空; 必须设置_ulMessageStatus_参数否则，将忽略_ulMessageStatus_ 。 
    
 _ulMessageFlags_
  
> [in]一个指向标志指示邮件的当前状态的消息的**PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) 属性从复制的位掩码。 如果_lpszMessageClass_为非空; 必须设置_ulMessageFlags_参数否则，将忽略_ulMessageFlags_ 。 
    
 _pFolderFocus_
  
> [in]一个指向直接包含邮件的文件夹。 _PFolderFocus_参数可以是 NULL，如果这样的文件夹不存在 （例如，如果邮件嵌入到另一条消息）。 
    
 _pMessageSite_
  
> [in]一个指向邮件的邮件网站。
    
 _pmsg_
  
> [in]指向邮件的指针。
    
 _pViewContext_
  
> [in]一个指向视图上下文的邮件。 _PViewContext_参数可以是 NULL。 
    
 _riid_
  
> [in]用于返回的 form 对象的接口接口标识符 (IID)。 _Riid_参数不能为 NULL。 
    
 _ppvObj_
  
> [输出]指向返回的接口的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 呼叫成功或多个预期值返回。
    
MAPI_E_NO_INTERFACE 
  
> 窗体不支持所请求的接口。
    
MAPI_E_NOT_FOUND 
  
> _LpszMessageClass_中传递的邮件类不匹配的邮件类的窗体库中的任何表单。 
    
## <a name="remarks"></a>说明

表单查看器调用**IMAPIFormMgr::LoadForm**方法打开现有邮件窗体。 **LoadForm**打开 form 对象，将邮件加载到窗体对象、 设置适当的视图上下文，如有必要，并返回窗体对象的请求的接口。 
  
_PFolderFocus_参数指向包含邮件的文件夹。 邮件嵌入到另一条消息中，如果_pFolderFocus_应为 NULL。 
  
## <a name="notes-to-implementers"></a>针对实施者的注释

实现消息的**PR_MESSAGE_CLASS** ([PidTagMessageClass](pidtagmessageclass-canonical-property.md))、 **PR_MSG_STATUS**和**PR_MESSAGE_FLAGS 如果_lpszMessageClass_中传递 NULL，则获取消息的邮件类、 状态和标志**属性。 如果_lpszMessageClass_中提供的邮件类字符串，则实现必须使用_ulMessageStatus_和_ulMessageFlags_中的值。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|MAPIFormFunctions.cpp  <br/> |OpenMessageNonModal  <br/> |MFCMAPI 使用**IMAPIFormMgr::LoadForm**方法显示之前加载窗体。  <br/> |
   
## <a name="see-also"></a>另请参阅



[PidTagMessageClass 规范属性](pidtagmessageclass-canonical-property.md)
  
[PidTagMessageFlags 规范属性](pidtagmessageflags-canonical-property.md)
  
[PidTagMessageStatus 规范属性](pidtagmessagestatus-canonical-property.md)
  
[IMAPIFormMgr : IUnknown](imapiformmgriunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

