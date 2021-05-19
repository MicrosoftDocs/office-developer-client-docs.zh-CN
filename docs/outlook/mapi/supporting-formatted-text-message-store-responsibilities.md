---
title: 支持格式化短信存储责任
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: a97993c2-52e4-4b71-ac03-2c02d82447d8
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 502ba82279664638c8e7e4ae68f74df74758918d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33435514"
---
# <a name="supporting-formatted-text-message-store-responsibilities"></a>支持格式化文本：邮件存储责任

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
邮件存储提供程序使用 **PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) 属性来发布它们是否可以处理 RTF 格式 (RTF) 、HTML 文本，以及（如果它们可感知 RTF）是否以压缩格式还是未压缩格式存储格式化文本。 邮件存储提供程序通过设置 STORE_RTF_OK 位来指示它们具有 RTF 感知性，并且它们通过设置未压缩STORE_UNCOMPRESSED_RTF格式存储格式化文本。 邮件存储提供程序通过设置值位来指示它们STORE_HTML_OK HTML。
  
虽然 RTF 感知客户端检查 STORE_RTF_OK 位以确定邮件存储是否支持 RTF 很重要，但客户端不需要关注 RTF 感知存储格式化文本的格式。 
  
所有邮件存储必须支持非 RTF 感知客户端。 如果客户端已更改 PR_BODY **(** [PidTagBody](pidtagbody-canonical-property.md)) 而不更新 **PR_RTF_IN_SYNC** 或 **PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) ，则非 RTF 感知邮件存储必须在调用邮件 [的 IMAPIProp：：SaveChanges](imapiprop-savechanges.md)方法期间删除 **PR_RTF_IN_SYNC** (PidTagRtfInSync) 属性。 [](pidtagrtfinsync-canonical-property.md) 删除 **PR_RTF_IN_SYNC** 将导致PR_RTF_COMPRESSED RTF感知客户端下次调用 [RTFSync](rtfsync.md)时，从 **PR_BODY** 属性重新计算属性。 
  
大多数 RTF 感知邮件存储不由客户端提供消息文本;必须根据请求计算。 由于此计算非常耗时且成本较高，因此客户端应尽可能 **PR_RTF_COMPRESSED** 此计算。 若要计算 **PR_BODY** 属性，邮件存储提供程序必须取消压缩 **PR_RTF_COMPRESSED** 属性的内容并删除格式文本。 不支持属性的 **客户端PR_RTF_COMPRESSED需要** 针对每封邮件进行此计算。 
  
复制邮件时，不使用 **IMAPISupport：:D oCopyProps** 或 **IMAPISupport：:D oCopyTo** 方法的邮件存储提供程序会面临创建不包含任何内容的邮件的风险，如果它们的实现排除 **PR_BODY** 属性并依赖于 **PR_RTF_COMPRESSED**。 PR_RTF_COMPRESSED **中数据** 可能已损坏。 在复制操作中排除这些邮件内容属性之一之前，请检查是否损坏，如下所示： 
  
1. 如果属性 **PR_RTF_COMPRESSED** 压缩 RTF，则该属性已损坏。 
    
2. 如果 RTF 标头中的神奇值不是  _dwMagicCompressedRTF_ 或  _dwMagicUncompressedRTF，_ 则该属性已损坏。
    
使用支持方法的邮件存储提供程序无需考虑实现对邮件损坏 **PR_RTF_COMPRESSED检查;** MAPI 确保相应的属性存在且有效。 
  
邮件存储提供程序可以实施三种不同级别的 RTF 支持;MAPI 建议 RTF 感知邮件存储提供程序在中间或最高级别实现支持。 所有 RTF 感知邮件存储提供程序负责从传出邮件的 **PR_RTF_COMPRESSED** 中包含的数据生成 **PR_BODY，** 并调用 **RTFSync** 以同步传入邮件的文本和格式。 
  
下表介绍了这三个级别之间的差异。 
  
|**支持级别**|**说明**|
|:-----|:-----|
|低  <br/> |只要将更改保存到邮件，邮件存储提供程序就会调用 **RTFSync，** 并从 PR_RTF_COMPRESSED 中提取 **PR_BODY** 属性的数据 **，** 而不是要求客户端进行设置。 存储 **PR_BODY PR_RTF_COMPRESSED** 和库。  <br/> |
|中间  <br/> |邮件存储提供程序仅存储 PR_RTF_COMPRESSED **属性，****并在必要时** PR_BODY计算数据。  <br/> |
|高  <br/> |邮件存储提供程序既不 **存储PR_BODY** RTF 属性，也不存储辅助 RTF 属性。 当邮件文本已更改且格式保持不变或传输提供程序下载新邮件时，将调用 **RTFSync。**  <br/> |
   

