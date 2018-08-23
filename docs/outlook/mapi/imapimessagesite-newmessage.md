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
ms.openlocfilehash: 133a2ae3896b9aaedb502cb77516040c53584882
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22563735"
---
# <a name="imapimessagesitenewmessage"></a>IMAPIMessageSite::NewMessage

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
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
  
> [in]指示哪些文件夹中邮件应组成。 如果该变量为 FALSE，将忽略该_pFolderFocus_参数和表单查看器可以撰写任何文件夹中的邮件。 如果该变量值为 TRUE 和_pFolderFocus_参数中传递 NULL，则邮件由当前文件夹中。 如果该变量为 TRUE 且非 NULL 值_pFolderFocus_中传递，邮件由由_pFolderFocus_指向的文件夹中。
    
 _pFolderFocus_
  
> [in]指向在其中创建新邮件文件夹的指针。
    
 _pPersistMessage_
  
> [in]指向新窗体的窗体对象的指针。
    
 _ppMessage_
  
> [输出]为指向新邮件的指针。
    
 _ppMessageSite_
  
> [输出]指向新邮件的邮件网站对象的指针的指针。
    
 _ppViewContext_
  
> [输出]指向适用于向新窗体与新邮件的传递了视图上下文的指针的指针。 如果窗体实现自己视图上下文，则可以_ppViewContext_参数中传递 NULL。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 呼叫成功或多个预期值返回。
    
## <a name="remarks"></a>注解

表单对象调用**IMAPIMessageSite::NewMessage**方法创建新邮件。 窗体使用**NewMessage**获得其视图的新邮件和关联的邮件网站。 然后，它可以修改新邮件。 
  
您还可以通过传入非 NULL 值_ppViewContext_参数中获取的关联的视图上下文。 此视图上下文可直接，也可以聚合和传递给新邮件。 如果需要完整的实现，则在_ppViewContext_传递 NULL。
  
有关与窗体服务器相关的接口的列表，请参阅[MAPI 表单接口](mapi-form-interfaces.md)。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|MyMAPIFormViewer.cpp  <br/> |CMyMAPIFormViewer::NewMessage  <br/> |MFCMAPI 使用**IMAPIMessageSite::NewMessage**方法创建一个新的邮件、 实例化新的表单查看器中，并调用**SetPersist**对表单查看器中设置邮件。 最后，该消息网站返回表单查看器。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIViewContext : IUnknown](imapiviewcontextiunknown.md)
  
[IMAPIMessageSite : IUnknown](imapimessagesiteiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)
  
[MAPI 表单接口](mapi-form-interfaces.md)

