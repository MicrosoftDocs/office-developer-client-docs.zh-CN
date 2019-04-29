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
  
> 实时表单的父窗口的句柄。
    
 _lpMsgStore_
  
> 实时指向邮件存储区的指针, 该邮件存储区包含由_lpParentFolder_参数指向的文件夹。 
    
 _lpParentFolder_
  
> 实时一个指针, 指向在其中创建与_ulMessageToken_参数相关联的邮件的文件夹。 
    
 _lpInterface_
  
> 实时指向接口标识符 (IID) 的指针, 该接口标识符代表要用于访问表单中显示的邮件的接口。 _lpInterface_参数必须为 NULL 或 IID_IMessage。 在使用的标准接口[IMessage](imessageimapiprop.md)中传递 NULL 结果。 
    
 _ulMessageToken_
  
> 实时与要在表单中显示的邮件相关联的标记。 必须将_ulMessageToken_参数设置为以前对[IMAPISession::P repareform](imapisession-prepareform.md)的调用中的_lpulMessageToken_参数的内容。
    
 _lpMessageSent_
  
> 实时保留必须为 NULL。 
    
 _ulFlags_
  
> 实时用于控制是否保存邮件以及是否保存邮件的标志的位掩码。 可以设置以下标志:
    
MAPI_NEW_MESSAGE 
  
> 从未保存过该邮件 (即它的[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)方法从未被调用过)。 
    
MAPI_POST_MESSAGE 
  
> 应将邮件保存到其父文件夹中。 邮件不会被处理为发送, 而是投递到文件夹中。 如果未设置此标志, 则会将邮件复制到 "发件箱", 并将其处理为发送。 
    
 _ulMessageStatus_
  
> 实时从与_ulMessageToken_参数中的标记关联的消息的**PR_MSG_STATUS** ([PidTagMessageStatus](pidtagmessagestatus-canonical-property.md)) 属性复制的标志的位掩码。 这些标志提供有关邮件状态的信息。 
    
 _ulMessageFlags_
  
> 实时从与_ulMessageToken_参数中的标记关联的消息的**PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) 属性复制的标志的位掩码。 这些标志提供有关邮件状态的详细信息。 
    
 _ulAccess_
  
> 实时指示表单中显示的邮件的权限级别的标志。 此信息从与_ulMessageToken_参数中的令牌相关联的邮件的**PR_ACCESS** ([PidTagAccess](pidtagaccess-canonical-property.md)) 属性复制。 
    
 _lpszMessageClass_
  
> 实时指向在表单中显示的邮件的邮件类的指针, 从与_ulMessageToken_参数中的令牌相关联的邮件的**PR_MESSAGE_CLASS** ([PidTagMessageClass](pidtagmessageclass-canonical-property.md)) 属性复制。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 表单已成功显示。
    
MAPI_E_USER_CANCEL 
  
> 用户取消了操作, 通常是单击对话框中的 "**取消**" 按钮。 
    
## <a name="remarks"></a>说明

**IMAPISession:: ShowForm**方法显示一个已由**IMAPISession::P repareform**方法准备的邮件窗体。 
  
## <a name="notes-to-callers"></a>给调用方的说明

您应该只有对在**PrepareForm**方法的_lpMessage_参数中传递的邮件的单个引用。 
  
请注意, 表单实现可能返回除 MAPI 记录的错误值之外的其他错误值。 如果可以使用这些错误值来更精确地确定错误条件, 请执行此操作。 否则, 请处理这些错误, 就像处理 MAPI_E_CALL_FAILED 一样。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MAPIFormFunctions  <br/> |OpenMessageModal  <br/> |MFCMAPI 将**IMAPISession:: ShowForm**方法与**PrepareForm**方法结合使用, 以在模式窗体中显示消息。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIProp::SaveChanges](imapiprop-savechanges.md)
  
[IMessage : IMAPIProp](imessageimapiprop.md)
  
[IMAPISession::PrepareForm](imapisession-prepareform.md)
  
[IMAPISession : IUnknown](imapisessioniunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

