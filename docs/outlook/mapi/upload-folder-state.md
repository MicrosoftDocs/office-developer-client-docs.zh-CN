---
title: 上载文件夹状态
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: 270b1df0-c5cd-0d0f-7b57-2726dee978ab
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 82b00a33c5de11b3fc9ccd3bde4cf31c79b99c2a
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779043"
---
# <a name="upload-folder-state"></a><span data-ttu-id="172e7-103">上载文件夹状态</span><span class="sxs-lookup"><span data-stu-id="172e7-103">Upload Folder State</span></span>

  
  
<span data-ttu-id="172e7-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="172e7-104">**Applies to**: Outlook</span></span> 
  
 <span data-ttu-id="172e7-105">本主题介绍的复制状态机上载文件夹状态期间出现的情况。</span><span class="sxs-lookup"><span data-stu-id="172e7-105">This topic describes what happens during the upload folder state of the replication state machine.</span></span> 
  
## <a name="quick-info"></a><span data-ttu-id="172e7-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="172e7-106">Quick info</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="172e7-107">状态标识符：</span><span class="sxs-lookup"><span data-stu-id="172e7-107">State Identifier:</span></span>  <br/> |<span data-ttu-id="172e7-108">**LR_SYNC_UPLOAD_FOLDER**</span><span class="sxs-lookup"><span data-stu-id="172e7-108">**LR_SYNC_UPLOAD_FOLDER**</span></span> <br/> |
|<span data-ttu-id="172e7-109">相关的数据结构：</span><span class="sxs-lookup"><span data-stu-id="172e7-109">Related Data Structure:</span></span>  <br/> |<span data-ttu-id="172e7-110">**[UPFLD](upfld.md)**</span><span class="sxs-lookup"><span data-stu-id="172e7-110">**[UPFLD](upfld.md)**</span></span> <br/> |
|<span data-ttu-id="172e7-111">从此状态：</span><span class="sxs-lookup"><span data-stu-id="172e7-111">From this state:</span></span>  <br/> |[<span data-ttu-id="172e7-112">上载层次结构状态</span><span class="sxs-lookup"><span data-stu-id="172e7-112">Upload hierarchy state</span></span>](upload-hierarchy-state.md) <br/> |
|<span data-ttu-id="172e7-113">为此状态：</span><span class="sxs-lookup"><span data-stu-id="172e7-113">To this state:</span></span>  <br/> |<span data-ttu-id="172e7-114">上载层次结构状态</span><span class="sxs-lookup"><span data-stu-id="172e7-114">Upload hierarchy state</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="172e7-115">复制状态机是确定性状态机。</span><span class="sxs-lookup"><span data-stu-id="172e7-115">The replication state machine is a deterministic state machine.</span></span> <span data-ttu-id="172e7-116">从一种状态传出到另一个客户端从后者必须最终返回到前者。</span><span class="sxs-lookup"><span data-stu-id="172e7-116">A client departing from one state to another must eventually return to the former from the latter.</span></span> 
  
## <a name="description"></a><span data-ttu-id="172e7-117">说明</span><span class="sxs-lookup"><span data-stu-id="172e7-117">Description</span></span>

<span data-ttu-id="172e7-118">此状态启动上载已指定为上述上载层次结构状态层次结构中的文件夹。</span><span class="sxs-lookup"><span data-stu-id="172e7-118">This state initiates uploading a folder in a hierarchy that has been specified in a preceding upload hierarchy state.</span></span> <span data-ttu-id="172e7-119">在此状态下，Outlook 提供文件夹对象 （如果它不被删除） 和相应**UPFLD**数据结构的一部分指示文件夹 （新建、 移动、 修改或删除） 的状态标志。</span><span class="sxs-lookup"><span data-stu-id="172e7-119">During this state, Outlook provides the folder object (if it has not been deleted) and the flags indicating the state of the folder (new, moved, modified, or deleted) as part of the corresponding **UPFLD** data structure.</span></span> <span data-ttu-id="172e7-120">然后，客户端将此信息上载到服务器。</span><span class="sxs-lookup"><span data-stu-id="172e7-120">The client then uploads this information to the server.</span></span> 
  
<span data-ttu-id="172e7-121">如果成功上载，客户端设置到**UPF_OK** **UPFLD** *ulFlags* 。</span><span class="sxs-lookup"><span data-stu-id="172e7-121">If the upload is successful, the client sets  *ulFlags*  in **UPFLD** to **UPF_OK**.</span></span> <span data-ttu-id="172e7-122">Outlook 然后再清除其内部上载文件夹的请求信息。</span><span class="sxs-lookup"><span data-stu-id="172e7-122">Outlook then clears its internal information about the request to upload the folder.</span></span> 
  
<span data-ttu-id="172e7-123">文件夹上载结束时，本地存储返回到上载层次结构状态。</span><span class="sxs-lookup"><span data-stu-id="172e7-123">When the folder upload ends, the local store returns to the upload hierarchy state.</span></span> <span data-ttu-id="172e7-124">基于**[UPHIER](uphier.md)** 结构对应于上述上载层次结构状态，Outlook 来确定是否要继续进行上载下一步文件夹，并为下一个上载文件夹状态准备。</span><span class="sxs-lookup"><span data-stu-id="172e7-124">Based on the **[UPHIER](uphier.md)** structure corresponding to the preceding upload hierarchy state, Outlook determines whether to proceed with uploading the next folder and to prepare for the next upload folder state.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="172e7-125">如果客户端需要上载只有一个文件夹，客户端可以发起通过[同步状态](synchronize-state.md)复制，无需输入上载层次结构状态。</span><span class="sxs-lookup"><span data-stu-id="172e7-125">If the client needs to upload only one folder, the client can initiate the replication through the [synchronize state](synchronize-state.md) without entering the upload hierarchy state.</span></span> <span data-ttu-id="172e7-126">客户端设置**[同步](sync.md)** 的特定成员 — *ulFlags* **UPS_UPLOAD_ONLY**和**UPS_ONE_FOLDER**以及为该文件夹的 ID *feid* — 以告知该只有一个文件夹的 Outlook 将上载。</span><span class="sxs-lookup"><span data-stu-id="172e7-126">The client sets certain members of **[SYNC](sync.md)** —  *ulFlags*  to **UPS_UPLOAD_ONLY** and **UPS_ONE_FOLDER** and  *feid*  to the folder's ID — to tell Outlook that only one folder will be uploaded.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="172e7-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="172e7-127">See also</span></span>



[<span data-ttu-id="172e7-128">有关复制 API</span><span class="sxs-lookup"><span data-stu-id="172e7-128">About the Replication API</span></span>](about-the-replication-api.md)
  
[<span data-ttu-id="172e7-129">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="172e7-129">MAPI Constants</span></span>](mapi-constants.md)
  
[<span data-ttu-id="172e7-130">有关的复制状态机</span><span class="sxs-lookup"><span data-stu-id="172e7-130">About the Replication State Machine</span></span>](about-the-replication-state-machine.md)
  
[<span data-ttu-id="172e7-131">SYNCSTATE</span><span class="sxs-lookup"><span data-stu-id="172e7-131">SYNCSTATE</span></span>](syncstate.md)

