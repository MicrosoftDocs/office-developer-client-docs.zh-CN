---
title: MAPI 隐藏文件夹
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 8b3b9c80-f7f4-4f37-bd6b-323469d020f1
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 9f9daa2169a087cf962d09a7c135e2829c7cd1ee
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33424243"
---
# <a name="mapi-hidden-folders"></a><span data-ttu-id="1dc5a-103">MAPI 隐藏文件夹</span><span class="sxs-lookup"><span data-stu-id="1dc5a-103">MAPI Hidden Folders</span></span>

  
  
<span data-ttu-id="1dc5a-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="1dc5a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="1dc5a-105">隐藏文件夹是客户端在邮件存储的根文件夹中创建的常规文件夹，而不是 IPM (子树中) 文件夹。</span><span class="sxs-lookup"><span data-stu-id="1dc5a-105">Hidden folders are generic folders that clients create in the root folder of the message store, rather than in the root folder of an interpersonal message (IPM) subtree.</span></span> <span data-ttu-id="1dc5a-106">由于这些文件夹未放置在 IPM 子树中，因此邮件存储提供程序通常从用户视图中隐藏它们。</span><span class="sxs-lookup"><span data-stu-id="1dc5a-106">Because these folders are not placed in an IPM subtree, they are generally hidden from the user's view by the message store provider.</span></span> <span data-ttu-id="1dc5a-107">隐藏文件夹通常包含与邮件存储相关但与用户无关的信息。</span><span class="sxs-lookup"><span data-stu-id="1dc5a-107">Hidden folders typically contain information that is relevant to the message store but irrelevant to the user.</span></span> <span data-ttu-id="1dc5a-108">客户端创建隐藏的文件夹来存储，例如，要与文件夹层次结构的其余部分一起保存的其他信息。</span><span class="sxs-lookup"><span data-stu-id="1dc5a-108">Clients create hidden folders to store, for example, additional information to be saved with the rest of the folder hierarchy.</span></span>
  
<span data-ttu-id="1dc5a-109">MAPI 期望所有客户端能够显示、创建、修改和删除 IPM 子树中的文件夹。</span><span class="sxs-lookup"><span data-stu-id="1dc5a-109">MAPI expects all clients to be able to display, create, modify, and delete folders in an IPM subtree.</span></span> <span data-ttu-id="1dc5a-110">支持在其他树中处理文件夹被视为可选。</span><span class="sxs-lookup"><span data-stu-id="1dc5a-110">Support for working with folders in other trees is considered optional.</span></span> <span data-ttu-id="1dc5a-111">但是，所有可以用作默认存储且可以发送和接收邮件的邮件存储应完全支持隐藏文件夹。</span><span class="sxs-lookup"><span data-stu-id="1dc5a-111">However, all message stores that can be used as the default store and that can send and receive messages should fully support hidden folders.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="1dc5a-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1dc5a-112">See also</span></span>



[<span data-ttu-id="1dc5a-113">MAPI 文件夹</span><span class="sxs-lookup"><span data-stu-id="1dc5a-113">MAPI Folders</span></span>](mapi-folders.md)

