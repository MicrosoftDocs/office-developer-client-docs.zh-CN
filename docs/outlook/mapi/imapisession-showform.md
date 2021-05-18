---
title: IMAPISessionShowForm
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISession.ShowForm
api_type:
- COM
ms.assetid: 233cf936-34db-42d4-b5e3-17a93acb2009
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 8b90dee3958a20994f9a60d104ae714ad95307d3
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33412525"
---
# <a name="imapisessionshowform"></a>IMAPISession::ShowForm

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
显示窗体。
  
```cpp
HRESULT ShowForm(
  ULONG_PTR ulUIParam,
  LPMDB lpMsgStore,
  LPMAPIFOLDER lpParentFolder,
  LPCIID lpInterface,
  ULONG ulMessageToken,
  LPMESSAGE lpMessageSent,
  ULONG ulFlags,
  ULONG ulMessageStatus,
  ULONG ulMessageFlags,
  ULONG ulAccess,
  LPSTR lpszMessageClass
);
```

## <a name="parameters"></a>参数

 _ulUIParam_
  
> [in]窗体父窗口的句柄。
    
 _lpMsgStore_
  
> [in]指向包含  _lpParentFolder_ 参数指向的文件夹的邮件存储的指针。 
    
 _lpParentFolder_
  
> [in]指向创建与  _ulMessageToken_ 参数关联的邮件的文件夹的指针。 
    
 _lpInterface_
  
> [in]指向接口标识符 (IID) 表示用于访问窗体中显示的消息的接口的指针。 _lpInterface_ 参数必须为 NULL 或 IID_IMessage。 传递 NULL 会导致使用标准接口[IMessage。](imessageimapiprop.md) 
    
 _ulMessageToken_
  
> [in]与要显示在表单中的邮件关联的令牌。 必须将 _ulMessageToken_ 参数设置为上一次对 [IMAPISession：:P repareForm](imapisession-prepareform.md)的调用中 _lpulMessageToken_ 参数的内容。
    
 _lpMessageSent_
  
> [in]保留;必须为 NULL。 
    
 _ulFlags_
  
> [in]控制邮件保存方式和保存方式的标志的位掩码。 可以设置以下标志：
    
MAPI_NEW_MESSAGE 
  
> 邮件从未保存过 (，即 [从未调用过其 IMAPIProp：：SaveChanges](imapiprop-savechanges.md)) 。 
    
MAPI_POST_MESSAGE 
  
> 邮件应保存到其父文件夹。 邮件不会处理发送，而是发送到文件夹。 如果未设置此标志，邮件将复制到发件箱并进行处理以发送。 
    
 _ulMessageStatus_
  
> [in]从 _与 ulMessageToken_ 参数中的令牌关联的邮件的 **PR_MSG_STATUS** ([PidTagMessageStatus](pidtagmessagestatus-canonical-property.md)) 属性复制的标志的位掩码。 标志提供有关邮件状态的信息。 
    
 _ulMessageFlags_
  
> [in]从 _与 ulMessageToken_ 参数 **中的令牌** 关联的邮件的 PR_MESSAGE_FLAGS ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) 属性复制的标志的位掩码。 这些标志提供有关邮件状态的进一步信息。 
    
 _ulAccess_
  
> [in]一个标志，指示窗体中显示的邮件的权限级别。 此信息从与 _ulMessageToken_ 参数 **中的** 令牌PR_ACCESS ([PidTagAccess](pidtagaccess-canonical-property.md)) 属性中复制。 
    
 _lpszMessageClass_
  
> [in]指向表单中显示的邮件的邮件类的指针，从与 _ulMessageToken_ 参数中的令牌关联的邮件的 **PR_MESSAGE_CLASS** ([PidTagMessageClass](pidtagmessageclass-canonical-property.md)) 属性复制。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功显示表单。
    
MAPI_E_USER_CANCEL 
  
> 用户通常通过单击对话框中的"取消" **按钮来取消** 操作。 
    
## <a name="remarks"></a>备注

**IMAPISession：：ShowForm** 方法显示 **由 IMAPISession：:P repareForm 方法准备的消息** 表单。 
  
## <a name="notes-to-callers"></a>给调用方的说明

应只对在 **PrepareForm** 方法的  _lpMessage_ 参数中传递的邮件进行一次引用。 
  
请注意，表单实现可能会返回 MAPI 记录的错误值。 如果可以使用这些错误值更精确地确定错误条件，则执行上述操作。 否则，请像处理这些错误一样处理MAPI_E_CALL_FAILED。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MAPIFormFunctions.cpp  <br/> |OpenMessageModal  <br/> |MFCMAPI 使用 **IMAPISession：：ShowForm** 方法以及 **PrepareForm** 方法在模式窗体中显示消息。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIProp::SaveChanges](imapiprop-savechanges.md)
  
[IMessage : IMAPIProp](imessageimapiprop.md)
  
[IMAPISession::PrepareForm](imapisession-prepareform.md)
  
[IMAPISession : IUnknown](imapisessioniunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

