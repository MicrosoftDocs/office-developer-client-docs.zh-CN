---
title: 在传出邮件中支持格式化的文本客户端责任
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
# <a name="supporting-formatted-text-in-outgoing-messages-client-responsibilities"></a>在待发邮件中支持格式化文本: 客户端责任

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
客户端应用程序设置**PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) 属性、 **PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) 属性或传出邮件的**PR_HTML** ([PidTagHtml](pidtaghtml-canonical-property.md)) 属性。 仅支持纯文本的客户端仅设置**PR_BODY**属性。 rtf 格式 (rtf) 感知客户端可以设置**PR_BODY**和**PR_RTF_COMPRESSED**属性, 也可以仅设置**PR_RTF_COMPRESSED**, 具体取决于所使用的邮件存储提供程序。 HTML 感知客户端设置**PR_HTML**属性。 
  
客户端必须检查其邮件存储的**PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) 属性以确定存储是否支持 RTF, 这一点非常重要。 如果邮件存储区不能识别 rtf, 则 rtf 感知客户端会为每个传出邮件设置**PR_BODY**和**PR_RTF_COMPRESSED**属性。 
  
如果邮件存储区是 RTF 的, 则只需设置**PR_RTF_COMPRESSED**属性。 
  
 **设置 PR_RTF_COMPRESSED 并确保同步过程在必要时进行; RTF 感知客户端**
  
1. 调用[IMAPIProp:: OpenProperty](imapiprop-openproperty.md)方法以打开**PR_RTF_COMPRESSED**属性, 同时设置 MAPI_CREATE 和 MAPI_MODIFY 标志。 MAPI_CREATE 确保任何新数据将替换任何旧的数据和 MAPI_MODIFY, 使您能够进行这些替换。 
    
2. 调用[WrapCompressedRTFStream](wrapcompressedrtfstream.md)函数, 如果邮件存储区在其**PR_STORE_SUPPORT_MASK**属性中设置了 STORE_UNCOMPRESSED_RTF 位, 则传递 STORE_UNCOMPRESSED_RTF, 以获取 PR_RTF_COMPRESSED 的未压缩版本。 **** 从**OpenProperty**返回的流。
    
3. 将邮件文本数据写入从**WrapCompressedRTFStream**返回的未压缩流。
    
4. 提交并释放未压缩和压缩的流。
    
在这种情况下, 如果邮件存储区提供程序支持 RTF, 则您已完成所有必需的操作。 您可以根据邮件存储提供程序来处理同步过程和创建**PR_BODY**属性 (如有必要)。 但是, 如果邮件存储区提供程序不支持 RTF, 则必须调用[RTFSync](rtfsync.md)函数以将文本与格式设置同步, 设置 RTF_SYNC_RTF_CHANGED 标志。 
  

