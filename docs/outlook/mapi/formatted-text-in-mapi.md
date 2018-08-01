---
title: MAPI 中的格式化文本
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 4d0ff834-253b-4e8c-a5be-6e4745a2a66c
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 6b82a755cbf2c8bd0f1d3676d4560e131dce3bd2
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774987"
---
# <a name="formatted-text-in-mapi"></a>MAPI 中的格式化文本

  
  
**适用于**： Outlook 
  
消息的文本可存储和传输使用纯文本或带格式的文本。 带格式的文本更改其与，例如，一个或多个字体、 字号或文本颜色的外观，从而增强了消息文本。 建议的所有客户端和所有消息存储提供程序，只要有可能，都支持带格式的文本。 支持带格式的文本消息中添加通过改进消息可读性和进行消息处理更容易、 更高效的值。
  
可以采用多种方式实现格式化的文本。 最常用的方法是使用富文本格式 (RTF)。 MAPI 定义三个可传送属性用于保存消息文本信息： **PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) 纯文本， **PR_HTML** ([PidTagHtml](pidtaghtml-canonical-property.md)) HTML，和**PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) 的 RTF 已压缩的文本。 消息文本的格式的版本可以两次版本，而不的格式，因为它是与邮件传输和存储在**PR_RTF_COMPRESSED**属性之前被压缩 RTF 的文本。 在屏幕上显示邮件时，时，未压缩使用 MAPI 提供的实用工具函数。 
  
MAPI 定义这两个邮件文本属性和它们之间的转换的机制，以便 RTF 感知客户端可以与客户端和不支持的邮件系统互操作格式化文本。
  
### 

[同步文本和格式设置](synchronizing-text-and-formatting.md)
  
> 介绍如何保留 RTF 邮件文本的格式与同步。
    
[支持待发邮件中的格式化文本：客户端责任](supporting-formatted-text-in-outgoing-messages-client-responsibilities.md)
  
> 介绍在传出消息中支持带格式的文本的客户端应用程序责任。
    
[支持传入邮件中的格式化文本：客户端责任](supporting-formatted-text-in-incoming-messages-client-responsibilities.md)
  
> 介绍客户端应用程序接收的邮件中支持带格式的文本的责任。
    
[支持格式化文本：邮件存储区责任](supporting-formatted-text-message-store-responsibilities.md)
  
> 介绍支持带格式的文本的消息存储责任。
    
[支持格式化文本：显示附件](supporting-formatted-text-rendering-attachments.md)
  
> 介绍如何选择其中呈现附件。
    
[支持格式化文本：网关责任](supporting-formatted-text-gateway-responsibilities.md)
  
> 介绍传出和传入格式化的文本邮件的网关责任。
    

