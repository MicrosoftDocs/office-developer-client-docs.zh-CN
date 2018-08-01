---
title: 邮件存储区中的特殊文件夹
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 9462070e-1472-4e12-ba4e-e4ac60022892
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 013e62e06e100296a5fc702b68348bb74eb718e2
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778842"
---
# <a name="special-folders-in-message-stores"></a><span data-ttu-id="4f146-103">邮件存储区中的特殊文件夹</span><span class="sxs-lookup"><span data-stu-id="4f146-103">Special Folders in Message Stores</span></span>

  
  
<span data-ttu-id="4f146-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="4f146-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="4f146-105">可能提前创建如收件箱、 发件箱和搜索结果文件夹的特殊文件夹，并将其受消息存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="4f146-105">Special folders such as the Inbox, Outbox, and search-results folder may be created in advance and protected by the message store provider.</span></span> <span data-ttu-id="4f146-106">如果文件夹不存在，则 MAPI 将尝试通过调用[HrValidateIPMSubtree](hrvalidateipmsubtree.md)函数消息存储库中创建它们。</span><span class="sxs-lookup"><span data-stu-id="4f146-106">If the folders do not exist, MAPI will attempt to create them in the message store by calling the [HrValidateIPMSubtree](hrvalidateipmsubtree.md) function.</span></span> <span data-ttu-id="4f146-107">有关详细信息，请参阅[MAPI 特殊文件夹](mapi-special-folders.md)。</span><span class="sxs-lookup"><span data-stu-id="4f146-107">For more information, see [MAPI Special Folders](mapi-special-folders.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="4f146-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4f146-108">See also</span></span>



[<span data-ttu-id="4f146-109">实现邮件存储区中的文件夹</span><span class="sxs-lookup"><span data-stu-id="4f146-109">Implementing Folders in Message Stores</span></span>](implementing-folders-in-message-stores.md)

