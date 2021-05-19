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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32355718"
---
# <a name="pidtagmessagestatus-canonical-property"></a><span data-ttu-id="5371f-103">PidTagMessageStatus 规范属性</span><span class="sxs-lookup"><span data-stu-id="5371f-103">PidTagMessageStatus Canonical Property</span></span>

  
  
<span data-ttu-id="5371f-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="5371f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="5371f-105">包含定义内容表中邮件状态的 32 位位掩码标志。</span><span class="sxs-lookup"><span data-stu-id="5371f-105">Contains a 32-bit bitmask of flags that defines the status of a message in a contents table.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="5371f-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="5371f-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="5371f-107">PR_MSG_STATUS</span><span class="sxs-lookup"><span data-stu-id="5371f-107">PR_MSG_STATUS</span></span>  <br/> |
|<span data-ttu-id="5371f-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="5371f-108">Identifier:</span></span>  <br/> |<span data-ttu-id="5371f-109">0x0E17</span><span class="sxs-lookup"><span data-stu-id="5371f-109">0x0E17</span></span>  <br/> |
|<span data-ttu-id="5371f-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="5371f-110">Data type:</span></span>  <br/> |<span data-ttu-id="5371f-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="5371f-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="5371f-112">区域：</span><span class="sxs-lookup"><span data-stu-id="5371f-112">Area:</span></span>  <br/> |<span data-ttu-id="5371f-113">常规消息</span><span class="sxs-lookup"><span data-stu-id="5371f-113">General messaging</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="5371f-114">备注</span><span class="sxs-lookup"><span data-stu-id="5371f-114">Remarks</span></span>

<span data-ttu-id="5371f-115">邮件可以存在于内容表和一个或多个搜索结果表中，并且邮件的每个实例可以具有不同的状态。</span><span class="sxs-lookup"><span data-stu-id="5371f-115">A message can exist in a contents table and in one or more search-results tables, and each instance of the message can have a different status.</span></span> <span data-ttu-id="5371f-116">不应将此属性视为邮件上的属性，而应视为内容表中的列。</span><span class="sxs-lookup"><span data-stu-id="5371f-116">This property should not be considered a property on a message but a column in a contents table.</span></span> 
  
<span data-ttu-id="5371f-117">客户端应用程序可以在此属性中设置以下一个或多个标志：</span><span class="sxs-lookup"><span data-stu-id="5371f-117">A client application can set one or more of the following flags in this property:</span></span> 
  
<span data-ttu-id="5371f-118">MSGSTATUS_ANSWERED</span><span class="sxs-lookup"><span data-stu-id="5371f-118">MSGSTATUS_ANSWERED</span></span> 
  
> <span data-ttu-id="5371f-119">邮件已答复。</span><span class="sxs-lookup"><span data-stu-id="5371f-119">The message has been replied to.</span></span> 
    
<span data-ttu-id="5371f-120">MSGSTATUS_DELMARKED</span><span class="sxs-lookup"><span data-stu-id="5371f-120">MSGSTATUS_DELMARKED</span></span> 
  
> <span data-ttu-id="5371f-121">邮件已标记为后续删除。</span><span class="sxs-lookup"><span data-stu-id="5371f-121">The message has been marked for subsequent deletion.</span></span> 
    
<span data-ttu-id="5371f-122">MSGSTATUS_DRAFT</span><span class="sxs-lookup"><span data-stu-id="5371f-122">MSGSTATUS_DRAFT</span></span> 
  
> <span data-ttu-id="5371f-123">邮件位于草稿修订状态。</span><span class="sxs-lookup"><span data-stu-id="5371f-123">The message is in draft revision status.</span></span> 
    
<span data-ttu-id="5371f-124">MSGSTATUS_HIDDEN</span><span class="sxs-lookup"><span data-stu-id="5371f-124">MSGSTATUS_HIDDEN</span></span> 
  
> <span data-ttu-id="5371f-125">邮件从收件人的文件夹显示中取消显示。</span><span class="sxs-lookup"><span data-stu-id="5371f-125">The message is to be suppressed from recipients' folder displays.</span></span> 
    
<span data-ttu-id="5371f-126">MSGSTATUS_HIGHLIGHTED</span><span class="sxs-lookup"><span data-stu-id="5371f-126">MSGSTATUS_HIGHLIGHTED</span></span> 
  
> <span data-ttu-id="5371f-127">邮件将在收件人的文件夹显示中突出显示。</span><span class="sxs-lookup"><span data-stu-id="5371f-127">The message is to be highlighted in recipients' folder displays.</span></span> 
    
<span data-ttu-id="5371f-128">MSGSTATUS_REMOTE_DELETE</span><span class="sxs-lookup"><span data-stu-id="5371f-128">MSGSTATUS_REMOTE_DELETE</span></span> 
  
> <span data-ttu-id="5371f-129">邮件已在远程邮件存储中标记为删除，无需下载到本地客户端。</span><span class="sxs-lookup"><span data-stu-id="5371f-129">The message has been marked for deletion at the remote message store without downloading to the local client.</span></span> 
    
<span data-ttu-id="5371f-130">MSGSTATUS_REMOTE_DOWNLOAD</span><span class="sxs-lookup"><span data-stu-id="5371f-130">MSGSTATUS_REMOTE_DOWNLOAD</span></span> 
  
> <span data-ttu-id="5371f-131">邮件已标记为从远程邮件存储下载到本地客户端。</span><span class="sxs-lookup"><span data-stu-id="5371f-131">The message has been marked for downloading from the remote message store to the local client.</span></span> 
    
<span data-ttu-id="5371f-132">MSGSTATUS_TAGGED</span><span class="sxs-lookup"><span data-stu-id="5371f-132">MSGSTATUS_TAGGED</span></span> 
  
> <span data-ttu-id="5371f-133">邮件已标记为客户端定义。</span><span class="sxs-lookup"><span data-stu-id="5371f-133">The message has been tagged for a client-defined purpose.</span></span>
    
<span data-ttu-id="5371f-134">客户端MSGSTATUS_DELMARKED、MSGSTATUS_HIDDEN、MSGSTATUS_HIGHLIGHTED和 **MSGSTATUS_TAGGED** 标志。</span><span class="sxs-lookup"><span data-stu-id="5371f-134">The **MSGSTATUS_DELMARKED**, **MSGSTATUS_HIDDEN**, **MSGSTATUS_HIGHLIGHTED**, and **MSGSTATUS_TAGGED** flags are defined by the client.</span></span> <span data-ttu-id="5371f-135">传输和存储提供程序无需任何操作即可传递这些位。</span><span class="sxs-lookup"><span data-stu-id="5371f-135">Transport and store providers pass these bits without any action.</span></span> 
  
<span data-ttu-id="5371f-136">客户端可以通过适合其应用程序的任何方式解释这些值。</span><span class="sxs-lookup"><span data-stu-id="5371f-136">Clients can interpret these values in any way that is appropriate for their applications.</span></span> <span data-ttu-id="5371f-137">许多客户端使用此属性的一种方式是使用具有代表性图标显示标记为删除的邮件。</span><span class="sxs-lookup"><span data-stu-id="5371f-137">One way that many clients use this property is to display messages marked for deletion with a representative icon.</span></span> 
  
<span data-ttu-id="5371f-138">远程查看器客户端 **可以在MSGSTATUS_REMOTE_DELETE MSGSTATUS_REMOTE_DOWNLOAD** 向它显示的邮件头文件夹中的邮件设置或设置邮件。</span><span class="sxs-lookup"><span data-stu-id="5371f-138">A remote viewer client can set **MSGSTATUS_REMOTE_DELETE** or **MSGSTATUS_REMOTE_DOWNLOAD** on messages in the header folder presented to it by the remote transport provider.</span></span> <span data-ttu-id="5371f-139">客户端应用程序可以检查此文件夹中的每个邮件头，以确定应在远程邮件存储中下载还是删除邮件。</span><span class="sxs-lookup"><span data-stu-id="5371f-139">The client application can examine each message header in this folder to determine whether the message should be downloaded or deleted at the remote message store.</span></span> <span data-ttu-id="5371f-140">然后，它使用 [IMAPIFolder：：SetMessageStatus](imapifolder-setmessagestatus.md) 方法设置相应的标志。</span><span class="sxs-lookup"><span data-stu-id="5371f-140">It then uses the [IMAPIFolder::SetMessageStatus](imapifolder-setmessagestatus.md) method to set the appropriate flag.</span></span> <span data-ttu-id="5371f-141">**SetMessageStatus** 是设置此属性中任何标志的唯一方法; [不能使用 IMAPIProp：：SetProps](imapiprop-setprops.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="5371f-141">**SetMessageStatus** is the only way to set any of the flags in this property; the [IMAPIProp::SetProps](imapiprop-setprops.md) method cannot be used.</span></span> <span data-ttu-id="5371f-142">若要检索此属性，客户端调用 [IMAPIFolder：：GetMessageStatus，](imapifolder-getmessagestatus.md) 而不是 [IMAPIProp：：GetProps](imapiprop-getprops.md)。</span><span class="sxs-lookup"><span data-stu-id="5371f-142">To retrieve this property, clients call [IMAPIFolder::GetMessageStatus](imapifolder-getmessagestatus.md) rather than [IMAPIProp::GetProps](imapiprop-getprops.md).</span></span>
  
<span data-ttu-id="5371f-143">此属性的 16 (0x10000 31 位0x80000000) IPM 客户端应用程序中的 (消息) 使用。</span><span class="sxs-lookup"><span data-stu-id="5371f-143">Bits 16 through 31 (0x10000 through 0x80000000) of this property are available for use by the interpersonal message (IPM) client application.</span></span> <span data-ttu-id="5371f-144">保留所有其他位以供 MAPI 使用;上表中未定义的那些项应最初设置为零，以后不应更改。</span><span class="sxs-lookup"><span data-stu-id="5371f-144">All other bits are reserved for use by MAPI; those not defined in the preceding table should be initially set to zero and not altered subsequently.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="5371f-145">相关资源</span><span class="sxs-lookup"><span data-stu-id="5371f-145">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="5371f-146">协议规范</span><span class="sxs-lookup"><span data-stu-id="5371f-146">Protocol specifications</span></span>

<span data-ttu-id="5371f-147">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="5371f-147">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="5371f-148">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="5371f-148">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="5371f-149">[[MS-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="5371f-149">[[MS-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="5371f-150">处理在服务器和客户端之间同步邮件对象数据。</span><span class="sxs-lookup"><span data-stu-id="5371f-150">Handles synchronizing messaging object data between a server and a client.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="5371f-151">头文件</span><span class="sxs-lookup"><span data-stu-id="5371f-151">Header files</span></span>

<span data-ttu-id="5371f-152">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="5371f-152">Mapidefs.h</span></span>
  
> <span data-ttu-id="5371f-153">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="5371f-153">Provides data type definitions.</span></span>
    
<span data-ttu-id="5371f-154">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="5371f-154">Mapitags.h</span></span>
  
> <span data-ttu-id="5371f-155">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="5371f-155">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="5371f-156">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5371f-156">See also</span></span>



[<span data-ttu-id="5371f-157">IMAPITable::QueryRows</span><span class="sxs-lookup"><span data-stu-id="5371f-157">IMAPITable::QueryRows</span></span>](imapitable-queryrows.md)


[<span data-ttu-id="5371f-158">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="5371f-158">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="5371f-159">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="5371f-159">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="5371f-160">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="5371f-160">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="5371f-161">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="5371f-161">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

