---
title: 支持在传出邮件客户端责任的带格式的文本
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 7238b1a9-01ed-46a0-a625-26763323317d
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 975dd172b6ad342351f014d0966d62a150f713c6
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22571288"
---
# <a name="supporting-formatted-text-in-outgoing-messages-client-responsibilities"></a>支持待发邮件中的格式化文本：客户端责任

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
客户端应用程序设置的**PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) 属性、 **PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) 属性或的传出消息的**PR_HTML** ([PidTagHtml](pidtaghtml-canonical-property.md)) 属性。 仅支持纯文本的客户端设置仅**PR_BODY**属性。 Rtf 格式 (RTF)-请注意，客户端可能将**PR_BODY**和**PR_RTF_COMPRESSED**属性，或者仅**PR_RTF_COMPRESSED**，具体取决于消息存储提供程序正在使用。 HTML 感知客户端设置**PR_HTML**属性。 
  
非常重要的检查其消息存储库**PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) 属性以确定是否的存储支持 RTF 的客户端。 如果消息存储不是 RTF 感知的 RTF 感知客户端设置为每个传出消息的**PR_BODY**和**PR_RTF_COMPRESSED**属性。 
  
如果消息存储为 RTF 感知的仅将**PR_RTF_COMPRESSED**属性需要设置。 
  
 **若要设置 PR_RTF_COMPRESSED 并确保同步过程在发生作为有必要，RTF 感知客户端**
  
1. 调用[IMAPIProp::OpenProperty](imapiprop-openproperty.md)方法以打开**PR_RTF_COMPRESSED**属性，设置的 MAPI_CREATE 和 MAPI_MODIFY 标志。 MAPI_CREATE 确保新的任何数据替换任何旧数据和 MAPI_MODIFY 使您能够进行这些替换。 
    
2. 调用[WrapCompressedRTFStream](wrapcompressedrtfstream.md)函数，如果消息存储在其**PR_STORE_SUPPORT_MASK**属性，以获取**PR_RTF_COMPRESSED 未压缩的版本中设置 STORE_UNCOMPRESSED_RTF 位传递 STORE_UNCOMPRESSED_RTF**从**OpenProperty**返回流。
    
3. 写入到未压缩流**WrapCompressedRTFStream**从返回的消息文本数据。
    
4. 提交并释放未压缩和压缩流。
    
此时，消息存储提供程序支持 RTF，如果您已完成所有必需的。 如有必要，可以依赖处理同步过程和**PR_BODY**属性中，创建消息存储提供程序。 但是，如果消息存储提供程序不支持 RTF，您必须调用[RTFSync](rtfsync.md)函数同步带格式的文本设置 RTF_SYNC_RTF_CHANGED 标志。 
  

