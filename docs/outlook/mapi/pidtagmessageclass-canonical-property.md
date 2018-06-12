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
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: d4e478b053bc1aa81643a60899480ac2ad9d4265
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777835"
---
# <a name="pidtagmessageclass-canonical-property"></a>PidTagMessageClass 规范属性

  
  
**适用于**： Outlook 
  
包含标识-定义发件人的邮件类 IPM 如文本字符串。请注意。 
  
|||
|:-----|:-----|
|关联的属性：  <br/> |PR_MESSAGE_CLASS，PR_MESSAGE_CLASS_A，PR_MESSAGE_CLASS_W  <br/> |
|标识符:  <br/> |0x001A  <br/> |
|数据类型：  <br/> |PT_UNICODE PT_STRING8  <br/> |
|区域：  <br/> |Common  <br/> |
   
## <a name="remarks"></a>备注

邮件类将指定的邮件的类型。 它确定属性为邮件，定义将传达信息消息的类型，以及如何处理邮件的设置。 
  
这些属性包含与阶段连接在一起的字符串。 每个字符串代表子类的一个级别。 例如，IPM。注意是 IPM 的 IPM 的一个子类和超类别。Note.Private。 
  
这些属性必须包括 ASCII 字符到 127 32，并且必须以句点 (ASCII 46) 结尾。 排序和比较操作必须将其视为不区分大小写的字符串。 可能的最大长度为 255 个字符，但为了允许 MAPI 会议室追加限定符建议的原始长度保存下 128 个字符。 
  
每个邮件需要提供这些属性。 通常，创建一个新的邮件的客户端应用程序将其设置为[IMAPIFolder::CreateMessage](imapifolder-createmessage.md)成功返回。 但是，如果尚未设置该属性，当客户端调用[IMAPIProp::SaveChanges](imapiprop-savechanges.md)，消息存储应将其设置为 IPM。 
  
由 MAPI 定义的值是： 
  
```cpp
IPM.Note for a standard interpersonal message 
REPORT.<subject message class>.DR for a delivery report 
REPORT.<subject message class>.NDR for a nondelivery report 
REPORT.<subject message class>.IPNRN for a read report 
REPORT.<subject message class>.IPNNRN for a nonread report 
 
```

IPM 和 IPC 都应是超类仅，和一条消息，应具有至少一个要存储或提交之前追加的子类限定符。 邮件类的用法的详细信息，请参阅[Message Classes](mapi-message-classes.md)。 对于邮件类的必需的和可选属性的列表，请参阅[关于消息属性](message-properties-overview.md)的副标题。
  
自定义邮件类别可用于该邮件类仅保留范围内定义属性。 有关详细信息，请参阅[有关属性标识符](mapi-property-identifier-overview.md)。 
  
邮件类控件的接收文件夹传入消息存储在。 有关详细信息，请参阅[IMsgStore::GetReceiveFolderTable](imsgstore-getreceivefoldertable.md)方法。 
  
有关使用窗体和窗体服务器的邮件类的详细信息，请参阅[Choosing 邮件类](choosing-a-message-class.md)。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供了相关的 Exchange Server 协议规范参考。
    
[[MS OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)
  
> 处理邮件和附件的对象。
    
[[MS OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)
  
> 指定的属性和操作所允许的电子邮件消息对象。
    
[[MS OXOUM]](http://msdn.microsoft.com/library/2a0696c5-2caf-4f20-87fb-085db430afec%28Office.15%29.aspx)
  
> 指定的属性和操作所允许的表示语音邮件和传真消息。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含列为相关属性的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[映射到 MAPI 名称的规范属性名称](mapping-canonical-property-names-to-mapi-names.md)
  
[MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

