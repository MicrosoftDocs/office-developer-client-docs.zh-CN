---
title: IMAPIFolderCreateMessage
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIFolder.CreateMessage
api_type:
- COM
ms.assetid: e0222afa-c148-4735-a603-cac7be6c91f9
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: e740e86fc25307457119aabf6e2aa0c42a9d69b9
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22568222"
---
# <a name="imapifoldercreatemessage"></a>IMAPIFolder::CreateMessage

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
创建新邮件。
  
```cpp
HRESULT CreateMessage(
  LPCIID lpInterface,
  ULONG ulFlags,
  LPMESSAGE FAR * lppMessage
);
```

## <a name="parameters"></a>参数

 _lpInterface_
  
> [in]指向接口标识 (IID) 值，该值代表要用于访问新邮件的接口的指针。 有效的接口标识符包括 IID_IUnknown、 IID_IMAPIProp、 IID_IMAPIContainer 和 IID_IMAPIFolder。 传递 NULL 将导致消息存储提供程序返回的标准消息接口， [IMessage: IMAPIProp](imessageimapiprop.md)。 
    
 _ulFlags_
  
> [in]位掩码的标志，控制如何创建消息。 可以设置以下标志：
    
ITEMPROC_FORCE
  
> 指示到个人文件夹存储区 (PST) 邮件是否符合规则处理之前存储通知新消息的到达任何侦听客户端。 规则仅处理适用于 Exchange Server 处理服务器上的邮件的规则，因为不是 Microsoft Exchange Server，服务器创建的新邮件。 因此，提供程序或创建邮件客户端必须通过此标志结合使用[IMAPIPProp::SaveChanges](imapiprop-savechanges.md)保存一条消息，使用 NON_EMS_XP_SAVE，这表明服务器不是 Exchange 服务器。 
    
MAPI_ASSOCIATED 
  
> 应关联的内容表而不是标准内容表中包含要创建的消息。 从用户交互将隐藏相关联的消息。
    
MAPI_DEFERRED_ERRORS 
  
> 允许**CreateMessage**即使未全部完成创建操作已成功。 这意味着新邮件可能不会与呼叫者立即可用。 
    
 _lppMessage_
  
> [输出]指向新创建的消息的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 邮件已成功创建。
    
## <a name="remarks"></a>注解

**IMAPIFolder::CreateMessage**方法使用泛型或关联的内容创建一个新的邮件和分配条目标识符。 项标识符由部件的表示的消息存储提供程序和代表单个邮件的部件组成。 
  
## <a name="notes-to-implementers"></a>针对实施者的注释

您可以选择是否在**CreateMessage**或消息的[IMAPIProp::SaveChanges](imapiprop-savechanges.md)方法设置的所有必需的消息属性。 您不必公开这些属性，直到成功保存发生。 
  
有关如何使用相关的信息，请参阅[Folder-Associated 信息表](folder-associated-information-tables.md)和[内容表](contents-tables.md)的详细信息。 
  
## <a name="notes-to-callers"></a>给调用方的说明

某些消息存储提供程序允许可返回**CreateMessage** ; 后立即的新邮件的项标识符其他消息存储提供程序直到保存邮件延迟其可用性。 并非所有的消息存储提供程序直到以前呼叫过该消息的**IMAPIProp::SaveChanges**方法生成一个新的邮件的项标识符，因为您可能无法访问**CreateMessage**返回的项标识符。 此外，新邮件可能不会包含该文件夹的内容表中之前保存，发生此事件。 
  
预期分配给该新消息的消息存储库同时打开的所有成为唯一而不是只在当前消息存储库，但最可能的项标识符。 配置文件中出现的消息存储库的多个条目时发生此规则的一个例外。 这会导致要打开多次消息存储和要重复的条目标识符。 
  
若要创建传出邮件，请调用发件箱文件夹的**IMAPIFolder::CreateMessage**方法。 
  
如果您删除之前保存邮件包含一封新邮件的文件夹，则结果是未定义。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|FolderDlg.cpp  <br/> |CFolder::OnNewMessage  <br/> |MFCMAPI 使用**IMAPIFolder::CreateMessage**方法创建和保存新邮件。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIProp::SaveChanges](imapiprop-savechanges.md)
  
[IMAPIFolder : IMAPIContainer](imapifolderimapicontainer.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

