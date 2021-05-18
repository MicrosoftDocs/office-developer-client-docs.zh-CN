---
title: PidTagMessageClass 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagMessageClass
api_type:
- HeaderDef
ms.assetid: 1e704023-1992-4b43-857e-0a7da7bc8e87
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7912a3831333ff8a464a12e567430eb5a3272172
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32359261"
---
# <a name="pidtagmessageclass-canonical-property"></a>PidTagMessageClass 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含标识发件人定义的消息类别的文本字符串，例如 IPM.Note。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_MESSAGE_CLASS、PR_MESSAGE_CLASS_A、PR_MESSAGE_CLASS_W  <br/> |
|标识符:  <br/> |0x001A  <br/> |
|数据类型：  <br/> |PT_UNICODE、PT_STRING8  <br/> |
|区域：  <br/> |常见  <br/> |
   
## <a name="remarks"></a>备注

邮件类指定邮件的类型。 它确定为邮件定义的属性集、邮件传达的信息类型以及如何处理邮件。 
  
这些属性包含与句点连接在一起的字符串。 每个字符串表示子类的级别。 例如，IPM。注意 是 IPM 的子类和 IPM 的超级类。Note.Private。 
  
这些属性必须由 32 到 127 的 ASCII 字符组成，不得以 ASCII 46 (结束) 。 排序和比较操作必须视为不区分大小写的字符串。 最大可能长度为 255 个字符，但为了允许 MAPI 会议室追加限定符，建议原始长度保持在 128 个字符以下。 
  
需要每条消息才能提供这些属性。 通常，一旦 [IMAPIFolder：：CreateMessage](imapifolder-createmessage.md) 成功返回，创建新消息的客户端应用程序就会设置它。 但是，如果客户端调用 [IMAPIProp：：SaveChanges](imapiprop-savechanges.md)时尚未设置该属性，则消息存储应将其设置为 IPM。 
  
MAPI 定义的值为： 
  
```cpp
IPM.Note for a standard interpersonal message 
REPORT.<subject message class>.DR for a delivery report 
REPORT.<subject message class>.NDR for a nondelivery report 
REPORT.<subject message class>.IPNRN for a read report 
REPORT.<subject message class>.IPNNRN for a nonread report 
 
```

IPM 和 IPC 仅用作超级类，邮件在存储或提交之前至少应附加一个子类限定符。 有关邮件类使用情况的信息，请参阅 [邮件类](mapi-message-classes.md)。 有关邮件类的必需属性和可选属性的列表，请参阅关于邮件 [属性的子标题](message-properties-overview.md)。
  
自定义邮件类可以定义保留范围中的属性，以仅与邮件类一同使用。 有关详细信息，请参阅关于 [属性标识符](mapi-property-identifier-overview.md)。 
  
邮件类控制传入邮件存储在哪个接收文件夹中。 有关详细信息，请参阅 [IMsgStore：：GetReceiveFolderTable](imsgstore-getreceivefoldertable.md) 方法。 
  
有关将邮件类与窗体和窗体服务器一同使用的信息，请参阅 [选择邮件类](choosing-a-message-class.md)。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关协议Exchange Server的引用。
    
[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)
  
> 处理邮件和附件对象。
    
[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)
  
> 指定电子邮件对象允许的属性和操作。
    
[[MS-OXOUM]](https://msdn.microsoft.com/library/2a0696c5-2caf-4f20-87fb-085db430afec%28Office.15%29.aspx)
  
> 指定允许用于表示语音邮件和传真邮件的属性和操作。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为关联属性列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

