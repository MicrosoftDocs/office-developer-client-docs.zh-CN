---
title: 写入未压缩的格式文本
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
# <a name="writing-uncompressed-formatted-text"></a>写入未压缩的格式文本

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
准备发送带格式文本的邮件时，请将邮件的 **PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) 属性设置为压缩文本或未压缩文本。 在 PR_RTF_COMPRESSED **属性中** 写入压缩文本是一项占用大量 CPU 的操作，并且会显著影响性能。 
  
若要提高发送格式化邮件的性能，请执行以下任一操作：
  
- 升级 CPU，这是一种并不总是能实现的解决方案。
    
    - 或 -
    
- 在属性中写入 **未压缩PR_RTF_COMPRESSED** 文本。 
    
使用 **未压缩PR_RTF_COMPRESSED** 设置压缩文本的过程与使用压缩文本设置过程相同，只有一个例外。 调用 [WrapCompressedRTFStream](wrapcompressedrtfstream.md)时，在  _ulFlags_ STORE_UNCOMPRESSED_RTF设置值标记。 设置未压缩文本的缺点是增加邮件的大小。 
  

