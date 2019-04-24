---
title: 邮件存储区中的特殊文件夹
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 9462070e-1472-4e12-ba4e-e4ac60022892
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: ae881f56695914627e8c2f6f61f143da91cd78a8
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32344441"
---
# <a name="special-folders-in-message-stores"></a><span data-ttu-id="95cc1-103">邮件存储区中的特殊文件夹</span><span class="sxs-lookup"><span data-stu-id="95cc1-103">Special Folders in Message Stores</span></span>

  
  
<span data-ttu-id="95cc1-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="95cc1-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="95cc1-105">"收件箱"、"发件箱" 和 "搜索结果" 文件夹等特殊文件夹可以提前创建并受邮件存储提供程序保护。</span><span class="sxs-lookup"><span data-stu-id="95cc1-105">Special folders such as the Inbox, Outbox, and search-results folder may be created in advance and protected by the message store provider.</span></span> <span data-ttu-id="95cc1-106">如果文件夹不存在, MAPI 将尝试通过调用[HrValidateIPMSubtree](hrvalidateipmsubtree.md)函数在邮件存储区中创建这些文件夹。</span><span class="sxs-lookup"><span data-stu-id="95cc1-106">If the folders do not exist, MAPI will attempt to create them in the message store by calling the [HrValidateIPMSubtree](hrvalidateipmsubtree.md) function.</span></span> <span data-ttu-id="95cc1-107">有关详细信息, 请参阅[MAPI 特殊文件夹](mapi-special-folders.md)。</span><span class="sxs-lookup"><span data-stu-id="95cc1-107">For more information, see [MAPI Special Folders](mapi-special-folders.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="95cc1-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="95cc1-108">See also</span></span>



[<span data-ttu-id="95cc1-109">实现邮件存储中的文件夹</span><span class="sxs-lookup"><span data-stu-id="95cc1-109">Implementing Folders in Message Stores</span></span>](implementing-folders-in-message-stores.md)

