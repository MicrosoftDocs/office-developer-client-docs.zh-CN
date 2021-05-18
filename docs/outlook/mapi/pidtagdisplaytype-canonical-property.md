---
title: PidTagDisplayType 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagDisplayType
api_type:
- HeaderDef
ms.assetid: ee2bc6ca-3769-4b56-a77d-81418d28f768
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: da26fd2a8643817cf60adbfa6f4e85da345b875c
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32360779"
---
# <a name="pidtagdisplaytype-canonical-property"></a><span data-ttu-id="5b0ec-103">PidTagDisplayType 规范属性</span><span class="sxs-lookup"><span data-stu-id="5b0ec-103">PidTagDisplayType Canonical Property</span></span>

  
  
<span data-ttu-id="5b0ec-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="5b0ec-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="5b0ec-105">包含一个值，该值用于将图标与表的特定行关联。</span><span class="sxs-lookup"><span data-stu-id="5b0ec-105">Contains a value used to associate an icon with a particular row of a table.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="5b0ec-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="5b0ec-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="5b0ec-107">PR_DISPLAY_TYPE</span><span class="sxs-lookup"><span data-stu-id="5b0ec-107">PR_DISPLAY_TYPE</span></span>  <br/> |
|<span data-ttu-id="5b0ec-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="5b0ec-108">Identifier:</span></span>  <br/> |<span data-ttu-id="5b0ec-109">0x3900</span><span class="sxs-lookup"><span data-stu-id="5b0ec-109">0x3900</span></span>  <br/> |
|<span data-ttu-id="5b0ec-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="5b0ec-110">Data type:</span></span>  <br/> |<span data-ttu-id="5b0ec-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="5b0ec-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="5b0ec-112">区域：</span><span class="sxs-lookup"><span data-stu-id="5b0ec-112">Area:</span></span>  <br/> |<span data-ttu-id="5b0ec-113">MAPI 通讯簿</span><span class="sxs-lookup"><span data-stu-id="5b0ec-113">MAPI address book</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="5b0ec-114">备注</span><span class="sxs-lookup"><span data-stu-id="5b0ec-114">Remarks</span></span>

<span data-ttu-id="5b0ec-115">此属性包含一个长整型值，便于根据表项的类型对表项进行特殊处理。</span><span class="sxs-lookup"><span data-stu-id="5b0ec-115">This property contains a long integer that facilitates special treatment of the table entry based on its type.</span></span> <span data-ttu-id="5b0ec-116">此特殊处理通常包括显示与显示类型关联的图标或其他显示元素。</span><span class="sxs-lookup"><span data-stu-id="5b0ec-116">This special treatment typically consists of displaying an icon, or other display element, associated with the display type.</span></span> 
  
<span data-ttu-id="5b0ec-117">此属性不用于文件夹内容表。</span><span class="sxs-lookup"><span data-stu-id="5b0ec-117">This property is not used in folder contents tables.</span></span> <span data-ttu-id="5b0ec-118">客户端应用程序应该使用邮件的 **PR_MESSAGE_CLASS** ([PidTagMessageClass](pidtagmessageclass-canonical-property.md)) 属性和相应的 [IMAPIFormInfo](imapiforminfoimapiprop.md) 接口获取该邮件的 **PR_ICON** ([PidTagIcon](pidtagicon-canonical-property.md)) 和 **PR_MINI_ICON** ([PidTagMiniIcon](pidtagminiicon-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="5b0ec-118">Client applications should use a message's **PR_MESSAGE_CLASS** ([PidTagMessageClass](pidtagmessageclass-canonical-property.md)) property and appropriate [IMAPIFormInfo](imapiforminfoimapiprop.md) interface to get the **PR_ICON** ([PidTagIcon](pidtagicon-canonical-property.md)) and **PR_MINI_ICON** ([PidTagMiniIcon](pidtagminiicon-canonical-property.md)) properties for that message.</span></span> 
  
<span data-ttu-id="5b0ec-119">此属性可以正好具有下列值之一：</span><span class="sxs-lookup"><span data-stu-id="5b0ec-119">This property can have exactly one of the following values:</span></span>
  
<span data-ttu-id="5b0ec-120">DT_AGENT</span><span class="sxs-lookup"><span data-stu-id="5b0ec-120">DT_AGENT</span></span> 
  
> <span data-ttu-id="5b0ec-121">自动代理，如当天报价或天气图表显示。</span><span class="sxs-lookup"><span data-stu-id="5b0ec-121">An automated agent, such as Quote-Of-The-Day or a weather chart display.</span></span>
    
<span data-ttu-id="5b0ec-122">DT_DISTLIST</span><span class="sxs-lookup"><span data-stu-id="5b0ec-122">DT_DISTLIST</span></span> 
  
> <span data-ttu-id="5b0ec-123">通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="5b0ec-123">A distribution list.</span></span>
    
<span data-ttu-id="5b0ec-124">DT_FOLDER</span><span class="sxs-lookup"><span data-stu-id="5b0ec-124">DT_FOLDER</span></span> 
  
> <span data-ttu-id="5b0ec-125">显示与文件夹相邻的默认文件夹图标。</span><span class="sxs-lookup"><span data-stu-id="5b0ec-125">Display default folder icon adjacent to folder.</span></span>
    
<span data-ttu-id="5b0ec-126">DT_FOLDER_LINK</span><span class="sxs-lookup"><span data-stu-id="5b0ec-126">DT_FOLDER_LINK</span></span> 
  
> <span data-ttu-id="5b0ec-127">显示与文件夹相邻的默认文件夹链接图标，而不是默认文件夹图标。</span><span class="sxs-lookup"><span data-stu-id="5b0ec-127">Display default folder link icon adjacent to folder rather than the default folder icon.</span></span>
    
<span data-ttu-id="5b0ec-128">DT_FOLDER_SPECIAL</span><span class="sxs-lookup"><span data-stu-id="5b0ec-128">DT_FOLDER_SPECIAL</span></span> 
  
> <span data-ttu-id="5b0ec-129">显示具有应用程序特定区别的文件夹的图标，例如特殊类型的公用文件夹。</span><span class="sxs-lookup"><span data-stu-id="5b0ec-129">Display icon for a folder with an application-specific distinction, such as a special type of public folder.</span></span>
    
<span data-ttu-id="5b0ec-130">DT_FORUM</span><span class="sxs-lookup"><span data-stu-id="5b0ec-130">DT_FORUM</span></span> 
  
> <span data-ttu-id="5b0ec-131">论坛，例如公告板服务或公用或共享文件夹。</span><span class="sxs-lookup"><span data-stu-id="5b0ec-131">A forum, such as a bulletin board service or a public or shared folder.</span></span>
    
<span data-ttu-id="5b0ec-132">DT_GLOBAL</span><span class="sxs-lookup"><span data-stu-id="5b0ec-132">DT_GLOBAL</span></span> 
  
> <span data-ttu-id="5b0ec-133">全局通讯簿。</span><span class="sxs-lookup"><span data-stu-id="5b0ec-133">A global address book.</span></span>
    
<span data-ttu-id="5b0ec-134">DT_LOCAL</span><span class="sxs-lookup"><span data-stu-id="5b0ec-134">DT_LOCAL</span></span> 
  
> <span data-ttu-id="5b0ec-135">与小型工作组共享的本地通讯簿。</span><span class="sxs-lookup"><span data-stu-id="5b0ec-135">A local address book that you share with a small workgroup.</span></span>
    
<span data-ttu-id="5b0ec-136">DT_MAILUSER</span><span class="sxs-lookup"><span data-stu-id="5b0ec-136">DT_MAILUSER</span></span> 
  
> <span data-ttu-id="5b0ec-137">典型的消息传递用户。</span><span class="sxs-lookup"><span data-stu-id="5b0ec-137">A typical messaging user.</span></span>
    
<span data-ttu-id="5b0ec-138">DT_MODIFIABLE</span><span class="sxs-lookup"><span data-stu-id="5b0ec-138">DT_MODIFIABLE</span></span> 
  
> <span data-ttu-id="5b0ec-139">可修改;容器在用户界面中应表示为可修改。</span><span class="sxs-lookup"><span data-stu-id="5b0ec-139">Modifiable; the container should be denoted as modifiable in the user interface.</span></span>
    
<span data-ttu-id="5b0ec-140">DT_NOT_SPECIFIC</span><span class="sxs-lookup"><span data-stu-id="5b0ec-140">DT_NOT_SPECIFIC</span></span> 
  
> <span data-ttu-id="5b0ec-141">与任何其他设置都不匹配。</span><span class="sxs-lookup"><span data-stu-id="5b0ec-141">Does not match any of the other settings.</span></span>
    
<span data-ttu-id="5b0ec-142">DT_ORGANIZATION</span><span class="sxs-lookup"><span data-stu-id="5b0ec-142">DT_ORGANIZATION</span></span> 
  
> <span data-ttu-id="5b0ec-143">为大型组（如支持人员、会计或驱动协调器）定义的特殊别名。</span><span class="sxs-lookup"><span data-stu-id="5b0ec-143">A special alias defined for a large group, such as helpdesk, accounting, or blood-drive coordinator.</span></span>
    
<span data-ttu-id="5b0ec-144">DT_PRIVATE_DISTLIST</span><span class="sxs-lookup"><span data-stu-id="5b0ec-144">DT_PRIVATE_DISTLIST</span></span> 
  
> <span data-ttu-id="5b0ec-145">个人管理的专用通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="5b0ec-145">A private, personally administered distribution list.</span></span>
    
<span data-ttu-id="5b0ec-146">DT_REMOTE_MAILUSER</span><span class="sxs-lookup"><span data-stu-id="5b0ec-146">DT_REMOTE_MAILUSER</span></span> 
  
> <span data-ttu-id="5b0ec-147">已知来自外向或远程邮件系统的收件人。</span><span class="sxs-lookup"><span data-stu-id="5b0ec-147">A recipient known to be from a foreign or remote messaging system.</span></span>
    
<span data-ttu-id="5b0ec-148">DT_WAN</span><span class="sxs-lookup"><span data-stu-id="5b0ec-148">DT_WAN</span></span> 
  
> <span data-ttu-id="5b0ec-149">广区域网络通讯簿。</span><span class="sxs-lookup"><span data-stu-id="5b0ec-149">A wide area network address book.</span></span>
    
<span data-ttu-id="5b0ec-150">通讯簿内容表使用 DT_AGENT、DT_DISTLIST、DT_FORUM、DT_MAILUSER、DT_ORGANIZATION、DT_PRIVATE_DISTLIST 和 DT_REMOTE_MAILUSER 值。</span><span class="sxs-lookup"><span data-stu-id="5b0ec-150">Address book contents tables use the DT_AGENT, DT_DISTLIST, DT_FORUM, DT_MAILUSER, DT_ORGANIZATION, DT_PRIVATE_DISTLIST, and DT_REMOTE_MAILUSER values.</span></span> <span data-ttu-id="5b0ec-151">通讯簿层次结构表和一对表使用 DT_GLOBAL、DT_LOCAL、DT_MODIFIABLE、DT_NOT_SPECIFIC 和 DT_WAN 值。</span><span class="sxs-lookup"><span data-stu-id="5b0ec-151">Address book hierarchy tables and one-off tables use the DT_GLOBAL, DT_LOCAL, DT_MODIFIABLE, DT_NOT_SPECIFIC, and DT_WAN values.</span></span> <span data-ttu-id="5b0ec-152">文件夹层次结构表使用 DT_FOLDER、DT_FOLDER_LINK 和 DT_FOLDER_SPECIAL 值。</span><span class="sxs-lookup"><span data-stu-id="5b0ec-152">Folder hierarchy tables use the DT_FOLDER, DT_FOLDER_LINK, and DT_FOLDER_SPECIAL values.</span></span> 
  
<span data-ttu-id="5b0ec-153">如果未设置此属性，客户端应假定适合表的默认类型，通常为 DT_FOLDER、DT_LOCAL 或 DT_MAILUSER。</span><span class="sxs-lookup"><span data-stu-id="5b0ec-153">If this property is not set, the client should assume the default type appropriate for the table, typically DT_FOLDER, DT_LOCAL, or DT_MAILUSER.</span></span> 
  
 <span data-ttu-id="5b0ec-154">**注意** 未记录的所有值都保留用于 MAPI。</span><span class="sxs-lookup"><span data-stu-id="5b0ec-154">**Note** All values not documented are reserved for MAPI.</span></span> <span data-ttu-id="5b0ec-155">客户端应用程序不得定义任何新值，并且必须准备处理未记录的值。</span><span class="sxs-lookup"><span data-stu-id="5b0ec-155">Client applications must not define any new values and must be prepared to deal with an undocumented value.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="5b0ec-156">相关资源</span><span class="sxs-lookup"><span data-stu-id="5b0ec-156">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="5b0ec-157">协议规范</span><span class="sxs-lookup"><span data-stu-id="5b0ec-157">Protocol specifications</span></span>

<span data-ttu-id="5b0ec-158">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="5b0ec-158">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="5b0ec-159">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="5b0ec-159">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="5b0ec-160">[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="5b0ec-160">[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="5b0ec-161">处理邮件和附件对象。</span><span class="sxs-lookup"><span data-stu-id="5b0ec-161">Handles message and attachment objects.</span></span>
    
<span data-ttu-id="5b0ec-162">[[MS-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="5b0ec-162">[[MS-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="5b0ec-163">指定允许通讯簿模板使用的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="5b0ec-163">Specifies the properties and operations that are permissible for address book templates.</span></span>
    
<span data-ttu-id="5b0ec-164">[[MS-OXLDAP]](https://msdn.microsoft.com/library/727c090a-f05c-4eed-94aa-565724cfc550%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="5b0ec-164">[[MS-OXLDAP]](https://msdn.microsoft.com/library/727c090a-f05c-4eed-94aa-565724cfc550%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="5b0ec-165">启用目录访问。</span><span class="sxs-lookup"><span data-stu-id="5b0ec-165">Enables directory access.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="5b0ec-166">头文件</span><span class="sxs-lookup"><span data-stu-id="5b0ec-166">Header files</span></span>

<span data-ttu-id="5b0ec-167">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="5b0ec-167">Mapidefs.h</span></span>
  
> <span data-ttu-id="5b0ec-168">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="5b0ec-168">Provides data type definitions.</span></span>
    
<span data-ttu-id="5b0ec-169">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="5b0ec-169">Mapitags.h</span></span>
  
> <span data-ttu-id="5b0ec-170">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="5b0ec-170">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="5b0ec-171">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5b0ec-171">See also</span></span>



[<span data-ttu-id="5b0ec-172">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="5b0ec-172">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="5b0ec-173">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="5b0ec-173">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="5b0ec-174">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="5b0ec-174">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="5b0ec-175">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="5b0ec-175">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

