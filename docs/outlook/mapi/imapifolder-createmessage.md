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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32280083"
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
  
> 实时指向接口标识符 (IID) 的指针, 该接口标识符表示要用于访问新邮件的接口。 有效的接口标识符包括 IID_IUnknown、IID_IMAPIProp、IID_IMAPIContainer 和 IID_IMAPIFolder。 传递 NULL 将导致邮件存储区提供程序返回标准的邮件接口[IMessage: IMAPIProp](imessageimapiprop.md)。 
    
 _ulFlags_
  
> 实时用于控制如何创建邮件的标志的位掩码。 可以设置以下标志:
    
ITEMPROC_FORCE
  
> 向个人文件夹存储 (PST) 表明, 在存储通知任何侦听客户端的新邮件到达之前, 该邮件符合规则的处理条件。 规则处理仅适用于在不是 Microsoft Exchange server 的服务器上创建的新邮件, 因为 Exchange server 会在服务器上处理邮件的规则。 因此, 创建邮件的提供程序或客户端必须结合使用[IMAPIPProp:: SaveChanges](imapiprop-savechanges.md) using NON_EMS_XP_SAVE (指示服务器不是 Exchange 服务器) 中的另一封邮件传递此标志。 
    
MAPI_ASSOCIATED 
  
> 要创建的邮件应包含在 "关联的内容" 表中, 而不是 "标准内容" 表中。 将隐藏用户交互中的关联邮件。
    
MAPI_DEFERRED_ERRORS 
  
> 即使创建操作尚未完全完成, 也允许**CreateMessage**成功。 这意味着可能无法立即向呼叫者提供新邮件。 
    
 _lppMessage_
  
> 排除指向新创建的邮件的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 邮件已成功创建。
    
## <a name="remarks"></a>注解

**IMAPIFolder:: CreateMessage**方法创建一个包含常规或关联内容的新邮件, 并分配一个条目标识符。 条目标识符由表示邮件存储提供程序的部件和表示单个邮件的部件组成。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

您可以选择是在**CreateMessage**中还是在邮件的[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)方法中设置所有必需的邮件属性。 只有在成功保存之后, 才必须使这些属性可用。 
  
有关如何使用关联信息的详细信息, 请参阅与[文件夹相关的信息表](folder-associated-information-tables.md)和[内容表](contents-tables.md)。 
  
## <a name="notes-to-callers"></a>给调用方的说明

某些邮件存储提供程序允许新邮件的条目标识符在**CreateMessage**返回后立即可用。在保存邮件之前, 其他邮件存储提供程序会延迟其可用性。 由于并非所有邮件存储提供程序都会为新邮件生成条目标识符, 直到您调用邮件的**IMAPIProp:: SaveChanges**方法之后, 您可能无法在**CreateMessage**返回时访问条目标识符。 此外, 在保存过程中, 新邮件可能不会包含在文件夹的内容表中。 
  
预计分配给新邮件的条目标识符不仅在当前邮件存储中是唯一的, 而且很可能跨所有同时打开的邮件存储区。 当邮件存储区中的多个条目出现在配置文件中时, 将发生此规则的一个例外。 这会导致邮件存储区多次打开, 并且条目标识符将被复制。 
  
若要创建传出邮件, 请调用 "发件箱" 文件夹的**IMAPIFolder:: CreateMessage**方法。 
  
如果在保存邮件之前删除了包含新邮件的文件夹, 则结果是不确定的。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|FolderDlg  <br/> |CFolder:: OnNewMessage  <br/> |MFCMAPI 使用**IMAPIFolder:: CreateMessage**方法创建并保存新邮件。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIProp::SaveChanges](imapiprop-savechanges.md)
  
[IMAPIFolder : IMAPIContainer](imapifolderimapicontainer.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

