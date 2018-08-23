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
ms.openlocfilehash: e9e0ad958acc40dd28f3d9aab9996c1b7a36f38a
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22591483"
---
# <a name="imapisessionshowform"></a>IMAPISession::ShowForm

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
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
  
> [in]窗体的父窗口的句柄。
    
 _lpMsgStore_
  
> [in]消息存储库包含文件夹指向的指针指向_lpParentFolder_参数。 
    
 _lpParentFolder_
  
> [in]指向在其中创建_ulMessageToken_参数与关联的邮件文件夹的指针。 
    
 _lpInterface_
  
> [in]指向接口标识 (IID) 值，该值代表要用于访问表单中显示的消息的接口的指针。 _LpInterface_参数必须为空或 IID_IMessage。 传递空导致标准， [IMessage](imessageimapiprop.md)，正在使用的接口。 
    
 _ulMessageToken_
  
> [in]与窗体中显示的消息相关联的令牌。 从[IMAPISession::PrepareForm](imapisession-prepareform.md)到以前的呼叫， _ulMessageToken_参数必须设置为_lpulMessageToken_参数的内容。
    
 _lpMessageSent_
  
> [in]保留;必须为 NULL。 
    
 _ulFlags_
  
> [in]位掩码的标志，控制如何和是否保存邮件。 可以设置以下标志：
    
MAPI_NEW_MESSAGE 
  
> 从未保存过邮件 （即，其[IMAPIProp::SaveChanges](imapiprop-savechanges.md)方法调用过）。 
    
MAPI_POST_MESSAGE 
  
> 邮件应将保存到其父文件夹中。 消息未发送的处理，但投递到文件夹改为。 如果未设置此标志，邮件复制到发件箱并处理发送。 
    
 _ulMessageStatus_
  
> [in]复制从与_ulMessageToken_参数中的令牌关联的消息的**PR_MSG_STATUS** ([PidTagMessageStatus](pidtagmessagestatus-canonical-property.md)) 属性的标志的位掩码。 标志提供有关邮件的状态信息。 
    
 _ulMessageFlags_
  
> [in]复制从与_ulMessageToken_参数中的令牌关联的消息的**PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) 属性的标志的位掩码。 这些标志进一步提供有关邮件的状态信息。 
    
 _ulAccess_
  
> [in]一个标志，指示表单中显示的消息的权限级别。 从与_ulMessageToken_参数中的令牌关联的消息的**PR_ACCESS** ([PidTagAccess](pidtagaccess-canonical-property.md)) 属性复制此信息。 
    
 _lpszMessageClass_
  
> [in]指向要显示在表单中，复制**PR_MESSAGE_CLASS** ([PidTagMessageClass](pidtagmessageclass-canonical-property.md)) 属性与_ulMessageToken_参数中标记相关联的消息中的邮件的邮件类的指针。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 成功显示窗体。
    
MAPI_E_USER_CANCEL 
  
> 用户取消操作，通常通过单击对话框中的**取消**按钮。 
    
## <a name="remarks"></a>注解

**IMAPISession::ShowForm**方法显示已准备好**IMAPISession::PrepareForm**方法的邮件窗体。 
  
## <a name="notes-to-callers"></a>给调用方的说明

您应该仅对**PrepareForm**方法的_lpMessage_参数中传递的消息的单个引用。 
  
注意窗体实现可以返回错误值以外的记录的 MAPI 的值。 如果您可以使用这些错误值要更精确地确定错误条件的这样做。 与您处理 MAPI_E_CALL_FAILED，否则，处理这些错误。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|MAPIFormFunctions.cpp  <br/> |OpenMessageModal  <br/> |MFCMAPI 使用**IMAPISession::ShowForm**方法，以及**PrepareForm**方法中，窗体模式中显示一条消息。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIProp::SaveChanges](imapiprop-savechanges.md)
  
[IMessage : IMAPIProp](imessageimapiprop.md)
  
[IMAPISession::PrepareForm](imapisession-prepareform.md)
  
[IMAPISession : IUnknown](imapisessioniunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

