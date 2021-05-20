---
title: 支持传出邮件客户端责任中的格式化文本
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 7238b1a9-01ed-46a0-a625-26763323317d
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 01d5ae3fd06d570e15336fad9538f01e586cd0f3
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33431601"
---
# <a name="supporting-formatted-text-in-outgoing-messages-client-responsibilities"></a>支持传出邮件中的格式化文本：客户端责任

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
客户端应用程序为传出邮件设置 **PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) 属性 **、PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) 属性或 **PR_HTML** ([PidTagHtml](pidtaghtml-canonical-property.md)) 属性。 仅支持纯文本的客户端仅设置 **PR_BODY** 属性。 RTF (RTF) 客户端可能同时设置 **PR_BODY** 和 **PR_RTF_COMPRESSED** 属性，或仅 **设置 PR_RTF_COMPRESSED** 属性，具体取决于所使用的邮件存储提供程序。 HTML 感知客户端设置 **PR_HTML** 属性。 
  
客户端必须检查其邮件存储的 **PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) 属性以确定存储是否支持 RTF。 如果邮件存储无法识别 RTF，则 RTF 感知客户端将设置每个传出PR_BODY的 PR_RTF_COMPRESSED属性。 
  
如果邮件存储是 RTF 感知的，则只需 **PR_RTF_COMPRESSED** 属性。 
  
 **若要PR_RTF_COMPRESSED并确保同步过程在必要时发生，请设置 RTF 感知客户端**
  
1. 调用 [IMAPIProp：：OpenProperty](imapiprop-openproperty.md) 方法打开 PR_RTF_COMPRESSED **属性，** 同时设置 MAPI_CREATE 和 MAPI_MODIFY 标志。 MAPI_CREATE可确保任何新数据替换任何旧MAPI_MODIFY，并使您能够进行这些替换。 
    
2. 调用 [WrapCompressedRTFStream](wrapcompressedrtfstream.md)函数，如果邮件存储在其 PR_STORE_SUPPORT_MASK 属性中设置了 STORE_UNCOMPRESSED_RTF 位，则传递 **STORE_UNCOMPRESSED_RTF，** 以获取从 **OpenProperty** 返回的 **PR_RTF_COMPRESSED** 流的未压缩版本。
    
3. 将邮件文本数据写入从 **WrapCompressedRTFStream** 返回的未压缩流。
    
4. 提交并释放未压缩流和压缩流。
    
此时，如果邮件存储提供程序支持 RTF，则已完成所有必需操作。 如有必要，您可以依赖邮件存储提供程序来处理同步过程 **和 PR_BODY** 属性的创建。 但是，如果邮件存储提供程序不支持 RTF，则必须调用 [RTFSync](rtfsync.md) 函数以将文本与格式同步，并设置RTF_SYNC_RTF_CHANGED标记。 
  

