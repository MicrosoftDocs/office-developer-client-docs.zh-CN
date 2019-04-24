---
title: 上传文件夹状态
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: 270b1df0-c5cd-0d0f-7b57-2726dee978ab
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: c20f2998a2fef1ddb53b13708dcf56f9d7b50dbe
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32348424"
---
# <a name="upload-folder-state"></a><span data-ttu-id="0fa2d-103">上传文件夹状态</span><span class="sxs-lookup"><span data-stu-id="0fa2d-103">Upload Folder State</span></span>

  
  
<span data-ttu-id="0fa2d-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="0fa2d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
 <span data-ttu-id="0fa2d-105">本主题介绍复制状态机的上载文件夹状态过程中发生的情况。</span><span class="sxs-lookup"><span data-stu-id="0fa2d-105">This topic describes what happens during the upload folder state of the replication state machine.</span></span> 
  
## <a name="quick-info"></a><span data-ttu-id="0fa2d-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="0fa2d-106">Quick info</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="0fa2d-107">状态标识符:</span><span class="sxs-lookup"><span data-stu-id="0fa2d-107">State Identifier:</span></span>  <br/> |<span data-ttu-id="0fa2d-108">**LR_SYNC_UPLOAD_FOLDER**</span><span class="sxs-lookup"><span data-stu-id="0fa2d-108">**LR_SYNC_UPLOAD_FOLDER**</span></span> <br/> |
|<span data-ttu-id="0fa2d-109">相关数据结构:</span><span class="sxs-lookup"><span data-stu-id="0fa2d-109">Related Data Structure:</span></span>  <br/> |<span data-ttu-id="0fa2d-110">**[UPFLD](upfld.md)**</span><span class="sxs-lookup"><span data-stu-id="0fa2d-110">**[UPFLD](upfld.md)**</span></span> <br/> |
|<span data-ttu-id="0fa2d-111">从此状态:</span><span class="sxs-lookup"><span data-stu-id="0fa2d-111">From this state:</span></span>  <br/> |[<span data-ttu-id="0fa2d-112">上传层次结构状态</span><span class="sxs-lookup"><span data-stu-id="0fa2d-112">Upload hierarchy state</span></span>](upload-hierarchy-state.md) <br/> |
|<span data-ttu-id="0fa2d-113">到此状态:</span><span class="sxs-lookup"><span data-stu-id="0fa2d-113">To this state:</span></span>  <br/> |<span data-ttu-id="0fa2d-114">上传层次结构状态</span><span class="sxs-lookup"><span data-stu-id="0fa2d-114">Upload hierarchy state</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="0fa2d-115">复制状态计算机是确定的状态机。</span><span class="sxs-lookup"><span data-stu-id="0fa2d-115">The replication state machine is a deterministic state machine.</span></span> <span data-ttu-id="0fa2d-116">客户端从一个状态传出到另一个状态最终必须返回到前者的前一项。</span><span class="sxs-lookup"><span data-stu-id="0fa2d-116">A client departing from one state to another must eventually return to the former from the latter.</span></span> 
  
## <a name="description"></a><span data-ttu-id="0fa2d-117">说明</span><span class="sxs-lookup"><span data-stu-id="0fa2d-117">Description</span></span>

<span data-ttu-id="0fa2d-118">此状态将启动上传层次结构状态中指定的层次结构中的文件夹。</span><span class="sxs-lookup"><span data-stu-id="0fa2d-118">This state initiates uploading a folder in a hierarchy that has been specified in a preceding upload hierarchy state.</span></span> <span data-ttu-id="0fa2d-119">在此状态下, Outlook 提供的文件夹对象 (如果尚未删除) 和指示文件夹状态的标志 ("新建"、"已移动"、"已修改" 或 "已删除") 作为相应**UPFLD**数据结构的一部分。</span><span class="sxs-lookup"><span data-stu-id="0fa2d-119">During this state, Outlook provides the folder object (if it has not been deleted) and the flags indicating the state of the folder (new, moved, modified, or deleted) as part of the corresponding **UPFLD** data structure.</span></span> <span data-ttu-id="0fa2d-120">然后, 客户端将此信息上载到服务器。</span><span class="sxs-lookup"><span data-stu-id="0fa2d-120">The client then uploads this information to the server.</span></span> 
  
<span data-ttu-id="0fa2d-121">如果上载成功, 客户端会将**UPFLD**中的*ulFlags*设置为**UPF_OK**。</span><span class="sxs-lookup"><span data-stu-id="0fa2d-121">If the upload is successful, the client sets  *ulFlags*  in **UPFLD** to **UPF_OK**.</span></span> <span data-ttu-id="0fa2d-122">然后, Outlook 清除其有关上载文件夹的请求的内部信息。</span><span class="sxs-lookup"><span data-stu-id="0fa2d-122">Outlook then clears its internal information about the request to upload the folder.</span></span> 
  
<span data-ttu-id="0fa2d-123">文件夹上传结束时, 本地存储将返回到上传层次结构状态。</span><span class="sxs-lookup"><span data-stu-id="0fa2d-123">When the folder upload ends, the local store returns to the upload hierarchy state.</span></span> <span data-ttu-id="0fa2d-124">根据与上述上传层次结构状态相对应的**[UPHIER](uphier.md)** 结构, Outlook 决定是否继续上传下一个文件夹, 并准备下一个上载文件夹状态。</span><span class="sxs-lookup"><span data-stu-id="0fa2d-124">Based on the **[UPHIER](uphier.md)** structure corresponding to the preceding upload hierarchy state, Outlook determines whether to proceed with uploading the next folder and to prepare for the next upload folder state.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="0fa2d-125">如果客户端只需要上传一个文件夹, 则客户端可以通过[同步状态](synchronize-state.md)启动复制, 而无需输入上传层次结构状态。</span><span class="sxs-lookup"><span data-stu-id="0fa2d-125">If the client needs to upload only one folder, the client can initiate the replication through the [synchronize state](synchronize-state.md) without entering the upload hierarchy state.</span></span> <span data-ttu-id="0fa2d-126">客户端将**[同步](sync.md)** 的某些成员 ( *ulFlags* to **UPS_UPLOAD_ONLY** and **UPS_ONE_FOLDER** and *feid* ) 设置为文件夹的 ID, 告诉 Outlook 只会上载一个文件夹。</span><span class="sxs-lookup"><span data-stu-id="0fa2d-126">The client sets certain members of **[SYNC](sync.md)** —  *ulFlags*  to **UPS_UPLOAD_ONLY** and **UPS_ONE_FOLDER** and  *feid*  to the folder's ID — to tell Outlook that only one folder will be uploaded.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="0fa2d-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0fa2d-127">See also</span></span>



[<span data-ttu-id="0fa2d-128">关于复制 API</span><span class="sxs-lookup"><span data-stu-id="0fa2d-128">About the Replication API</span></span>](about-the-replication-api.md)
  
[<span data-ttu-id="0fa2d-129">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="0fa2d-129">MAPI Constants</span></span>](mapi-constants.md)
  
[<span data-ttu-id="0fa2d-130">关于复制状态机</span><span class="sxs-lookup"><span data-stu-id="0fa2d-130">About the Replication State Machine</span></span>](about-the-replication-state-machine.md)
  
[<span data-ttu-id="0fa2d-131">SYNCSTATE</span><span class="sxs-lookup"><span data-stu-id="0fa2d-131">SYNCSTATE</span></span>](syncstate.md)

