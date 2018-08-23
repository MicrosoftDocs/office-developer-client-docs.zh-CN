---
title: 编码与 TNEF 邮件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 6b86d9a9-6876-4885-ae1e-8571b25b85cc
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 5043c338f309b5da21ca828a47daf1d8b6abfd5d
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22577749"
---
# <a name="encoding-a-message-with-tnef"></a>编码与 TNEF 邮件

**适用于**： Outlook 2013 |Outlook 2016 
  
提交一条消息时, 传输提供程序可以创建用于在传输过程包含邮件文件。 接下来， [IStream](http://msdn.microsoft.com/en-us/library/aa380034%28VS.85%29.aspx)接口环绕该文件。 传输提供程序然后使用[ITnef](itnefiunknown.md)方法使属性可以轻松地进行解码接收传输提供程序的已标记格式的流中写入消息属性。 
  
**表示单个文件中的整个邮件**
  
1. 通过将[IStream](http://msdn.microsoft.com/en-us/library/aa380034%28VS.85%29.aspx)对象和消息传递到[OpenTnefStreamEx](opentnefstreamex.md)函数获取 TNEF 对象。 
    
2. 通过调用[IMAPIProp::GetPropList](imapiprop-getproplist.md)方法获得邮件的所有定义属性的列表。 
    
3. 使用[IMAPIProp](imapipropiunknown.md)方法来排除在邮件系统支持的所有属性。 在适当的时间，将这些属性写入邮件系统中的消息的系统要求的格式。 
    
4. 调用[ITnef::AddProps](itnef-addprops.md)进行编码其余的属性，包括所有附件。 
    
5. 调用[ITnef::Finish](itnef-finish.md)方法后所有请求的属性将被添加到 TNEF 流编码邮件。 
    
6. 调用[ITnef::OpenTaggedBody](itnef-opentaggedbody.md)方法以获取的已标记的消息文本。 此标记的文本是写出到邮件系统使用从 OLE [IStream](http://msdn.microsoft.com/en-us/library/aa380034%28VS.85%29.aspx)接口的方法。 
    
7. 调用[IUnknown::Release](http://msdn.microsoft.com/en-us/library/ms682317%28VS.85%29.aspx)方法以释放**ITnef**对象。 
    
**处理入站的 TNEF 邮件**
  
1. 从 MAPI 后台处理程序中获取 MAPI 邮件对象和写入到新的 MAPI 邮件的邮件头属性。
    
2. 创建并初始化[IStream](http://msdn.microsoft.com/en-us/library/aa380034%28VS.85%29.aspx)对象以包含从入站邮件的 TNEF 数据。 
    
3. 传递给[OpenTnefStreamEx](opentnefstreamex.md)函数的 MAPI 邮件和[IStream](http://msdn.microsoft.com/en-us/library/aa380034%28VS.85%29.aspx)对象。 
    
4. 通过调用[ITnef::ExtractProps](itnef-extractprops.md)方法解码 TNEF 数据中的信息。 
    
   > [!NOTE]
   > 任何由**ExtractProps**解码将覆盖从传入邮件信封进行解码的属性。 即提取的 TNEF 属性将覆盖一条消息中的现有属性。 
  
5. 通过调用[ITnef::OpenTaggedBody](itnef-opentaggedbody.md)处理已标记的邮件文本，并分析文本以恢复附件的位置。 
    
6. 通过调用[IMAPIProp::SaveChanges](imapiprop-savechanges.md)保存邮件。
    
7. 通过调用[IUnknown::Release](http://msdn.microsoft.com/en-us/library/ms682317%28VS.85%29.aspx)方法释放 TNEF 对象。 
    

