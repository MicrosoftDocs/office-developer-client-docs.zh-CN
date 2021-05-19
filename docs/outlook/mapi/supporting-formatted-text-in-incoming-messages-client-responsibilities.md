---
title: 支持传入邮件客户端责任中的格式化文本
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 79727700-5ef1-4a29-9ed0-fd46c7de3202
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 7f3cf5b245bdcd2c2707f0e2028d52a15c7e0f6b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33434499"
---
# <a name="supporting-formatted-text-in-incoming-messages-client-responsibilities"></a>支持传入邮件中的格式化文本：客户端责任

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
在邮件系统之间传输邮件时，MAPI 后台处理程序确保格式文本格式与邮件文本保持同步。 MAPI 后台处理程序从传递给传输提供程序的邮件的封装版本中调用 [RTFSync](rtfsync.md) 函数。 传输提供程序通过调用 [IMAPIProp：：SaveChanges](imapiprop-savechanges.md) 方法保存对邮件所做的更改，然后将它路由到新收件人。 
  
当收件人的 RTF 感知客户端应用程序打开邮件以显示文本时，它必须将文本与格式同步，并打开 **PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) 或 **PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) ，具体取决于可用的属性。
  
 **若要打开消息，请识别 RTF 的客户端**
  
1. 如果邮件存储无法识别 RTF，则调用 **RTFSync** 将邮件文本与格式同步。 如果 PR_RTF_IN_SYNC ([PidTagRtfIn) Sync](pidtagrtfinsync-canonical-property.md)属性缺失或设置为 FALSE，则 RTF_SYNC_BODY_CHANGED 标记应在 _ulFlags_ 参数中传递。 使用 RTF 感知邮件存储的客户端不需要进行 **RTFSync** 调用，因为邮件存储会处理它。 
    
2. 如果消息文本已更新，则调用[IMAPIProp：：SaveChanges。](imapiprop-savechanges.md) 
    
3. 调用 [IMAPIProp：：OpenProperty](imapiprop-openproperty.md) 以打开 **PR_RTF_COMPRESSED** 属性。 如果 **PR_RTF_COMPRESSED** 不可用，应打开 **PR_BODY** 属性以显示邮件内容。 
    
4. 调用 [WrapCompressedRTFStream](wrapcompressedrtfstream.md) 函数以创建压缩 RTF 数据的未压缩版本（如果可用）。 
    
5. 向用户显示未压缩的 RTF 数据或纯文本数据。
    
 **RTFSync** 返回一个布尔 值，该值指示消息是否已更新。 如果此值返回 TRUE，则 **有时调用 SaveChanges** 以永久更新。 在 **RTFSync** 返回后，无需立即进行调用。 
  
> [!NOTE]
> 由于许多组件在接收格式化文本之前会处理该文本，因此存在损坏的可能性。 此损坏可能来自邮件存储提供程序、第三方应用程序、网关或传输错误。 
  

