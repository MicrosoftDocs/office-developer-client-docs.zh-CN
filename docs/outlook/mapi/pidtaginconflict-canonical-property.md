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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32358532"
---
# <a name="pidtaginconflict-canonical-property"></a><span data-ttu-id="f39e7-103">PidTagInConflict 规范属性</span><span class="sxs-lookup"><span data-stu-id="f39e7-103">PidTagInConflict Canonical Property</span></span>

  
  
<span data-ttu-id="f39e7-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f39e7-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f39e7-105">当附件代表备用副本时, 该参数包含 TRUE。</span><span class="sxs-lookup"><span data-stu-id="f39e7-105">Contains TRUE when the attachment represents an alternate replica.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="f39e7-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="f39e7-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="f39e7-107">PR_IN_CONFLICT</span><span class="sxs-lookup"><span data-stu-id="f39e7-107">PR_IN_CONFLICT</span></span>  <br/> |
|<span data-ttu-id="f39e7-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="f39e7-108">Identifier:</span></span>  <br/> |<span data-ttu-id="f39e7-109">0x666C</span><span class="sxs-lookup"><span data-stu-id="f39e7-109">0x666C</span></span>  <br/> |
|<span data-ttu-id="f39e7-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="f39e7-110">Data type:</span></span>  <br/> |<span data-ttu-id="f39e7-111">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="f39e7-111">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="f39e7-112">区域：</span><span class="sxs-lookup"><span data-stu-id="f39e7-112">Area:</span></span>  <br/> |<span data-ttu-id="f39e7-113">冲突注释</span><span class="sxs-lookup"><span data-stu-id="f39e7-113">Conflict note</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="f39e7-114">注解</span><span class="sxs-lookup"><span data-stu-id="f39e7-114">Remarks</span></span>

<span data-ttu-id="f39e7-115">同步期间, 电子邮件客户端和服务器必须生成冲突解决消息, 以检测副本中的当前版本的邮件的冲突。</span><span class="sxs-lookup"><span data-stu-id="f39e7-115">The email client and server must generate a conflict resolve message when detecting a conflict against the current version of a message in the replica during synchronization.</span></span> <span data-ttu-id="f39e7-116">请务必了解, 在当前同步操作过程中, 本地副本中的邮件的当前版本可能已传输。</span><span class="sxs-lookup"><span data-stu-id="f39e7-116">It is important to understand that it is possible that the current version of the message in the local replica was transmitted during the current synchronization operation.</span></span> <span data-ttu-id="f39e7-117">当服务器上已存在冲突时, 将发生这种情况, 在将任何冲突的邮件下载到本地副本之前。</span><span class="sxs-lookup"><span data-stu-id="f39e7-117">This will happen when the conflict already exists on the server before any of the conflicting messages were downloaded to the local replica.</span></span> <span data-ttu-id="f39e7-118">冲突解决邮件必须作为相互冲突的 PCLs 的独立副本进行同步。</span><span class="sxs-lookup"><span data-stu-id="f39e7-118">A conflict resolve message must be synchronized as independent replicas with conflicting PCLs.</span></span> <span data-ttu-id="f39e7-119">冲突解决邮件本身不得在客户端和服务器之间同步;只应交换独立的副本。</span><span class="sxs-lookup"><span data-stu-id="f39e7-119">The conflict resolve message itself must not be synchronized between client and server; only the independent replicas should be exchanged.</span></span> <span data-ttu-id="f39e7-120">然后, 同步伙伴必须生成与冲突邮件的结构相匹配的新邮件。</span><span class="sxs-lookup"><span data-stu-id="f39e7-120">The synchronization partner must then generate a new message that matches the structure of the conflict message.</span></span> <span data-ttu-id="f39e7-121">因此, 客户端和服务器应使用相同的算法来检测 "入选方" 项, 这一点非常重要。</span><span class="sxs-lookup"><span data-stu-id="f39e7-121">Therefore, it is important that client and server use the same algorithm to detect the "winner" item.</span></span> <span data-ttu-id="f39e7-122">必须应用以下规则来检测 "入选方":</span><span class="sxs-lookup"><span data-stu-id="f39e7-122">The following rules must be applied to detect the "winner":</span></span>
  
1. <span data-ttu-id="f39e7-123">上次修改时间。</span><span class="sxs-lookup"><span data-stu-id="f39e7-123">Last modification time.</span></span>
    
2. <span data-ttu-id="f39e7-124">较高的 CN GUID (使用内存比较) 中断关联。</span><span class="sxs-lookup"><span data-stu-id="f39e7-124">Higher CN GUID (using memory compare) to break tie.</span></span>
    
## <a name="related-resources"></a><span data-ttu-id="f39e7-125">相关资源</span><span class="sxs-lookup"><span data-stu-id="f39e7-125">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="f39e7-126">协议规范</span><span class="sxs-lookup"><span data-stu-id="f39e7-126">Protocol specifications</span></span>

<span data-ttu-id="f39e7-127">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="f39e7-127">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="f39e7-128">提供对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="f39e7-128">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="f39e7-129">[[毫秒-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="f39e7-129">[[MS-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="f39e7-130">处理服务器和客户端之间的同步邮件对象数据。</span><span class="sxs-lookup"><span data-stu-id="f39e7-130">Handles synchronizing messaging object data between a server and a client.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="f39e7-131">头文件</span><span class="sxs-lookup"><span data-stu-id="f39e7-131">Header files</span></span>

<span data-ttu-id="f39e7-132">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="f39e7-132">Mapidefs.h</span></span>
  
> <span data-ttu-id="f39e7-133">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="f39e7-133">Provides data type definitions.</span></span>
    
<span data-ttu-id="f39e7-134">Mapitags</span><span class="sxs-lookup"><span data-stu-id="f39e7-134">Mapitags.h</span></span>
  
> <span data-ttu-id="f39e7-135">包含列为关联属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="f39e7-135">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="f39e7-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f39e7-136">See also</span></span>



[<span data-ttu-id="f39e7-137">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="f39e7-137">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="f39e7-138">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="f39e7-138">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="f39e7-139">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="f39e7-139">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="f39e7-140">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="f39e7-140">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

