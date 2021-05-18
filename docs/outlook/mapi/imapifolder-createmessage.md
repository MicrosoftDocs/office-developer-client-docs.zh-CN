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
ms.openlocfilehash: 4d38648f5e3084c8342fca8d18f0bd3efc915155
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33412630"
---
# <a name="imapifoldercreatemessage"></a>IMAPIFolder::CreateMessage

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
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
  
> [in]指向接口标识符的指针 (IID) 表示用于访问新邮件的接口的 IID 标识符。 有效的接口标识符包括IID_IUnknown、IID_IMAPIProp、IID_IMAPIContainer和IID_IMAPIFolder。 传递 NULL 会导致邮件存储提供程序返回标准消息接口 [IMessage ： IMAPIProp](imessageimapiprop.md)。 
    
 _ulFlags_
  
> [in]控制邮件创建方式的标志的位掩码。 可以设置以下标志：
    
ITEMPROC_FORCE
  
> 向 PST (个人文件夹存储) 在存储通知任何侦听客户端新邮件到达之前，该邮件符合规则处理条件。 规则处理仅适用于在非规则服务器上创建的新Microsoft Exchange Server，Exchange Server处理服务器上邮件的规则。 因此，创建邮件的提供程序或客户端必须使用 NON_EMS_XP_SAVE 将邮件与[IMAPIPProp：：SaveChanges](imapiprop-savechanges.md)一起传递此标志，这表示服务器不是 Exchange Server。 
    
MAPI_ASSOCIATED 
  
> 要创建的消息应包含在关联的内容表中，而不是标准内容表中。 关联消息在用户交互中隐藏。
    
MAPI_DEFERRED_ERRORS 
  
> 即使创建操作尚未完成，也允许 **CreateMessage** 成功。 这意味着新邮件可能不会立即对呼叫者可用。 
    
 _lppMessage_
  
> [out]指向指向新创建的消息的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功创建邮件。
    
## <a name="remarks"></a>备注

**IMAPIFolder：：CreateMessage** 方法创建包含通用或关联内容的新消息，并分配条目标识符。 条目标识符由一个代表邮件存储提供程序的部件和一个代表单个邮件的部件组成。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

您可以选择是设置 **CreateMessage** 中或邮件 [的 IMAPIProp：：SaveChanges](imapiprop-savechanges.md) 方法中所需的全部邮件属性。 在成功保存之前，不需要使这些属性可用。 
  
若要详细了解如何处理相关信息，请参阅[Folder-Associated Information Tables](folder-associated-information-tables.md) and [Contents Tables。](contents-tables.md) 
  
## <a name="notes-to-callers"></a>给调用方的说明

某些邮件存储提供程序允许在 **CreateMessage** 返回后立即提供新邮件的条目标识符;其他邮件存储提供程序会延迟其可用性，直到邮件保存。 由于在调用邮件的 **IMAPIProp：：SaveChanges** 方法之前，并非所有邮件存储提供程序都会生成新邮件的条目标识符，因此在 **CreateMessage** 返回时，可能无法访问条目标识符。 此外，在保存发生之前，新邮件可能不包含在文件夹的内容表中。 
  
预计分配给新邮件的条目标识符不仅在当前邮件存储中是唯一的，而且很可能在所有同时打开的邮件存储中是唯一的。 当配置文件中出现邮件存储的多个条目时，会出现此规则的一个例外。 这将导致多次打开邮件存储并复制条目标识符。 
  
若要创建传出邮件，请调用发件箱文件夹的 **IMAPIFolder：：CreateMessage** 方法。 
  
如果在保存邮件之前删除包含新邮件的文件夹，则结果未定义。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|FolderDlg.cpp  <br/> |CFolder：：OnNewMessage  <br/> |MFCMAPI 使用 **IMAPIFolder：：CreateMessage** 方法创建和保存新邮件。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIProp::SaveChanges](imapiprop-savechanges.md)
  
[IMAPIFolder : IMAPIContainer](imapifolderimapicontainer.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

