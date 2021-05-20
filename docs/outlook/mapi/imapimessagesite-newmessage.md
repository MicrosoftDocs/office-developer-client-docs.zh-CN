---
title: IMAPIMessageSiteNewMessage
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIMessageSite.NewMessage
api_type:
- COM
ms.assetid: ce6b6e6c-7f22-43c2-8182-90cf6db93844
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: f51dd1fe533d0577996e6e1be185302f2dc972fe
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33438769"
---
# <a name="imapimessagesitenewmessage"></a>IMAPIMessageSite::NewMessage

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
创建新邮件。
  
```cpp
HRESULT NewMessage(
  ULONG fComposeInFolder,
  LPMAPIFOLDER pFolderFocus,
  LPPERSISTMESSAGE pPersistMessage,
  LPMESSAGE FAR * ppMessage,
  LPMAPIMESSAGESITE FAR * ppMessageSite,
  LPMAPIVIEWCONTEXT FAR * ppViewContext
);
```

## <a name="parameters"></a>参数

 _fComposeInFolder_
  
> [in]指示应在哪个文件夹中撰写邮件。 如果变量为 FALSE，  _则忽略 pFolderFocus_ 参数，并且窗体查看器可以在任何文件夹中撰写邮件。 如果变量为 TRUE，并且 NULL 在  _pFolderFocus_ 参数中传递，则邮件将在当前文件夹中撰写。 如果变量为 TRUE，且  _pFolderFocus_ 中传递了非 NULL 值，则邮件将组合在  _pFolderFocus 指向的文件夹中_。
    
 _pFolderFocus_
  
> [in]指向新建邮件的文件夹的指针。
    
 _pPersistMessage_
  
> [in]指向新窗体的 form 对象的指针。
    
 _ppMessage_
  
> [out]指向指向新邮件的指针的指针。
    
 _ppMessageSite_
  
> [out]指向指向新邮件的消息网站对象的指针的指针。
    
 _ppViewContext_
  
> [out]指向适用于通过新消息传递到新表单的视图上下文的指针的指针。 如果表单实现自己的视图上下文，可以在  _ppViewContext_ 参数中传递 NULL。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功并返回了预期值。
    
## <a name="remarks"></a>备注

Form 对象调用 **IMAPIMessageSite：：NewMessage** 方法来创建新邮件。 表单使用 **NewMessage** 从其视图中获取新邮件和关联邮件网站。 然后，它可以修改新邮件。 
  
您还可以通过传递  _ppViewContext_ 参数中的非 NULL 值来获取关联的视图上下文。 此视图上下文可以直接使用，也可以聚合并传递到新邮件。 如果需要完整实现，在  _ppViewContext_ 中传递 NULL。
  
有关与表单服务器相关的接口列表，请参阅 [MAPI Form Interfaces](mapi-form-interfaces.md)。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MyMAPIFormViewer.cpp  <br/> |CMyMAPIFormViewer：：NewMessage  <br/> |MFCMAPI 使用 **IMAPIMessageSite：：NewMessage** 方法创建新邮件、实例化新的表单查看器，并调用 **SetPersist** 在表单查看器上设置邮件。 最后，它将窗体查看器作为消息网站返回。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIViewContext : IUnknown](imapiviewcontextiunknown.md)
  
[IMAPIMessageSite : IUnknown](imapimessagesiteiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)
  
[MAPI 表单接口](mapi-form-interfaces.md)

