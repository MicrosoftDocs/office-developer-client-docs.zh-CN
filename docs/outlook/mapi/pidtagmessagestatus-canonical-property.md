---
title: PidTagMessageStatus 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagMessageStatus
api_type:
- HeaderDef
ms.assetid: e479e863-a8de-4f7e-9eae-3f721cd16e9a
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: dacd759d978394a5f4ed028915ed1c717bf6efe5
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25382804"
---
# <a name="pidtagmessagestatus-canonical-property"></a><span data-ttu-id="65297-103">PidTagMessageStatus 规范属性</span><span class="sxs-lookup"><span data-stu-id="65297-103">PidTagMessageStatus Canonical Property</span></span>

  
  
<span data-ttu-id="65297-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="65297-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="65297-105">包含一个 32 位位掩码的标志，内容表中定义的一条消息，状态。</span><span class="sxs-lookup"><span data-stu-id="65297-105">Contains a 32-bit bitmask of flags that defines the status of a message in a contents table.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="65297-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="65297-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="65297-107">PR_MSG_STATUS</span><span class="sxs-lookup"><span data-stu-id="65297-107">PR_MSG_STATUS</span></span>  <br/> |
|<span data-ttu-id="65297-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="65297-108">Identifier:</span></span>  <br/> |<span data-ttu-id="65297-109">0x0E17</span><span class="sxs-lookup"><span data-stu-id="65297-109">0x0E17</span></span>  <br/> |
|<span data-ttu-id="65297-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="65297-110">Data type:</span></span>  <br/> |<span data-ttu-id="65297-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="65297-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="65297-112">区域：</span><span class="sxs-lookup"><span data-stu-id="65297-112">Area:</span></span>  <br/> |<span data-ttu-id="65297-113">常规消息</span><span class="sxs-lookup"><span data-stu-id="65297-113">General messaging</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="65297-114">说明</span><span class="sxs-lookup"><span data-stu-id="65297-114">Remarks</span></span>

<span data-ttu-id="65297-115">在内容和一个或多个搜索结果表中可以存在一条消息和消息的每个实例都可以具有不同的状态。</span><span class="sxs-lookup"><span data-stu-id="65297-115">A message can exist in a contents table and in one or more search-results tables, and each instance of the message can have a different status.</span></span> <span data-ttu-id="65297-116">此属性不应考虑上一条消息，但内容表中的列的属性。</span><span class="sxs-lookup"><span data-stu-id="65297-116">This property should not be considered a property on a message but a column in a contents table.</span></span> 
  
<span data-ttu-id="65297-117">客户端应用程序可以设置此属性中的一个或多个以下标志：</span><span class="sxs-lookup"><span data-stu-id="65297-117">A client application can set one or more of the following flags in this property:</span></span> 
  
<span data-ttu-id="65297-118">MSGSTATUS_ANSWERED</span><span class="sxs-lookup"><span data-stu-id="65297-118">MSGSTATUS_ANSWERED</span></span> 
  
> <span data-ttu-id="65297-119">已答复邮件。</span><span class="sxs-lookup"><span data-stu-id="65297-119">The message has been replied to.</span></span> 
    
<span data-ttu-id="65297-120">MSGSTATUS_DELMARKED</span><span class="sxs-lookup"><span data-stu-id="65297-120">MSGSTATUS_DELMARKED</span></span> 
  
> <span data-ttu-id="65297-121">邮件已标记为后续删除。</span><span class="sxs-lookup"><span data-stu-id="65297-121">The message has been marked for subsequent deletion.</span></span> 
    
<span data-ttu-id="65297-122">MSGSTATUS_DRAFT</span><span class="sxs-lookup"><span data-stu-id="65297-122">MSGSTATUS_DRAFT</span></span> 
  
> <span data-ttu-id="65297-123">邮件是草稿修订状态。</span><span class="sxs-lookup"><span data-stu-id="65297-123">The message is in draft revision status.</span></span> 
    
<span data-ttu-id="65297-124">MSGSTATUS_HIDDEN</span><span class="sxs-lookup"><span data-stu-id="65297-124">MSGSTATUS_HIDDEN</span></span> 
  
> <span data-ttu-id="65297-125">邮件是从收件人的文件夹显示要取消。</span><span class="sxs-lookup"><span data-stu-id="65297-125">The message is to be suppressed from recipients' folder displays.</span></span> 
    
<span data-ttu-id="65297-126">MSGSTATUS_HIGHLIGHTED</span><span class="sxs-lookup"><span data-stu-id="65297-126">MSGSTATUS_HIGHLIGHTED</span></span> 
  
> <span data-ttu-id="65297-127">邮件是在收件人的文件夹显示突出显示。</span><span class="sxs-lookup"><span data-stu-id="65297-127">The message is to be highlighted in recipients' folder displays.</span></span> 
    
<span data-ttu-id="65297-128">MSGSTATUS_REMOTE_DELETE</span><span class="sxs-lookup"><span data-stu-id="65297-128">MSGSTATUS_REMOTE_DELETE</span></span> 
  
> <span data-ttu-id="65297-129">邮件已标记为删除远程邮件存储在无须下载到本地客户端。</span><span class="sxs-lookup"><span data-stu-id="65297-129">The message has been marked for deletion at the remote message store without downloading to the local client.</span></span> 
    
<span data-ttu-id="65297-130">MSGSTATUS_REMOTE_DOWNLOAD</span><span class="sxs-lookup"><span data-stu-id="65297-130">MSGSTATUS_REMOTE_DOWNLOAD</span></span> 
  
> <span data-ttu-id="65297-131">已从远程邮件存储下载到本地客户端标记邮件。</span><span class="sxs-lookup"><span data-stu-id="65297-131">The message has been marked for downloading from the remote message store to the local client.</span></span> 
    
<span data-ttu-id="65297-132">MSGSTATUS_TAGGED</span><span class="sxs-lookup"><span data-stu-id="65297-132">MSGSTATUS_TAGGED</span></span> 
  
> <span data-ttu-id="65297-133">邮件已标记的客户端定义用途。</span><span class="sxs-lookup"><span data-stu-id="65297-133">The message has been tagged for a client-defined purpose.</span></span>
    
<span data-ttu-id="65297-134">由客户端定义**MSGSTATUS_DELMARKED**、 **MSGSTATUS_HIDDEN**、 **MSGSTATUS_HIGHLIGHTED**和**MSGSTATUS_TAGGED**标志。</span><span class="sxs-lookup"><span data-stu-id="65297-134">The **MSGSTATUS_DELMARKED**, **MSGSTATUS_HIDDEN**, **MSGSTATUS_HIGHLIGHTED**, and **MSGSTATUS_TAGGED** flags are defined by the client.</span></span> <span data-ttu-id="65297-135">传输和存储提供程序传递这些位不需要任何操作。</span><span class="sxs-lookup"><span data-stu-id="65297-135">Transport and store providers pass these bits without any action.</span></span> 
  
<span data-ttu-id="65297-136">客户端可以解释以任何方式适合其应用程序的这些值。</span><span class="sxs-lookup"><span data-stu-id="65297-136">Clients can interpret these values in any way that is appropriate for their applications.</span></span> <span data-ttu-id="65297-137">多个客户端使用此属性的一种方法是显示消息标记为删除代表图标。</span><span class="sxs-lookup"><span data-stu-id="65297-137">One way that many clients use this property is to display messages marked for deletion with a representative icon.</span></span> 
  
<span data-ttu-id="65297-138">远程查看器客户端可以设置**MSGSTATUS_REMOTE_DELETE**或**MSGSTATUS_REMOTE_DOWNLOAD**邮件提供给它的远程传输提供程序的标头文件夹中。</span><span class="sxs-lookup"><span data-stu-id="65297-138">A remote viewer client can set **MSGSTATUS_REMOTE_DELETE** or **MSGSTATUS_REMOTE_DOWNLOAD** on messages in the header folder presented to it by the remote transport provider.</span></span> <span data-ttu-id="65297-139">客户端应用程序可以检查以确定是否应下载或在远程邮件存储区删除邮件此文件夹中的每个邮件标头。</span><span class="sxs-lookup"><span data-stu-id="65297-139">The client application can examine each message header in this folder to determine whether the message should be downloaded or deleted at the remote message store.</span></span> <span data-ttu-id="65297-140">然后使用[IMAPIFolder::SetMessageStatus](imapifolder-setmessagestatus.md)方法可设置适当的标志。</span><span class="sxs-lookup"><span data-stu-id="65297-140">It then uses the [IMAPIFolder::SetMessageStatus](imapifolder-setmessagestatus.md) method to set the appropriate flag.</span></span> <span data-ttu-id="65297-141">**SetMessageStatus**是任何标志设置此属性; 中的唯一方法不能使用[IMAPIProp::SetProps](imapiprop-setprops.md)方法。</span><span class="sxs-lookup"><span data-stu-id="65297-141">**SetMessageStatus** is the only way to set any of the flags in this property; the [IMAPIProp::SetProps](imapiprop-setprops.md) method cannot be used.</span></span> <span data-ttu-id="65297-142">若要检索此属性，客户端调用[IMAPIFolder::GetMessageStatus](imapifolder-getmessagestatus.md) ，而不是[IMAPIProp::GetProps](imapiprop-getprops.md)。</span><span class="sxs-lookup"><span data-stu-id="65297-142">To retrieve this property, clients call [IMAPIFolder::GetMessageStatus](imapifolder-getmessagestatus.md) rather than [IMAPIProp::GetProps](imapiprop-getprops.md).</span></span>
  
<span data-ttu-id="65297-143">位 16 到 31 (通过 0x80000000 0x10000)，此属性是可供使用人际邮件 (IPM) 客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="65297-143">Bits 16 through 31 (0x10000 through 0x80000000) of this property are available for use by the interpersonal message (IPM) client application.</span></span> <span data-ttu-id="65297-144">所有其他位供使用通过 MAPI;上表中未定义的值应最初设置为零并随后不会改动。</span><span class="sxs-lookup"><span data-stu-id="65297-144">All other bits are reserved for use by MAPI; those not defined in the preceding table should be initially set to zero and not altered subsequently.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="65297-145">相关资源</span><span class="sxs-lookup"><span data-stu-id="65297-145">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="65297-146">协议规范</span><span class="sxs-lookup"><span data-stu-id="65297-146">Protocol specifications</span></span>

<span data-ttu-id="65297-147">[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="65297-147">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="65297-148">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="65297-148">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="65297-149">[[MS OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="65297-149">[[MS-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="65297-150">同步服务器和客户端之间的消息对象数据的句柄。</span><span class="sxs-lookup"><span data-stu-id="65297-150">Handles synchronizing messaging object data between a server and a client.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="65297-151">头文件</span><span class="sxs-lookup"><span data-stu-id="65297-151">Header files</span></span>

<span data-ttu-id="65297-152">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="65297-152">Mapidefs.h</span></span>
  
> <span data-ttu-id="65297-153">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="65297-153">Provides data type definitions.</span></span>
    
<span data-ttu-id="65297-154">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="65297-154">Mapitags.h</span></span>
  
> <span data-ttu-id="65297-155">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="65297-155">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="65297-156">另请参阅</span><span class="sxs-lookup"><span data-stu-id="65297-156">See also</span></span>



[<span data-ttu-id="65297-157">IMAPITable::QueryRows</span><span class="sxs-lookup"><span data-stu-id="65297-157">IMAPITable::QueryRows</span></span>](imapitable-queryrows.md)


[<span data-ttu-id="65297-158">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="65297-158">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="65297-159">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="65297-159">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="65297-160">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="65297-160">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="65297-161">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="65297-161">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

