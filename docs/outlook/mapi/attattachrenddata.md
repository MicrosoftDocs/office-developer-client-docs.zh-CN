---
title: attAttachRenddata
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: c510b7a5-0f55-46af-bddb-40a8195a84d4
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: d8c6699ac1bc5687b1c885d156535e5b54b93140
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774576"
---
# <a name="attattachrenddata"></a><span data-ttu-id="d814a-103">attAttachRenddata</span><span class="sxs-lookup"><span data-stu-id="d814a-103">attAttachRenddata</span></span>

  
  
<span data-ttu-id="d814a-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="d814a-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="d814a-105">**AttAttachRenddata**属性被编码为**RENDDATA**结构，描述如何和附件呈现消息文本中的位置。</span><span class="sxs-lookup"><span data-stu-id="d814a-105">The **attAttachRenddata** attribute is encoded as a **RENDDATA** structure that describes how and where the attachment is rendered in the message text.</span></span> <span data-ttu-id="d814a-106">**RENDDATA**结构是只需编码 TNEF 用于将 stream 中为**sizeof(RENDDATA)** 字节开头**RENDDATA**结构中的第一个成员。</span><span class="sxs-lookup"><span data-stu-id="d814a-106">The **RENDDATA** structure is simply encoded in the TNEF stream as **sizeof(RENDDATA)** bytes beginning with the first member of the **RENDDATA** structure.</span></span> <span data-ttu-id="d814a-107">如果**RENDDATA**结构的**dwFlags**成员的值设置为**MAC_BINARY**，以下附件的数据存储在 MacBinary 格式;否则，像往常一样编码附件数据。</span><span class="sxs-lookup"><span data-stu-id="d814a-107">If the value of the **RENDDATA** structure's **dwFlags** member is set to **MAC_BINARY**, then the data for the following attachment is stored in MacBinary format; otherwise, the attachment data is encoded as usual.</span></span>
  

