---
title: 支持格式化的短信存储任务
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
# <a name="supporting-formatted-text-message-store-responsibilities"></a>支持格式化文本: 邮件存储责任

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
邮件存储提供程序使用**PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) 属性来发布它们是否可以处理 rtf 格式 (rtf)、HTML 文本, 如果它们是 rtf 格式, 则无论它们是否将格式化文本存储在压缩或解压缩格式。 邮件存储提供程序通过设置 STORE_RTF_OK 位来指示它们是 RTF 感知的, 并通过设置 STORE_UNCOMPRESSED_RTF 位将格式文本存储在未压缩的表单中。 邮件存储提供程序通过设置 STORE_HTML_OK 位来指示它们是 HTML 感知的。
  
虽然支持 rtf 的客户端检查 STORE_RTF_OK 位以确定邮件存储区是否支持 RTF, 这一点很重要, 但客户并不需要考虑 rtf 感知存储的格式化文本的格式。 
  
所有邮件存储区都必须支持非 RTF 感知客户端。 如果客户端已更改**PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)), 则非 RTF 邮件存储必须在调用邮件的[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)方法过程中删除**PR_RTF_IN_SYNC** ([PidTagRtfInSync](pidtagrtfinsync-canonical-property.md)) 属性, 而不更新**PR_RTF_IN_SYNC**或**PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md))。 删除**PR_RTF_IN_SYNC**将导致**PR_RTF_COMPRESSED**属性在下次调用 RTF 的客户端时从**PR_BODY**属性重新计算。 [](rtfsync.md) 
  
大多数 RTF 感知邮件存储都不是由客户端提供的邮件文本;必须按要求计算。 由于此计算耗费时间且成本高昂, 因此客户端应尽可能使用**PR_RTF_COMPRESSED** 。 若要计算**PR_BODY**属性, 邮件存储提供程序必须对**PR_RTF_COMPRESSED**属性的内容进行解压缩并删除 rtf 格式。 不支持**PR_RTF_COMPRESSED**属性的客户端要求对每封邮件进行此计算。 
  
在复制邮件时, 不使用 IMAPISupport 的邮件存储提供程序 **::D ocopyprops**或**IMAPISupport::D ocopyto**方法运行创建不包含内容的邮件的风险 (如果其实现排除了**PR_BODY** )。属性并依赖**PR_RTF_COMPRESSED**。 **PR_RTF_COMPRESSED**属性中的数据可能已损坏。 在复制操作中排除这些邮件内容的任何属性之前, 请检查是否有损坏, 如下所示: 
  
1. 如果**PR_RTF_COMPRESSED**的值不大于压缩的 RTF, 则该属性已损坏。 
    
2. 如果 RTF 标头中的幻值不是_dwMagicCompressedRTF_或_dwMagicUncompressedRTF_, 则该属性已损坏。
    
使用支持方法的邮件存储提供程序不需要考虑为**PR_RTF_COMPRESSED**损坏实施检查;MAPI 可确保适当的属性存在且有效。 
  
邮件存储提供程序可以实现三种不同级别的 RTF 支持;MAPI 建议 RTF 感知邮件存储提供程序在中间或最高级别实现其支持。 所有 RTF 感知邮件存储区提供程序负责从**PR_RTF_COMPRESSED**中包含的数据生成**PR_BODY** , 并调用**RTFSync**以同步传入邮件上的文本和格式设置。 
  
下表介绍了这三种级别之间的差异。 
  
|**支持级别**|**说明**|
|:-----|:-----|
|低  <br/> |只要将更改保存到邮件并从**PR_RTF_COMPRESSED**中提取**PR_BODY**属性的数据, 邮件存储提供程序就会调用**RTFSync** , 而不是要求客户端对其进行设置。 同时存储**PR_BODY**和**PR_RTF_COMPRESSED** 。  <br/> |
|中间  <br/> |邮件存储提供程序仅存储**PR_RTF_COMPRESSED**属性 (必要时计算**PR_BODY** )。  <br/> |
|高  <br/> |邮件存储提供程序既不存储**PR_BODY** , 也不存储辅助 RTF 属性。 当邮件文本已更改且格式设置保持不变或在传输提供程序下载新邮件时, 将调用**RTFSync** 。  <br/> |
   

