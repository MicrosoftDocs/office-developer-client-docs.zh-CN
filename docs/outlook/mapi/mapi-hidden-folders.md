---
title: MAPI 隐藏文件夹
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 8b3b9c80-f7f4-4f37-bd6b-323469d020f1
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 81b53bc138a64da673d6723e60fd90b086174efe
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776250"
---
# <a name="mapi-hidden-folders"></a><span data-ttu-id="816c7-103">MAPI 隐藏文件夹</span><span class="sxs-lookup"><span data-stu-id="816c7-103">MAPI Hidden Folders</span></span>

  
  
<span data-ttu-id="816c7-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="816c7-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="816c7-105">隐藏的文件夹是通用的客户端创建根文件夹的消息存储库，而不是人际邮件 (IPM) 子树的根文件夹中。</span><span class="sxs-lookup"><span data-stu-id="816c7-105">Hidden folders are generic folders that clients create in the root folder of the message store, rather than in the root folder of an interpersonal message (IPM) subtree.</span></span> <span data-ttu-id="816c7-106">由于这些文件夹不放置在 IPM 子树中，它们是通常从视图中隐藏用户的消息存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="816c7-106">Because these folders are not placed in an IPM subtree, they are generally hidden from the user's view by the message store provider.</span></span> <span data-ttu-id="816c7-107">隐藏的文件夹通常包含相关的消息存储到但不向用户相关的信息。</span><span class="sxs-lookup"><span data-stu-id="816c7-107">Hidden folders typically contain information that is relevant to the message store but irrelevant to the user.</span></span> <span data-ttu-id="816c7-108">客户端创建隐藏的文件夹来存储，例如，要保存与文件夹层次结构的其余部分的其他信息。</span><span class="sxs-lookup"><span data-stu-id="816c7-108">Clients create hidden folders to store, for example, additional information to be saved with the rest of the folder hierarchy.</span></span>
  
<span data-ttu-id="816c7-109">MAPI 需要所有客户端能够显示、 创建、 修改和删除 IPM 子树中的文件夹。</span><span class="sxs-lookup"><span data-stu-id="816c7-109">MAPI expects all clients to be able to display, create, modify, and delete folders in an IPM subtree.</span></span> <span data-ttu-id="816c7-110">使用其他树中的文件夹的支持会被视为是可选的。</span><span class="sxs-lookup"><span data-stu-id="816c7-110">Support for working with folders in other trees is considered optional.</span></span> <span data-ttu-id="816c7-111">但是，可用于为默认存储和的可以发送和接收邮件的所有邮件存储应完全都支持隐藏的文件夹。</span><span class="sxs-lookup"><span data-stu-id="816c7-111">However, all message stores that can be used as the default store and that can send and receive messages should fully support hidden folders.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="816c7-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="816c7-112">See also</span></span>



[<span data-ttu-id="816c7-113">MAPI 文件夹</span><span class="sxs-lookup"><span data-stu-id="816c7-113">MAPI Folders</span></span>](mapi-folders.md)

