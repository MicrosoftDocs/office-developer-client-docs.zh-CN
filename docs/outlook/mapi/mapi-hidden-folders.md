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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32346744"
---
# <a name="mapi-hidden-folders"></a><span data-ttu-id="01b1b-103">MAPI 隐藏文件夹</span><span class="sxs-lookup"><span data-stu-id="01b1b-103">MAPI Hidden Folders</span></span>

  
  
<span data-ttu-id="01b1b-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="01b1b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="01b1b-105">隐藏文件夹是客户端在邮件存储区的根文件夹中创建的通用文件夹, 而不是在人际邮件 (IPM) 子树的根文件夹中创建的文件夹。</span><span class="sxs-lookup"><span data-stu-id="01b1b-105">Hidden folders are generic folders that clients create in the root folder of the message store, rather than in the root folder of an interpersonal message (IPM) subtree.</span></span> <span data-ttu-id="01b1b-106">由于这些文件夹不放置在 IPM 子树中, 因此邮件存储提供程序通常会将这些文件夹隐藏在用户的视图中。</span><span class="sxs-lookup"><span data-stu-id="01b1b-106">Because these folders are not placed in an IPM subtree, they are generally hidden from the user's view by the message store provider.</span></span> <span data-ttu-id="01b1b-107">隐藏的文件夹通常包含与邮件存储区相关但与用户无关的信息。</span><span class="sxs-lookup"><span data-stu-id="01b1b-107">Hidden folders typically contain information that is relevant to the message store but irrelevant to the user.</span></span> <span data-ttu-id="01b1b-108">客户端创建用于存储的隐藏文件夹, 例如, 与文件夹层次结构的其余部分一起保存的附加信息。</span><span class="sxs-lookup"><span data-stu-id="01b1b-108">Clients create hidden folders to store, for example, additional information to be saved with the rest of the folder hierarchy.</span></span>
  
<span data-ttu-id="01b1b-109">MAPI 要求所有客户端都能够显示、创建、修改和删除 IPM 子树中的文件夹。</span><span class="sxs-lookup"><span data-stu-id="01b1b-109">MAPI expects all clients to be able to display, create, modify, and delete folders in an IPM subtree.</span></span> <span data-ttu-id="01b1b-110">对在其他树中使用文件夹的支持被认为是可选的。</span><span class="sxs-lookup"><span data-stu-id="01b1b-110">Support for working with folders in other trees is considered optional.</span></span> <span data-ttu-id="01b1b-111">但是, 所有可用作默认存储的邮件存储以及可以发送和接收邮件的所有邮件都应完全支持隐藏文件夹。</span><span class="sxs-lookup"><span data-stu-id="01b1b-111">However, all message stores that can be used as the default store and that can send and receive messages should fully support hidden folders.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="01b1b-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="01b1b-112">See also</span></span>



[<span data-ttu-id="01b1b-113">MAPI 文件夹</span><span class="sxs-lookup"><span data-stu-id="01b1b-113">MAPI Folders</span></span>](mapi-folders.md)

