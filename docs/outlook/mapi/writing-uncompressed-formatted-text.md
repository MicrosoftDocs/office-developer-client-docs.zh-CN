---
title: 编写未压缩的格式化文本
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: c78d4d00-bc31-4d0b-8af0-dd0b8f3febfe
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 9baf3397255d6138caaad84de5ff5621bd6c9555
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779115"
---
# <a name="writing-uncompressed-formatted-text"></a>编写未压缩的格式化文本

  
  
**适用于**： Outlook 
  
在准备要发送带格式的文本消息时，以下任意会设置为压缩或未压缩文本的消息的**PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) 属性。 **PR_RTF_COMPRESSED**属性中写入压缩的文本频繁的 CPU 密集型操作，可以显著影响性能。 
  
以提高性能的发送格式的邮件，或者：
  
- 升级 CPU，并不总是貌似合理的解决方案。
    
    - 或者-
    
- 写入**PR_RTF_COMPRESSED**属性中的未压缩的文本。 
    
设置**PR_RTF_COMPRESSED**未压缩文本的过程是相同设置压缩文本，有一个例外。 调用[WrapCompressedRTFStream](wrapcompressedrtfstream.md)时, _ulFlags_参数中设置 STORE_UNCOMPRESSED_RTF 标志。 设置未压缩的文本有缺点，它会增加邮件的大小。 
  

