---
title: 在传入邮件中支持格式化文本客户端责任
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
# <a name="supporting-formatted-text-in-incoming-messages-client-responsibilities"></a>在传入邮件中支持格式化文本: 客户端责任

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
当邮件在邮件系统之间传输时, MAPI 后台处理程序会确保 rtf 格式设置与邮件文本保持同步。 MAPI 后台处理程序从传递给传输提供程序的邮件的已包装版本中调用[RTFSync](rtfsync.md)函数。 传输提供程序通过调用[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)方法来保存对邮件所做的更改, 然后将其路由到新的收件人。 
  
当收件人的 RTF 感知客户端应用程序打开邮件以显示文本时, 它必须将文本与格式设置同步并打开**PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) 或**PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)), 具体取决于可用的属性。
  
 **打开邮件、支持 RTF 的客户端**
  
1. 如果邮件存储区不支持 RTF, 则调用**RTFSync**以将邮件文本与格式同步。 如果**PR_RTF_IN_SYNC** ([PidTagRtfInSync](pidtagrtfinsync-canonical-property.md)) 属性缺失或设置为 FALSE, 则应在_ulFlags_参数中传递 RTF_SYNC_BODY_CHANGED 标志。 处理 RTF 格式的邮件存储区的客户端无需进行**RTFSync**调用, 因为邮件存储负责处理它。 
    
2. 如果邮件文本已更新, 则调用[IMAPIProp:: SaveChanges](imapiprop-savechanges.md) 。 
    
3. 调用[IMAPIProp:: OpenProperty](imapiprop-openproperty.md)以打开**PR_RTF_COMPRESSED**属性。 如果**PR_RTF_COMPRESSED**不可用, 则应改为打开**PR_BODY**属性以显示邮件内容。 
    
4. 调用[WrapCompressedRTFStream](wrapcompressedrtfstream.md)函数以创建压缩的 RTF 数据的未压缩版本 (如果可用)。 
    
5. 向用户显示未压缩的 RTF 数据或纯文本数据。
    
 **RTFSync**返回一个布尔值, 该值指示是否已更新邮件。 如果此值返回 TRUE, 则在某个时刻调用**SaveChanges**以使更新成为永久更新。 不需要在**RTFSync**返回后立即执行该调用。 
  
> [!NOTE]
> 由于在您接收到格式化文本之前很多组件会对其进行处理, 因此可能会损坏。 此损坏可能来自邮件存储提供程序、第三方应用程序、网关或传输错误。 
  

