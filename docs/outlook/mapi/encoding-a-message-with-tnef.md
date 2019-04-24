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
  
提交邮件时, 传输提供程序可以创建用于在传输过程中包含邮件的文件。 接下来, 将在文件周围封装[IStream](https://msdn.microsoft.com/library/aa380034%28VS.85%29.aspx)接口。 然后, 传输提供程序使用[ITnef](itnefiunknown.md)方法将邮件属性以标记格式写入流, 从而使接收传输提供程序可以轻松地对属性进行解码。 
  
**表示单个文件中的整个邮件**
  
1. 通过将[IStream](https://msdn.microsoft.com/library/aa380034%28VS.85%29.aspx)对象和邮件传递到[OpenTnefStreamEx](opentnefstreamex.md)函数来获取 TNEF 对象。 
    
2. 通过调用[IMAPIProp:: GetPropList](imapiprop-getproplist.md)方法获取邮件的所有已定义属性的列表。 
    
3. 使用[IMAPIProp](imapipropiunknown.md)方法排除邮件系统支持的所有属性。 在适当的时间, 将这些属性以邮件系统所需的格式写入邮件系统。 
    
4. 调用[ITnef:: AddProps](itnef-addprops.md)对其余的属性 (包括所有附件) 进行编码。 
    
5. 在添加所有请求的属性后, 调用[ITnef:: Finish](itnef-finish.md)方法将邮件编码到 TNEF 流中。 
    
6. 调用[ITnef:: OpenTaggedBody](itnef-opentaggedbody.md)方法以获取带标记的邮件文本。 使用 OLE [IStream](https://msdn.microsoft.com/library/aa380034%28VS.85%29.aspx)接口中的方法将此标记的文本写入邮件系统。 
    
7. 调用[IUnknown:: release](https://msdn.microsoft.com/library/ms682317%28VS.85%29.aspx)方法以释放**ITnef**对象。 
    
**处理入站 TNEF 邮件**
  
1. 从 mapi 后台处理程序获取 mapi 邮件对象, 并将邮件头属性写入新 MAPI 邮件。
    
2. 创建并初始化[IStream](https://msdn.microsoft.com/library/aa380034%28VS.85%29.aspx)对象以包含入站邮件中的 TNEF 数据。 
    
3. 将 MAPI 邮件和[IStream](https://msdn.microsoft.com/library/aa380034%28VS.85%29.aspx)对象传递到[OpenTnefStreamEx](opentnefstreamex.md)函数。 
    
4. 通过调用[ITnef:: ExtractProps](itnef-extractprops.md)方法, 对 TNEF 数据中的信息进行解码。 
    
   > [!NOTE]
   > 由**ExtractProps**解码的任何内容都将覆盖从传入邮件的信封解码的属性。 也就是说, 提取的 TNEF 属性将覆盖邮件中的现有属性。 
  
5. 通过调用[ITnef:: OpenTaggedBody](itnef-opentaggedbody.md)并分析文本来恢复附件位置, 以处理带标记的邮件文本。 
    
6. 通过调用[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)保存邮件。
    
7. 通过调用[IUnknown:: release](https://msdn.microsoft.com/library/ms682317%28VS.85%29.aspx)方法释放 TNEF 对象。 
    

