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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32332058"
---
# <a name="choosing-a-forms-property-set"></a>选择表单的属性集

**适用于**：Outlook 2013 | Outlook 2016 
  
在实现窗体服务器时, 需要为您的邮件类需要的每条信息提供一个属性。 这些属性可以是预定义的 MAPI 属性, 也可以是您定义的自定义属性。 有关使用属性的详细信息, 请参阅[MAPI 属性概述](mapi-property-overview.md)。
  
表单配置文件将包含表单服务器为要使用的客户端应用程序公开的属性列表, 但这并不一定是表单服务器所使用的全部属性列表。 客户端应用程序通常使用公开的属性, 使用户能够对文件夹中的邮件进行排序或以某种方式自定义其界面。
  
MAPI 具有大量预定义的属性, 足以满足大多数应用程序的要求。 但是, 有时会发生自定义邮件类需要 MAPI 未定义的属性。 您可以使用自定义属性来扩展 MAPI 的预定义属性集, 以确定您的表单服务器需要支持的任何特殊信息。
  
您可以使用下列任一方法来定义自定义属性:
  
- 选择属性的名称, 并使用[IMAPIProp:: GetIDsFromNames](imapiprop-getidsfromnames.md)方法获取它的属性标记。 调用此方法时使用的[IMAPIProp](imapipropiunknown.md)接口来自在创建邮件时传递给表单服务器的[IMessage](imessageimapiprop.md)指针。 请注意, 属性名称必须是宽字符字符串。 
    
- 自己定义自定义属性标记。 自定义属性标记必须在0x6800 到0x7BFF 的范围内。 此范围中的属性是特定于邮件类别的。
    
有关定义自定义属性的详细信息, 请参阅[定义新的 MAPI 属性](defining-new-mapi-properties.md)。
  
> [!NOTE]
> 包含邮件文本的表单服务器通常使用**PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) 属性来存储它。 如果您的表单服务器使用**PR_RTF_COMPRESSED**, 则还应确保**PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) 属性包含邮件文本的纯文本版本, 以便不支持 rtf 的客户端读取生成的邮件格式 (RTF) 消息文本。 
  
## <a name="see-also"></a>另请参阅

- [开发 MAPI 表单服务器](developing-mapi-form-servers.md)

