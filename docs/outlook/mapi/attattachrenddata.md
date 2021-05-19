---
title: attAttachRenddata
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: c510b7a5-0f55-46af-bddb-40a8195a84d4
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: d58fc0eae5401773d28f5bbe510913ff381ade8d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33427134"
---
# <a name="attattachrenddata"></a><span data-ttu-id="3e09a-103">attAttachRenddata</span><span class="sxs-lookup"><span data-stu-id="3e09a-103">attAttachRenddata</span></span>

  
  
<span data-ttu-id="3e09a-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="3e09a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="3e09a-105">**attAttachRenddata** 属性编码为描述附件在邮件文本中的呈现方式和位置的 **RENDDATA** 结构。</span><span class="sxs-lookup"><span data-stu-id="3e09a-105">The **attAttachRenddata** attribute is encoded as a **RENDDATA** structure that describes how and where the attachment is rendered in the message text.</span></span> <span data-ttu-id="3e09a-106">**RENDDATA** 结构在 TNEF 流中仅编码为 (**RENDDATA**) 字节的大小，从 **RENDDATA** 结构的第一个成员开始。</span><span class="sxs-lookup"><span data-stu-id="3e09a-106">The **RENDDATA** structure is simply encoded in the TNEF stream as **sizeof(RENDDATA)** bytes beginning with the first member of the **RENDDATA** structure.</span></span> <span data-ttu-id="3e09a-107">如果 **RENDDATA** 结构的 **dwFlags** 成员的值设置为 **MAC_BINARY，** 则以下附件的数据将存储为 MacBinary 格式;否则，附件数据将像往常一样编码。</span><span class="sxs-lookup"><span data-stu-id="3e09a-107">If the value of the **RENDDATA** structure's **dwFlags** member is set to **MAC_BINARY**, then the data for the following attachment is stored in MacBinary format; otherwise, the attachment data is encoded as usual.</span></span>
  

