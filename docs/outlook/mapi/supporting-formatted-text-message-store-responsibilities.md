---
title: 支持格式化的文本消息存储职责
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: a97993c2-52e4-4b71-ac03-2c02d82447d8
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 301ebbf8e7a3e2a2deb303af5b198fd11511d495
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778895"
---
# <a name="supporting-formatted-text-message-store-responsibilities"></a>支持的格式文本： 消息存储职责

  
  
**适用于**： Outlook 
  
消息存储提供程序使用**PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) 属性可发布是否能够处理富文本格式 (RTF)、 HTML 文本和 RTF 感知时是否它们存储中的格式化的文本压缩或未压缩格式。 消息存储提供程序指示它们是 RTF 感知通过设置 STORE_RTF_OK 位以及它们存储格式化的文本未压缩窗体中通过设置 STORE_UNCOMPRESSED_RTF 位。 消息存储提供程序表明它们是 HTML 感知通过设置 STORE_HTML_OK 位。
  
重要要检查的位以确定的消息存储支持 RTF STORE_RTF_OK RTF 感知客户端时，就不需要对客户端关心 RTF 感知存储格式化文本的格式。 
  
所有邮件存储必须都支持非 RTF 感知客户端。 非 RTF 注意消息存储必须消息的[IMAPIProp::SaveChanges](imapiprop-savechanges.md)方法在呼叫过程中删除**PR_RTF_IN_SYNC** ([PidTagRtfInSync](pidtagrtfinsync-canonical-property.md)) 属性，如果客户端已而不更改**PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md))更新**PR_RTF_IN_SYNC**或**PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md))。 删除**PR_RTF_IN_SYNC**使重新计算**PR_BODY**属性中的下次 RTF 感知客户端调用[RTFSync](rtfsync.md) **PR_RTF_COMPRESSED**属性。 
  
大多数 RTF 感知的消息存储由客户端; 不是授予消息文本它必须请求计算。 因为此计算非常耗时且成本低，客户端应使用**PR_RTF_COMPRESSED**尽可能。 若要计算的**PR_BODY**属性，消息存储提供程序必须解压缩**PR_RTF_COMPRESSED**属性的内容并删除格式文本格式。 不支持**PR_RTF_COMPRESSED**属性的客户端需要对每个消息执行此计算。 
  
当复制邮件，消息存储提供程序不使用运行的与任何内容创建一条消息，如果其实现排除**PR_BODY**风险**IMAPISupport::DoCopyProps**或**IMAPISupport::DoCopyTo**方法属性和依赖于**PR_RTF_COMPRESSED**。 很可能已损坏的**PR_RTF_COMPRESSED**属性中的数据。 之前不包括复制操作这些消息内容属性之一，检查已损坏，如下所示： 
  
1. 如果不大于压缩 RTF **PR_RTF_COMPRESSED**的值，该属性已损坏。 
    
2. 如果在 RTF 标题魔术值不是_dwMagicCompressedRTF_或_dwMagicUncompressedRTF_，该属性已损坏。
    
消息存储提供程序使用方法需要不考虑实现**PR_RTF_COMPRESSED**损坏; 检查的支持MAPI 确保的相应属性存在，且有效。 
  
有三个不同级别的消息存储提供程序可以实现; RTF 支持MAPI 建议 RTF 感知消息存储提供程序实施他们的支持在中间或最高级别。 所有 RTF 感知消息存储提供程序的传出邮件**PR_RTF_COMPRESSED**中包括的数据从生成**PR_BODY**和**RTFSync**调用同步文本和传入消息的格式。 
  
以下三个级别之间的差异如下表所述。 
  
|**支持级别**|**说明**|
|:-----|:-----|
|Low  <br/> |消息存储提供程序调用**RTFSync** ，只要更改将保存到一条消息，并从**PR_RTF_COMPRESSED**而不是要求客户端将其设置为提取**PR_BODY**属性的数据。 **PR_BODY**和**PR_RTF_COMPRESSED**存储。  <br/> |
|居中  <br/> |消息存储提供程序存储仅**PR_RTF_COMPRESSED**属性，计算**PR_BODY**在必要时。  <br/> |
|High  <br/> |消息存储提供程序存储区，既未**PR_BODY**或辅助 RTF 属性。 **RTFSync**称为已更改消息文本和格式保持不变时或下载新邮件时由传输提供程序。  <br/> |
   

