---
title: Upload层次结构状态
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: e39c4198-4913-5e86-900a-32e5ba5d801c
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: f789f4d7bbaf585d0d80f2208c35313542dfc191
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33415423"
---
# <a name="upload-hierarchy-state"></a><span data-ttu-id="f33ce-103">Upload层次结构状态</span><span class="sxs-lookup"><span data-stu-id="f33ce-103">Upload Hierarchy State</span></span>

  
  
<span data-ttu-id="f33ce-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f33ce-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
 <span data-ttu-id="f33ce-105">本主题介绍在复制状态机的上载层次结构状态期间发生的情况。</span><span class="sxs-lookup"><span data-stu-id="f33ce-105">This topic describes what happens during the upload hierarchy state of the replication state machine.</span></span> 
  
## <a name="quick-info"></a><span data-ttu-id="f33ce-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="f33ce-106">Quick info</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="f33ce-107">状态标识符：</span><span class="sxs-lookup"><span data-stu-id="f33ce-107">State Identifier:</span></span>  <br/> |<span data-ttu-id="f33ce-108">**LR_SYNC_UPLOAD_HIERARCHY**</span><span class="sxs-lookup"><span data-stu-id="f33ce-108">**LR_SYNC_UPLOAD_HIERARCHY**</span></span> <br/> |
|<span data-ttu-id="f33ce-109">相关数据结构：</span><span class="sxs-lookup"><span data-stu-id="f33ce-109">Related Data Structure:</span></span>  <br/> |<span data-ttu-id="f33ce-110">**[UPHIER](uphier.md)**</span><span class="sxs-lookup"><span data-stu-id="f33ce-110">**[UPHIER](uphier.md)**</span></span> <br/> |
|<span data-ttu-id="f33ce-111">从此状态：</span><span class="sxs-lookup"><span data-stu-id="f33ce-111">From this state:</span></span>  <br/> |[<span data-ttu-id="f33ce-112">同步状态</span><span class="sxs-lookup"><span data-stu-id="f33ce-112">Synchronize state</span></span>](synchronize-state.md) <br/> |
|<span data-ttu-id="f33ce-113">至此状态：</span><span class="sxs-lookup"><span data-stu-id="f33ce-113">To this state:</span></span>  <br/> |<span data-ttu-id="f33ce-114">[Upload文件夹状态或](upload-folder-state.md)同步状态</span><span class="sxs-lookup"><span data-stu-id="f33ce-114">[Upload folder state](upload-folder-state.md), or synchronize state</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="f33ce-115">复制状态机是一个确定性状态机。</span><span class="sxs-lookup"><span data-stu-id="f33ce-115">The replication state machine is a deterministic state machine.</span></span> <span data-ttu-id="f33ce-116">从一个状态到另一个状态的客户端最终必须从后者返回到另一个状态。</span><span class="sxs-lookup"><span data-stu-id="f33ce-116">A client departing one state to another must eventually return to the former from the latter.</span></span> 
  
## <a name="description"></a><span data-ttu-id="f33ce-117">说明</span><span class="sxs-lookup"><span data-stu-id="f33ce-117">Description</span></span>

<span data-ttu-id="f33ce-118">此状态启动上载在之前的同步状态中指定的文件夹树层次结构。</span><span class="sxs-lookup"><span data-stu-id="f33ce-118">This state initiates uploading a folder tree hierarchy that has been specified in a preceding synchronize state.</span></span> <span data-ttu-id="f33ce-119">Outlook确定已在该层次结构中创建或修改的文件夹数，并初始化 **UPHIER** 中的 *cEnt。*</span><span class="sxs-lookup"><span data-stu-id="f33ce-119">Outlook determines the number of folders that have been created or modified in that hierarchy and initializes  *cEnt*  in **UPHIER**.</span></span> <span data-ttu-id="f33ce-120">Outlook还保留与另一个成员 iEnt 的已上传文件夹 *数的计数*。</span><span class="sxs-lookup"><span data-stu-id="f33ce-120">Outlook also keeps a count of the number of uploaded folders with another member  *iEnt*  .</span></span> <span data-ttu-id="f33ce-121">若要上载每个  *cEnt*  文件夹，客户端会将本地存储移动到上载文件夹状态，在文件夹上载完成时返回到上载层次结构状态。</span><span class="sxs-lookup"><span data-stu-id="f33ce-121">To upload each of the  *cEnt*  folders, the client moves the local store into the upload folder state, returning to the upload hierarchy state when the folder upload finishes.</span></span> 
  
<span data-ttu-id="f33ce-122">当上载层次结构状态结束时，本地存储将返回到同步状态。</span><span class="sxs-lookup"><span data-stu-id="f33ce-122">When the upload hierarchy state ends, the local store returns to the synchronize state.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f33ce-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f33ce-123">See also</span></span>



[<span data-ttu-id="f33ce-124">关于复制 API</span><span class="sxs-lookup"><span data-stu-id="f33ce-124">About the Replication API</span></span>](about-the-replication-api.md)
  
[<span data-ttu-id="f33ce-125">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="f33ce-125">MAPI Constants</span></span>](mapi-constants.md)
  
[<span data-ttu-id="f33ce-126">关于复制状态机</span><span class="sxs-lookup"><span data-stu-id="f33ce-126">About the Replication State Machine</span></span>](about-the-replication-state-machine.md)
  
[<span data-ttu-id="f33ce-127">SYNCSTATE</span><span class="sxs-lookup"><span data-stu-id="f33ce-127">SYNCSTATE</span></span>](syncstate.md)

