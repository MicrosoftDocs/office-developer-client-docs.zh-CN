---
title: 创建邮件主题
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 70e18534-054f-49e7-9a5d-10db0db132d0
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 419c9776b380436b1a7163803a8677fb6a89be97
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774741"
---
# <a name="creating-a-message-subject"></a><span data-ttu-id="37c75-103">创建邮件主题</span><span class="sxs-lookup"><span data-stu-id="37c75-103">Creating a Message Subject</span></span>

  
  
<span data-ttu-id="37c75-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="37c75-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="37c75-105">邮件的主题， **PR_SUBJECT** ([PidTagSubject](pidtagsubject-canonical-property.md))，是可选属性，用于汇总用途的一条消息。</span><span class="sxs-lookup"><span data-stu-id="37c75-105">The subject of a message, **PR_SUBJECT** ([PidTagSubject](pidtagsubject-canonical-property.md)), is an optional property, used to summarize the intent of a message.</span></span> <span data-ttu-id="37c75-106">如果您选择将其设置，使其包含字符的字符串 128 个字节或更少。</span><span class="sxs-lookup"><span data-stu-id="37c75-106">If you choose to set it, make it a character string 128 bytes or less.</span></span> <span data-ttu-id="37c75-107">128 字节限制并不是通过 MAPI; 施加限制它是由一些消息存储提供程序的限制。</span><span class="sxs-lookup"><span data-stu-id="37c75-107">The 128 byte limit is not a limit imposed by MAPI; it is a limit imposed by some message store providers.</span></span> <span data-ttu-id="37c75-108">若要确保与执行实施它的提供程序互操作性，限制为 128 个字节的主题。</span><span class="sxs-lookup"><span data-stu-id="37c75-108">To ensure interoperability with providers that do impose it, limit subjects to 128 bytes.</span></span> 
  
<span data-ttu-id="37c75-109">请注意，某些消息存储提供程序不允许**PR_SUBJECT**写入到[IStream](http://msdn.microsoft.com/en-us/library/aa380034%28VS.85%29.aspx)接口的流。</span><span class="sxs-lookup"><span data-stu-id="37c75-109">Be aware that some message store providers do not allow **PR_SUBJECT** to be written to a stream with the [IStream](http://msdn.microsoft.com/en-us/library/aa380034%28VS.85%29.aspx) interface.</span></span> 
  
<span data-ttu-id="37c75-110">未设置**PR_SUBJECT_PREFIX** ([PidTagSubjectPrefix](pidtagsubjectprefix-canonical-property.md));此属性是设置仅在答复和转发邮件。</span><span class="sxs-lookup"><span data-stu-id="37c75-110">Do not set **PR_SUBJECT_PREFIX** ([PidTagSubjectPrefix](pidtagsubjectprefix-canonical-property.md)); this property is set only on replies and forwarded messages.</span></span> 
  

