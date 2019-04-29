---
title: 写入未压缩的格式化文本
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: c78d4d00-bc31-4d0b-8af0-dd0b8f3febfe
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 7ad12fbc9671d0a21c6c6e6d4615b45a17a72fce
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33426322"
---
# <a name="writing-uncompressed-formatted-text"></a>写入未压缩的格式化文本

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
准备发送带格式文本的邮件时, 请将邮件的**PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) 属性设置为 "已压缩" 或 "未压缩文本"。 在**PR_RTF_COMPRESSED**属性中写入压缩的文本是一项非常耗费 CPU 的操作, 可能会严重影响性能。 
  
若要提高发送格式化邮件的性能, 请执行以下操作之一:
  
- 升级 CPU, 这是一种并非始终 plausible 的解决方案。
    
    - 和
    
- 在**PR_RTF_COMPRESSED**属性中写入未压缩的文本。 
    
使用未压缩的文本设置**PR_RTF_COMPRESSED**的过程与使用压缩的文本设置它的过程相同, 但有一个例外。 调用[WrapCompressedRTFStream](wrapcompressedrtfstream.md)时, 请在_ulFlags_参数中设置 STORE_UNCOMPRESSED_RTF 标志。 设置未压缩的文本的缺点在于它会增加邮件大小。 
  

