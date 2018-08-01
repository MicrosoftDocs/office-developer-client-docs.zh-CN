---
title: 选择窗体的属性集
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 5680fed2-b2e7-4c4b-9ba8-2c497b9c433c
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 456ef036b26fd8b9840d33f0f699474c3a6ce127
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774665"
---
# <a name="choosing-a-forms-property-set"></a>选择窗体的属性集

**适用于**： Outlook 
  
实现表单服务器时，您需要具有对每个邮件类所需的信息的属性。 这些属性可以是预定义的 MAPI 属性，也可以在您定义的自定义属性。 有关使用属性的详细信息，请参阅[MAPI 属性概述](mapi-property-overview.md)。
  
您窗体的配置文件将包含客户端应用程序可以使用，公开您的窗体服务器的属性列表，但这不需要在整个窗体服务器使用的属性列表。 客户端应用程序通常使用公开的属性使用户能够排序文件夹中的邮件或自定义其接口以某种方式。
  
MAPI 都有一大的预定义满足大多数应用程序的属性。 但是，将自定义邮件类别时需要 MAPI 未定义的属性的时间。 您可以使用自定义属性扩展 MAPI 预定义的一组属性的窗体服务器需要支持的任何特殊信息。
  
您可以使用以下方法来定义自定义属性之一：
  
- 为属性选择一个名称并使用[IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md)方法为其获取属性标记。 通过其调用此方法的[IMAPIProp](imapipropiunknown.md)接口来自时创建邮件传递到窗体服务器[IMessage](imessageimapiprop.md)指针。 请注意，在属性名称必须范围个字符的字符串。 
    
- 定义您自己的自定义属性标记。 自定义属性标记必须在范围内通过 0x7BFF 0x6800。 此范围中的属性是邮件类特定。
    
有关定义自定义属性的详细信息，请参阅[定义新的 MAPI 属性](defining-new-mapi-properties.md)。
  
> [!NOTE]
> 通常具有消息文本的窗体服务器使用**PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) 属性以将其存储。 如果窗体服务器使用**PR_RTF_COMPRESSED**，它还应**PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) 属性包含纯文本邮件正文，版客户端不支持格式文本读取生成消息的情况下消息文本设置格式 (RTF)。 
  
## <a name="see-also"></a>另请参阅

- [开发 MAPI 表单服务器](developing-mapi-form-servers.md)

