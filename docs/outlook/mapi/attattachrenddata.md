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
ms.openlocfilehash: a006c126ec5e0fb86847226195efd03f7ae5351f
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22569447"
---
# <a name="attattachrenddata"></a><span data-ttu-id="f979d-103">attAttachRenddata</span><span class="sxs-lookup"><span data-stu-id="f979d-103">attAttachRenddata</span></span>

  
  
<span data-ttu-id="f979d-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f979d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f979d-105">**AttAttachRenddata**属性被编码为**RENDDATA**结构，描述如何和附件呈现消息文本中的位置。</span><span class="sxs-lookup"><span data-stu-id="f979d-105">The **attAttachRenddata** attribute is encoded as a **RENDDATA** structure that describes how and where the attachment is rendered in the message text.</span></span> <span data-ttu-id="f979d-106">**RENDDATA**结构是只需编码 TNEF 用于将 stream 中为**sizeof(RENDDATA)** 字节开头**RENDDATA**结构中的第一个成员。</span><span class="sxs-lookup"><span data-stu-id="f979d-106">The **RENDDATA** structure is simply encoded in the TNEF stream as **sizeof(RENDDATA)** bytes beginning with the first member of the **RENDDATA** structure.</span></span> <span data-ttu-id="f979d-107">如果**RENDDATA**结构的**dwFlags**成员的值设置为**MAC_BINARY**，以下附件的数据存储在 MacBinary 格式;否则，像往常一样编码附件数据。</span><span class="sxs-lookup"><span data-stu-id="f979d-107">If the value of the **RENDDATA** structure's **dwFlags** member is set to **MAC_BINARY**, then the data for the following attachment is stored in MacBinary format; otherwise, the attachment data is encoded as usual.</span></span>
  

