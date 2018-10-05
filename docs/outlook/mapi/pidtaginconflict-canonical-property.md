---
title: PidTagInConflict 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagInConflict
api_type:
- HeaderDef
ms.assetid: e83c05c6-a7c0-486c-a112-58a39255767a
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: fc2774efed1a15fe79e167149f2cb162bae7642c
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25384435"
---
# <a name="pidtaginconflict-canonical-property"></a><span data-ttu-id="543fb-103">PidTagInConflict 规范属性</span><span class="sxs-lookup"><span data-stu-id="543fb-103">PidTagInConflict Canonical Property</span></span>

  
  
<span data-ttu-id="543fb-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="543fb-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="543fb-105">包含 TRUE 时附件表示备用的副本。</span><span class="sxs-lookup"><span data-stu-id="543fb-105">Contains TRUE when the attachment represents an alternate replica.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="543fb-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="543fb-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="543fb-107">PR_IN_CONFLICT</span><span class="sxs-lookup"><span data-stu-id="543fb-107">PR_IN_CONFLICT</span></span>  <br/> |
|<span data-ttu-id="543fb-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="543fb-108">Identifier:</span></span>  <br/> |<span data-ttu-id="543fb-109">0x666C</span><span class="sxs-lookup"><span data-stu-id="543fb-109">0x666C</span></span>  <br/> |
|<span data-ttu-id="543fb-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="543fb-110">Data type:</span></span>  <br/> |<span data-ttu-id="543fb-111">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="543fb-111">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="543fb-112">区域：</span><span class="sxs-lookup"><span data-stu-id="543fb-112">Area:</span></span>  <br/> |<span data-ttu-id="543fb-113">冲突注释</span><span class="sxs-lookup"><span data-stu-id="543fb-113">Conflict note</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="543fb-114">说明</span><span class="sxs-lookup"><span data-stu-id="543fb-114">Remarks</span></span>

<span data-ttu-id="543fb-115">同步过程中副本中检测针对一条消息的当前版本冲突时的电子邮件客户端和服务器必须生成冲突解决消息。</span><span class="sxs-lookup"><span data-stu-id="543fb-115">The email client and server must generate a conflict resolve message when detecting a conflict against the current version of a message in the replica during synchronization.</span></span> <span data-ttu-id="543fb-116">务必了解可能会在当前的同步操作过程中已传输的当前版本中的本地副本的消息。</span><span class="sxs-lookup"><span data-stu-id="543fb-116">It is important to understand that it is possible that the current version of the message in the local replica was transmitted during the current synchronization operation.</span></span> <span data-ttu-id="543fb-117">当已存在冲突的服务器上的任何冲突消息已下载到的本地副本之前，将发生此错误。</span><span class="sxs-lookup"><span data-stu-id="543fb-117">This will happen when the conflict already exists on the server before any of the conflicting messages were downloaded to the local replica.</span></span> <span data-ttu-id="543fb-118">冲突解决消息必须作为具有冲突 Pcl 的独立副本进行同步。</span><span class="sxs-lookup"><span data-stu-id="543fb-118">A conflict resolve message must be synchronized as independent replicas with conflicting PCLs.</span></span> <span data-ttu-id="543fb-119">冲突解决消息本身不必须同步客户端和服务器; 之间应交换仅的独立副本。</span><span class="sxs-lookup"><span data-stu-id="543fb-119">The conflict resolve message itself must not be synchronized between client and server; only the independent replicas should be exchanged.</span></span> <span data-ttu-id="543fb-120">同步伙伴然后必须生成新消息相匹配的结构冲突消息。</span><span class="sxs-lookup"><span data-stu-id="543fb-120">The synchronization partner must then generate a new message that matches the structure of the conflict message.</span></span> <span data-ttu-id="543fb-121">因此，很重要的客户端和服务器使用相同的算法来检测"获胜"项。</span><span class="sxs-lookup"><span data-stu-id="543fb-121">Therefore, it is important that client and server use the same algorithm to detect the "winner" item.</span></span> <span data-ttu-id="543fb-122">必须应用以下规则来检测"入选":</span><span class="sxs-lookup"><span data-stu-id="543fb-122">The following rules must be applied to detect the "winner":</span></span>
  
1. <span data-ttu-id="543fb-123">上次修改时间。</span><span class="sxs-lookup"><span data-stu-id="543fb-123">Last modification time.</span></span>
    
2. <span data-ttu-id="543fb-124">更高版本 （使用内存比较） 的 CN GUID 中断领结。</span><span class="sxs-lookup"><span data-stu-id="543fb-124">Higher CN GUID (using memory compare) to break tie.</span></span>
    
## <a name="related-resources"></a><span data-ttu-id="543fb-125">相关资源</span><span class="sxs-lookup"><span data-stu-id="543fb-125">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="543fb-126">协议规范</span><span class="sxs-lookup"><span data-stu-id="543fb-126">Protocol specifications</span></span>

<span data-ttu-id="543fb-127">[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="543fb-127">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="543fb-128">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="543fb-128">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="543fb-129">[[MS OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="543fb-129">[[MS-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="543fb-130">同步服务器和客户端之间的消息对象数据的句柄。</span><span class="sxs-lookup"><span data-stu-id="543fb-130">Handles synchronizing messaging object data between a server and a client.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="543fb-131">头文件</span><span class="sxs-lookup"><span data-stu-id="543fb-131">Header files</span></span>

<span data-ttu-id="543fb-132">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="543fb-132">Mapidefs.h</span></span>
  
> <span data-ttu-id="543fb-133">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="543fb-133">Provides data type definitions.</span></span>
    
<span data-ttu-id="543fb-134">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="543fb-134">Mapitags.h</span></span>
  
> <span data-ttu-id="543fb-135">包含列为相关属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="543fb-135">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="543fb-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="543fb-136">See also</span></span>



[<span data-ttu-id="543fb-137">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="543fb-137">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="543fb-138">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="543fb-138">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="543fb-139">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="543fb-139">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="543fb-140">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="543fb-140">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

