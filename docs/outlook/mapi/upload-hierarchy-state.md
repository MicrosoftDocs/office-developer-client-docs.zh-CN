---
title: 上传层次结构状态
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: e39c4198-4913-5e86-900a-32e5ba5d801c
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: f789f4d7bbaf585d0d80f2208c35313542dfc191
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32286313"
---
# <a name="upload-hierarchy-state"></a><span data-ttu-id="e7333-103">上传层次结构状态</span><span class="sxs-lookup"><span data-stu-id="e7333-103">Upload Hierarchy State</span></span>

  
  
<span data-ttu-id="e7333-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e7333-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
 <span data-ttu-id="e7333-105">本主题介绍复制状态机的上载层次结构状态过程中发生的情况。</span><span class="sxs-lookup"><span data-stu-id="e7333-105">This topic describes what happens during the upload hierarchy state of the replication state machine.</span></span> 
  
## <a name="quick-info"></a><span data-ttu-id="e7333-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="e7333-106">Quick info</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="e7333-107">状态标识符:</span><span class="sxs-lookup"><span data-stu-id="e7333-107">State Identifier:</span></span>  <br/> |<span data-ttu-id="e7333-108">**LR_SYNC_UPLOAD_HIERARCHY**</span><span class="sxs-lookup"><span data-stu-id="e7333-108">**LR_SYNC_UPLOAD_HIERARCHY**</span></span> <br/> |
|<span data-ttu-id="e7333-109">相关数据结构:</span><span class="sxs-lookup"><span data-stu-id="e7333-109">Related Data Structure:</span></span>  <br/> |<span data-ttu-id="e7333-110">**[UPHIER](uphier.md)**</span><span class="sxs-lookup"><span data-stu-id="e7333-110">**[UPHIER](uphier.md)**</span></span> <br/> |
|<span data-ttu-id="e7333-111">从此状态:</span><span class="sxs-lookup"><span data-stu-id="e7333-111">From this state:</span></span>  <br/> |[<span data-ttu-id="e7333-112">同步状态</span><span class="sxs-lookup"><span data-stu-id="e7333-112">Synchronize state</span></span>](synchronize-state.md) <br/> |
|<span data-ttu-id="e7333-113">到此状态:</span><span class="sxs-lookup"><span data-stu-id="e7333-113">To this state:</span></span>  <br/> |<span data-ttu-id="e7333-114">[上传文件夹状态](upload-folder-state.md)或同步状态</span><span class="sxs-lookup"><span data-stu-id="e7333-114">[Upload folder state](upload-folder-state.md), or synchronize state</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="e7333-115">复制状态计算机是确定的状态机。</span><span class="sxs-lookup"><span data-stu-id="e7333-115">The replication state machine is a deterministic state machine.</span></span> <span data-ttu-id="e7333-116">客户端在向另一种状态传出一种状态时, 最终必须从后者返回前一个状态。</span><span class="sxs-lookup"><span data-stu-id="e7333-116">A client departing one state to another must eventually return to the former from the latter.</span></span> 
  
## <a name="description"></a><span data-ttu-id="e7333-117">说明</span><span class="sxs-lookup"><span data-stu-id="e7333-117">Description</span></span>

<span data-ttu-id="e7333-118">此状态将启动上载已在之前的同步状态中指定的文件夹树层次结构。</span><span class="sxs-lookup"><span data-stu-id="e7333-118">This state initiates uploading a folder tree hierarchy that has been specified in a preceding synchronize state.</span></span> <span data-ttu-id="e7333-119">Outlook 确定在该层次结构中创建或修改的文件夹数, 并在**UPHIER**中初始化*分币*。</span><span class="sxs-lookup"><span data-stu-id="e7333-119">Outlook determines the number of folders that have been created or modified in that hierarchy and initializes  *cEnt*  in **UPHIER**.</span></span> <span data-ttu-id="e7333-120">Outlook 还会保留上载的文件夹与其他成员*iEnt*的数量的计数。</span><span class="sxs-lookup"><span data-stu-id="e7333-120">Outlook also keeps a count of the number of uploaded folders with another member  *iEnt*  .</span></span> <span data-ttu-id="e7333-121">若要上传每个*分币*文件夹, 客户端会将本地存储区移到上传文件夹状态, 并在文件夹上传完成时返回到上传层次结构状态。</span><span class="sxs-lookup"><span data-stu-id="e7333-121">To upload each of the  *cEnt*  folders, the client moves the local store into the upload folder state, returning to the upload hierarchy state when the folder upload finishes.</span></span> 
  
<span data-ttu-id="e7333-122">当上载层次结构状态结束时, 本地存储将返回到同步状态。</span><span class="sxs-lookup"><span data-stu-id="e7333-122">When the upload hierarchy state ends, the local store returns to the synchronize state.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e7333-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e7333-123">See also</span></span>



[<span data-ttu-id="e7333-124">关于复制 API</span><span class="sxs-lookup"><span data-stu-id="e7333-124">About the Replication API</span></span>](about-the-replication-api.md)
  
[<span data-ttu-id="e7333-125">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="e7333-125">MAPI Constants</span></span>](mapi-constants.md)
  
[<span data-ttu-id="e7333-126">关于复制状态机</span><span class="sxs-lookup"><span data-stu-id="e7333-126">About the Replication State Machine</span></span>](about-the-replication-state-machine.md)
  
[<span data-ttu-id="e7333-127">SYNCSTATE</span><span class="sxs-lookup"><span data-stu-id="e7333-127">SYNCSTATE</span></span>](syncstate.md)

