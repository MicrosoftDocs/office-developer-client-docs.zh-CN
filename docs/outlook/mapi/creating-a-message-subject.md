---
title: 创建邮件主题
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 70e18534-054f-49e7-9a5d-10db0db132d0
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 753834ba4df6d0239a484af380e4fe0aa45666b4
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32332961"
---
# <a name="creating-a-message-subject"></a><span data-ttu-id="3ec97-103">创建邮件主题</span><span class="sxs-lookup"><span data-stu-id="3ec97-103">Creating a Message Subject</span></span>

  
  
<span data-ttu-id="3ec97-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="3ec97-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="3ec97-105">邮件的主题（PR_SUBJECT ( [PidTagSubject](pidtagsubject-canonical-property.md)) ）是一个可选属性，用于总结邮件的意图。</span><span class="sxs-lookup"><span data-stu-id="3ec97-105">The subject of a message, **PR_SUBJECT** ([PidTagSubject](pidtagsubject-canonical-property.md)), is an optional property, used to summarize the intent of a message.</span></span> <span data-ttu-id="3ec97-106">如果选择设置它，请使其为字符串字符串 128 字节或更少。</span><span class="sxs-lookup"><span data-stu-id="3ec97-106">If you choose to set it, make it a character string 128 bytes or less.</span></span> <span data-ttu-id="3ec97-107">128 字节的限制不是 MAPI 施加的限制;它是某些邮件存储提供程序施加的限制。</span><span class="sxs-lookup"><span data-stu-id="3ec97-107">The 128 byte limit is not a limit imposed by MAPI; it is a limit imposed by some message store providers.</span></span> <span data-ttu-id="3ec97-108">为了确保与实施它的提供程序的互操作性，将主题限制为 128 个字节。</span><span class="sxs-lookup"><span data-stu-id="3ec97-108">To ensure interoperability with providers that do impose it, limit subjects to 128 bytes.</span></span> 
  
<span data-ttu-id="3ec97-109">请注意，某些邮件存储提供程序 **不允许PR_SUBJECT** [IStream](https://msdn.microsoft.com/library/aa380034%28VS.85%29.aspx) 接口写入流。</span><span class="sxs-lookup"><span data-stu-id="3ec97-109">Be aware that some message store providers do not allow **PR_SUBJECT** to be written to a stream with the [IStream](https://msdn.microsoft.com/library/aa380034%28VS.85%29.aspx) interface.</span></span> 
  
<span data-ttu-id="3ec97-110">不要将[PidTagSubjectPrefix PR_SUBJECT_PREFIX (PidTagSubjectPrefix](pidtagsubjectprefix-canonical-property.md)) ;此属性仅在答复和转发的邮件上设置。</span><span class="sxs-lookup"><span data-stu-id="3ec97-110">Do not set **PR_SUBJECT_PREFIX** ([PidTagSubjectPrefix](pidtagsubjectprefix-canonical-property.md)); this property is set only on replies and forwarded messages.</span></span> 
  

