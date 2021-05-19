---
title: 使用 TNEF 对邮件编码
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 6b86d9a9-6876-4885-ae1e-8571b25b85cc
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: cdaa03cfbc0bbd0fcf6a320ecf8fae9f372d5781
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32336699"
---
# <a name="encoding-a-message-with-tnef"></a>使用 TNEF 对邮件编码

**适用于**：Outlook 2013 | Outlook 2016 
  
提交邮件时，传输提供程序可以创建用于在传输期间包含邮件的文件。 接下来 [，IStream](https://msdn.microsoft.com/library/aa380034%28VS.85%29.aspx) 接口包装在文件周围。 然后，传输提供程序使用 [ITnef](itnefiunknown.md) 方法以标记格式将邮件属性写入流，使接收传输提供程序可以轻松地解码这些属性。 
  
**在单个文件中表示整个邮件**
  
1. 通过向[OpenTnefStreamEx](opentnefstreamex.md)函数传递[IStream](https://msdn.microsoft.com/library/aa380034%28VS.85%29.aspx)对象和消息来获取 TNEF 对象。 
    
2. 通过调用 [IMAPIProp：：GetPropList](imapiprop-getproplist.md) 方法获取邮件的所有已定义属性的列表。 
    
3. 使用 [IMAPIProp](imapipropiunknown.md) 方法排除邮件系统支持的所有属性。 在适当的时间，以邮件系统所需的格式将这些属性写入邮件系统。 
    
4. 调用 [ITnef：：AddProps](itnef-addprops.md) 对其余属性（包括所有附件）进行编码。 
    
5. 在添加 [所有请求的属性后，调用 ITnef：：Finish](itnef-finish.md) 方法将邮件编码到 TNEF 流中。 
    
6. 调用 [ITnef：：OpenTaggedBody](itnef-opentaggedbody.md) 方法以获取带标记的邮件文本。 此标记文本使用 OLE [IStream](https://msdn.microsoft.com/library/aa380034%28VS.85%29.aspx) 接口中的方法写入邮件系统。 
    
7. 调用 [IUnknown：：Release](https://msdn.microsoft.com/library/ms682317%28VS.85%29.aspx) 方法来释放 **ITnef** 对象。 
    
**处理入站 TNEF 邮件**
  
1. 从 MAPI 后台处理程序获取 MAPI 邮件对象，将邮件头属性写入新的 MAPI 邮件。
    
2. 创建并初始化 [IStream](https://msdn.microsoft.com/library/aa380034%28VS.85%29.aspx) 对象以包含入站邮件中的 TNEF 数据。 
    
3. 将 MAPI 消息和 [IStream 对象](https://msdn.microsoft.com/library/aa380034%28VS.85%29.aspx) 传递到 [OpenTnefStreamEx](opentnefstreamex.md) 函数。 
    
4. 通过调用 [ITnef：：ExtractProps](itnef-extractprops.md) 方法解码 TNEF 数据中的信息。 
    
   > [!NOTE]
   > ExtractProps **解码** 的所有内容都将覆盖从传入邮件信封解码的属性。 也就是说，提取的 TNEF 属性将覆盖邮件中的现有属性。 
  
5. 通过调用 [ITnef：：OpenTaggedBody](itnef-opentaggedbody.md) 处理标记的邮件文本，然后分析文本以恢复附件位置。 
    
6. 通过调用 [IMAPIProp：：SaveChanges 保存消息](imapiprop-savechanges.md)。
    
7. 通过调用 [IUnknown：：Release](https://msdn.microsoft.com/library/ms682317%28VS.85%29.aspx) 方法释放 TNEF 对象。 
    

