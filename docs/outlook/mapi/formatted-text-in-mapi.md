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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33408087"
---
# <a name="formatted-text-in-mapi"></a>MAPI 中的格式化文本

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
可以使用纯文本或格式化文本存储和传输邮件文本。 格式化文本通过更改消息文本的外观（例如，使用一个或多个字体、字号或文本颜色）来增强消息文本。 建议所有客户端以及所有邮件存储提供程序尽可能支持格式化文本。 支持邮件中的格式化文本通过提高邮件可读性并简化邮件处理来增加价值。
  
格式化文本可以通过多种方式实现。 最常见的使用 RTF 格式格式 (RTF) 。 MAPI 定义用于存储邮件文本信息的三个可传输属性 **：PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) 表示纯文本 **，PR_HTML** ([PidTagHtml](pidtaghtml-canonical-property.md)) 表示 HTML，PR_RTF_COMPRESSED ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) 表示已压缩的 RTF 文本。  由于邮件文本的格式版本可以比不带格式的版本大两倍，因此在将 RTF 文本与邮件一起传输并存储在 PR_RTF_COMPRESSED 属性中之前 **，会** 先进行压缩。 当应该在屏幕上显示消息时，使用 MAPI 提供的实用工具函数取消压缩消息。 
  
MAPI 定义这两个邮件文本属性和机制，以便 RTF 感知客户端可以与不支持格式化文本的客户端和邮件系统进行互操作。
  
### 

[同步文本和格式](synchronizing-text-and-formatting.md)
  
> 介绍如何保持 RTF 邮件文本与格式同步。
    
[支持传出邮件中的格式化文本：客户端责任](supporting-formatted-text-in-outgoing-messages-client-responsibilities.md)
  
> 介绍客户端应用程序在支持传出邮件中的格式化文本方面的责任。
    
[支持传入邮件中的格式化文本：客户端责任](supporting-formatted-text-in-incoming-messages-client-responsibilities.md)
  
> 介绍客户端应用程序在支持传入邮件中的格式化文本方面的责任。
    
[支持格式化文本：邮件存储责任](supporting-formatted-text-message-store-responsibilities.md)
  
> 描述邮件存储支持格式化文本的责任。
    
[支持格式化文本：呈现附件](supporting-formatted-text-rendering-attachments.md)
  
> 介绍如何选择附件的呈现位置。
    
[支持格式化文本：网关责任](supporting-formatted-text-gateway-responsibilities.md)
  
> 描述网关对传出和传入格式化短信的责任。
    

