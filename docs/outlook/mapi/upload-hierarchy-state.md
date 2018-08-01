---
title: 上传层次结构状态
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: e39c4198-4913-5e86-900a-32e5ba5d801c
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: d53790cb51b660c781190cf41ca317c823a021e8
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779055"
---
# <a name="upload-hierarchy-state"></a><span data-ttu-id="132a0-103">上传层次结构状态</span><span class="sxs-lookup"><span data-stu-id="132a0-103">Upload Hierarchy State</span></span>

  
  
<span data-ttu-id="132a0-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="132a0-104">**Applies to**: Outlook</span></span> 
  
 <span data-ttu-id="132a0-105">本主题介绍的复制状态机上载层次结构状态期间出现的情况。</span><span class="sxs-lookup"><span data-stu-id="132a0-105">This topic describes what happens during the upload hierarchy state of the replication state machine.</span></span> 
  
## <a name="quick-info"></a><span data-ttu-id="132a0-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="132a0-106">Quick info</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="132a0-107">状态标识符：</span><span class="sxs-lookup"><span data-stu-id="132a0-107">State Identifier:</span></span>  <br/> |<span data-ttu-id="132a0-108">**LR_SYNC_UPLOAD_HIERARCHY**</span><span class="sxs-lookup"><span data-stu-id="132a0-108">**LR_SYNC_UPLOAD_HIERARCHY**</span></span> <br/> |
|<span data-ttu-id="132a0-109">相关的数据结构：</span><span class="sxs-lookup"><span data-stu-id="132a0-109">Related Data Structure:</span></span>  <br/> |<span data-ttu-id="132a0-110">**[UPHIER](uphier.md)**</span><span class="sxs-lookup"><span data-stu-id="132a0-110">**[UPHIER](uphier.md)**</span></span> <br/> |
|<span data-ttu-id="132a0-111">从此状态：</span><span class="sxs-lookup"><span data-stu-id="132a0-111">From this state:</span></span>  <br/> |[<span data-ttu-id="132a0-112">同步状态</span><span class="sxs-lookup"><span data-stu-id="132a0-112">Synchronize state</span></span>](synchronize-state.md) <br/> |
|<span data-ttu-id="132a0-113">为此状态：</span><span class="sxs-lookup"><span data-stu-id="132a0-113">To this state:</span></span>  <br/> |<span data-ttu-id="132a0-114">[上载文件夹状态](upload-folder-state.md)，或同步状态</span><span class="sxs-lookup"><span data-stu-id="132a0-114">[Upload folder state](upload-folder-state.md), or synchronize state</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="132a0-115">复制状态机是确定性状态机。</span><span class="sxs-lookup"><span data-stu-id="132a0-115">The replication state machine is a deterministic state machine.</span></span> <span data-ttu-id="132a0-116">传出到另一种状态的客户端从后者必须最终返回到前者。</span><span class="sxs-lookup"><span data-stu-id="132a0-116">A client departing one state to another must eventually return to the former from the latter.</span></span> 
  
## <a name="description"></a><span data-ttu-id="132a0-117">说明</span><span class="sxs-lookup"><span data-stu-id="132a0-117">Description</span></span>

<span data-ttu-id="132a0-118">此状态启动上载已在前面指定的文件夹树层次结构同步状态。</span><span class="sxs-lookup"><span data-stu-id="132a0-118">This state initiates uploading a folder tree hierarchy that has been specified in a preceding synchronize state.</span></span> <span data-ttu-id="132a0-119">Outlook 来确定已创建或修改在该层次结构和初始化 *%uphier* **** 中的文件夹的数目。</span><span class="sxs-lookup"><span data-stu-id="132a0-119">Outlook determines the number of folders that have been created or modified in that hierarchy and initializes  *cEnt*  in **UPHIER**.</span></span> <span data-ttu-id="132a0-120">同样，outlook 将保持与另一个成员*iEnt*上载文件夹的数目。</span><span class="sxs-lookup"><span data-stu-id="132a0-120">Outlook also keeps a count of the number of uploaded folders with another member  *iEnt*  .</span></span> <span data-ttu-id="132a0-121">若要上载 *%* 文件夹中每个，客户端进入本地存储上载文件夹状态，文件夹上载完成后，返回到上载层次结构状态。</span><span class="sxs-lookup"><span data-stu-id="132a0-121">To upload each of the  *cEnt*  folders, the client moves the local store into the upload folder state, returning to the upload hierarchy state when the folder upload finishes.</span></span> 
  
<span data-ttu-id="132a0-122">上载层次结构状态结束时，本地存储返回到同步状态。</span><span class="sxs-lookup"><span data-stu-id="132a0-122">When the upload hierarchy state ends, the local store returns to the synchronize state.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="132a0-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="132a0-123">See also</span></span>



[<span data-ttu-id="132a0-124">关于复制 API</span><span class="sxs-lookup"><span data-stu-id="132a0-124">About the Replication API</span></span>](about-the-replication-api.md)
  
[<span data-ttu-id="132a0-125">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="132a0-125">MAPI Constants</span></span>](mapi-constants.md)
  
[<span data-ttu-id="132a0-126">关于复制状态计算机</span><span class="sxs-lookup"><span data-stu-id="132a0-126">About the Replication State Machine</span></span>](about-the-replication-state-machine.md)
  
[<span data-ttu-id="132a0-127">SYNCSTATE</span><span class="sxs-lookup"><span data-stu-id="132a0-127">SYNCSTATE</span></span>](syncstate.md)

