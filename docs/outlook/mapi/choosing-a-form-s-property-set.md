---
title: 选择表单的属性集
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 5680fed2-b2e7-4c4b-9ba8-2c497b9c433c
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: d983b71c7c92c395740a8ae6f6d3666a8bc2c0c7
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33407191"
---
# <a name="choosing-a-forms-property-set"></a>选择表单的属性集

**适用于**：Outlook 2013 | Outlook 2016 
  
当您实现表单服务器时，您需要为邮件类需要的每个信息段设置一个 属性。 这些属性可以是预定义的 MAPI 属性，也可以是定义的自定义属性。 有关使用属性的信息，请参阅 [MAPI 属性概述](mapi-property-overview.md)。
  
表单配置文件将包含表单服务器公开的属性列表，供客户端应用程序使用，但这不是表单服务器使用的属性的整个列表。 客户端应用程序通常使用公开的属性来允许用户对文件夹中的邮件进行排序或以某种方式自定义其界面。
  
MAPI 具有一大组预定义属性，这对于大多数应用程序都足够。 但是，有时自定义邮件类需要 MAPI 未定义的属性。 您可以使用自定义属性来扩展窗体服务器需要支持的任何特殊信息的 MAPI 预定义属性集。
  
可以使用以下任一方法来定义自定义属性：
  
- 选择属性的名称，并使用 [IMAPIProp：：GetIDsFromNames](imapiprop-getidsfromnames.md) 方法获取该属性的属性标记。 通过 [调用此方法的 IMAPIProp](imapipropiunknown.md) 接口来自创建消息时传递给表单服务器的 [IMessage](imessageimapiprop.md) 指针。 请注意，属性名称必须是宽字符字符串。 
    
- 自己定义自定义属性标记。 自定义属性标记的范围必须0x6800到0x7BFF。 此范围中的属性特定于邮件类。
    
有关定义自定义属性的信息，请参阅 [定义新的 MAPI 属性](defining-new-mapi-properties.md)。
  
> [!NOTE]
> 具有邮件文本的表单服务器通常使用 PR_RTF_COMPRESSED  ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) 属性来存储它。 如果您的表单服务器使用 **PR_RTF_COMPRESSED**，它还应确保 **PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) 属性包含仅文本版本的邮件文本，以防生成的邮件由不支持 RTF (RTF) 格式邮件文本的客户端读取。 
  
## <a name="see-also"></a>另请参阅

- [开发 MAPI 表单服务器](developing-mapi-form-servers.md)

