---
title: MAPI 中的格式化文本
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 4d0ff834-253b-4e8c-a5be-6e4745a2a66c
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 7f37d65e4beb328c2c92cf0c2ab28586af6bee45
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32327466"
---
# <a name="formatted-text-in-mapi"></a>MAPI 中的格式化文本

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
可以使用纯文本或带格式的文本来存储和传输邮件的文本。 格式化文本通过更改其外观 (例如, 一个或多个字体、字体大小或文本颜色) 来增强邮件文本。 建议所有的客户端和所有邮件存储提供程序 (如果可能) 都支持格式化文本。 在邮件中支持格式化文本通过提高邮件可读性和简化邮件处理来增加价值。
  
可以通过多种方式实现格式化文本。 最常见的方法是使用格式文本格式 (rtf)。 MAPI 定义了用于保存邮件文本信息的三个传输属性: **PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) 用于纯文本、 **PR_HTML** ([PidTagHtml](pidtaghtml-canonical-property.md)) for HTML 和**PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)), 用于已压缩的 rtf 文本。 由于邮件文本的格式设置版本的大小可以是不带格式的版本, 因此 RTF 文本在与邮件一起传输并存储在**PR_RTF_COMPRESSED**属性中之前会进行压缩。 在屏幕上显示邮件的时间时, 将使用 MAPI 提供的实用工具函数对其进行解压缩。 
  
MAPI 定义了这两种邮件文本属性和在它们之间进行转换的机制, 以便 RTF 感知客户端可以与不支持格式化文本的客户端和邮件系统进行交互操作。
  
### 

[同步文本和格式设置](synchronizing-text-and-formatting.md)
  
> 介绍如何将 RTF 邮件文本与格式保持同步。
    
[在待发邮件中支持格式化文本: 客户端责任](supporting-formatted-text-in-outgoing-messages-client-responsibilities.md)
  
> 介绍在传出邮件中支持格式化文本的客户端应用程序责任。
    
[在传入邮件中支持格式化文本: 客户端责任](supporting-formatted-text-in-incoming-messages-client-responsibilities.md)
  
> 介绍在传入邮件中支持格式化文本的客户端应用程序责任。
    
[支持格式化文本: 邮件存储责任](supporting-formatted-text-message-store-responsibilities.md)
  
> 介绍用于支持格式化文本的邮件存储职责。
    
[支持格式化文本: 呈现附件](supporting-formatted-text-rendering-attachments.md)
  
> 介绍如何选择呈现附件的位置。
    
[支持格式化文本: 网关责任](supporting-formatted-text-gateway-responsibilities.md)
  
> 介绍传出和传入的格式化短信的网关职责。
    

