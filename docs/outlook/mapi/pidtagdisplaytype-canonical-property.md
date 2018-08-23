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
ms.openlocfilehash: 5b067b3bc38df978cd0f4c52beb37579619edc24
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22583510"
---
# <a name="pidtagdisplaytype-canonical-property"></a><span data-ttu-id="c4da9-103">PidTagDisplayType 规范属性</span><span class="sxs-lookup"><span data-stu-id="c4da9-103">PidTagDisplayType Canonical Property</span></span>

  
  
<span data-ttu-id="c4da9-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="c4da9-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="c4da9-105">包含用于将图标与特定的表格行关联的值。</span><span class="sxs-lookup"><span data-stu-id="c4da9-105">Contains a value used to associate an icon with a particular row of a table.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="c4da9-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="c4da9-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="c4da9-107">PR_DISPLAY_TYPE</span><span class="sxs-lookup"><span data-stu-id="c4da9-107">PR_DISPLAY_TYPE</span></span>  <br/> |
|<span data-ttu-id="c4da9-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="c4da9-108">Identifier:</span></span>  <br/> |<span data-ttu-id="c4da9-109">0x3900</span><span class="sxs-lookup"><span data-stu-id="c4da9-109">0x3900</span></span>  <br/> |
|<span data-ttu-id="c4da9-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="c4da9-110">Data type:</span></span>  <br/> |<span data-ttu-id="c4da9-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="c4da9-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="c4da9-112">区域：</span><span class="sxs-lookup"><span data-stu-id="c4da9-112">Area:</span></span>  <br/> |<span data-ttu-id="c4da9-113">MAPI 通讯簿</span><span class="sxs-lookup"><span data-stu-id="c4da9-113">MAPI address book</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="c4da9-114">注解</span><span class="sxs-lookup"><span data-stu-id="c4da9-114">Remarks</span></span>

<span data-ttu-id="c4da9-115">此属性包含长整型，从而便于在其类型基于的表项的特殊处理。</span><span class="sxs-lookup"><span data-stu-id="c4da9-115">This property contains a long integer that facilitates special treatment of the table entry based on its type.</span></span> <span data-ttu-id="c4da9-116">显示的图标或其他 display 元素的显示类型相关联的通常包含此特殊处理。</span><span class="sxs-lookup"><span data-stu-id="c4da9-116">This special treatment typically consists of displaying an icon, or other display element, associated with the display type.</span></span> 
  
<span data-ttu-id="c4da9-117">文件夹内容表中不使用此属性。</span><span class="sxs-lookup"><span data-stu-id="c4da9-117">This property is not used in folder contents tables.</span></span> <span data-ttu-id="c4da9-118">客户端应用程序应使用消息的**PR_MESSAGE_CLASS** ([PidTagMessageClass](pidtagmessageclass-canonical-property.md)) 属性和相应的[IMAPIFormInfo](imapiforminfoimapiprop.md)接口要获取的**PR_ICON** ([PidTagIcon](pidtagicon-canonical-property.md)) 和**PR_MINI_ICON** ([PidTagMiniIcon](pidtagminiicon-canonical-property.md)) 的邮件的属性。</span><span class="sxs-lookup"><span data-stu-id="c4da9-118">Client applications should use a message's **PR_MESSAGE_CLASS** ([PidTagMessageClass](pidtagmessageclass-canonical-property.md)) property and appropriate [IMAPIFormInfo](imapiforminfoimapiprop.md) interface to get the **PR_ICON** ([PidTagIcon](pidtagicon-canonical-property.md)) and **PR_MINI_ICON** ([PidTagMiniIcon](pidtagminiicon-canonical-property.md)) properties for that message.</span></span> 
  
<span data-ttu-id="c4da9-119">此属性可以具有完全下列值之一：</span><span class="sxs-lookup"><span data-stu-id="c4da9-119">This property can have exactly one of the following values:</span></span>
  
<span data-ttu-id="c4da9-120">DT_AGENT</span><span class="sxs-lookup"><span data-stu-id="c4da9-120">DT_AGENT</span></span> 
  
> <span data-ttu-id="c4da9-121">自动的代理，如天报价单或天气图表的显示。</span><span class="sxs-lookup"><span data-stu-id="c4da9-121">An automated agent, such as Quote-Of-The-Day or a weather chart display.</span></span>
    
<span data-ttu-id="c4da9-122">DT_DISTLIST</span><span class="sxs-lookup"><span data-stu-id="c4da9-122">DT_DISTLIST</span></span> 
  
> <span data-ttu-id="c4da9-123">通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="c4da9-123">A distribution list.</span></span>
    
<span data-ttu-id="c4da9-124">DT_FOLDER</span><span class="sxs-lookup"><span data-stu-id="c4da9-124">DT_FOLDER</span></span> 
  
> <span data-ttu-id="c4da9-125">显示默认文件夹图标紧邻文件夹。</span><span class="sxs-lookup"><span data-stu-id="c4da9-125">Display default folder icon adjacent to folder.</span></span>
    
<span data-ttu-id="c4da9-126">DT_FOLDER_LINK</span><span class="sxs-lookup"><span data-stu-id="c4da9-126">DT_FOLDER_LINK</span></span> 
  
> <span data-ttu-id="c4da9-127">显示默认文件夹链接图标紧邻文件夹，而不是默认文件夹图标。</span><span class="sxs-lookup"><span data-stu-id="c4da9-127">Display default folder link icon adjacent to folder rather than the default folder icon.</span></span>
    
<span data-ttu-id="c4da9-128">DT_FOLDER_SPECIAL</span><span class="sxs-lookup"><span data-stu-id="c4da9-128">DT_FOLDER_SPECIAL</span></span> 
  
> <span data-ttu-id="c4da9-129">显示特定于应用程序的差异，如一个特殊类型的公用文件夹的文件夹的图标。</span><span class="sxs-lookup"><span data-stu-id="c4da9-129">Display icon for a folder with an application-specific distinction, such as a special type of public folder.</span></span>
    
<span data-ttu-id="c4da9-130">DT_FORUM</span><span class="sxs-lookup"><span data-stu-id="c4da9-130">DT_FORUM</span></span> 
  
> <span data-ttu-id="c4da9-131">论坛，如布告栏服务或公共或共享文件夹。</span><span class="sxs-lookup"><span data-stu-id="c4da9-131">A forum, such as a bulletin board service or a public or shared folder.</span></span>
    
<span data-ttu-id="c4da9-132">DT_GLOBAL</span><span class="sxs-lookup"><span data-stu-id="c4da9-132">DT_GLOBAL</span></span> 
  
> <span data-ttu-id="c4da9-133">全局通讯簿。</span><span class="sxs-lookup"><span data-stu-id="c4da9-133">A global address book.</span></span>
    
<span data-ttu-id="c4da9-134">DT_LOCAL</span><span class="sxs-lookup"><span data-stu-id="c4da9-134">DT_LOCAL</span></span> 
  
> <span data-ttu-id="c4da9-135">与小型工作组共享本地通讯簿。</span><span class="sxs-lookup"><span data-stu-id="c4da9-135">A local address book that you share with a small workgroup.</span></span>
    
<span data-ttu-id="c4da9-136">DT_MAILUSER</span><span class="sxs-lookup"><span data-stu-id="c4da9-136">DT_MAILUSER</span></span> 
  
> <span data-ttu-id="c4da9-137">典型的消息用户。</span><span class="sxs-lookup"><span data-stu-id="c4da9-137">A typical messaging user.</span></span>
    
<span data-ttu-id="c4da9-138">DT_MODIFIABLE</span><span class="sxs-lookup"><span data-stu-id="c4da9-138">DT_MODIFIABLE</span></span> 
  
> <span data-ttu-id="c4da9-139">可修改;在用户界面中，应为可修改表示容器。</span><span class="sxs-lookup"><span data-stu-id="c4da9-139">Modifiable; the container should be denoted as modifiable in the user interface.</span></span>
    
<span data-ttu-id="c4da9-140">DT_NOT_SPECIFIC</span><span class="sxs-lookup"><span data-stu-id="c4da9-140">DT_NOT_SPECIFIC</span></span> 
  
> <span data-ttu-id="c4da9-141">不匹配的任何其他设置。</span><span class="sxs-lookup"><span data-stu-id="c4da9-141">Does not match any of the other settings.</span></span>
    
<span data-ttu-id="c4da9-142">DT_ORGANIZATION</span><span class="sxs-lookup"><span data-stu-id="c4da9-142">DT_ORGANIZATION</span></span> 
  
> <span data-ttu-id="c4da9-143">定义一大组，如帮助台、 accounting 或血驱动器协调特殊别名。</span><span class="sxs-lookup"><span data-stu-id="c4da9-143">A special alias defined for a large group, such as helpdesk, accounting, or blood-drive coordinator.</span></span>
    
<span data-ttu-id="c4da9-144">DT_PRIVATE_DISTLIST</span><span class="sxs-lookup"><span data-stu-id="c4da9-144">DT_PRIVATE_DISTLIST</span></span> 
  
> <span data-ttu-id="c4da9-145">专用的个人管理通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="c4da9-145">A private, personally administered distribution list.</span></span>
    
<span data-ttu-id="c4da9-146">DT_REMOTE_MAILUSER</span><span class="sxs-lookup"><span data-stu-id="c4da9-146">DT_REMOTE_MAILUSER</span></span> 
  
> <span data-ttu-id="c4da9-147">已知要从外部或远程邮件系统的收件人。</span><span class="sxs-lookup"><span data-stu-id="c4da9-147">A recipient known to be from a foreign or remote messaging system.</span></span>
    
<span data-ttu-id="c4da9-148">DT_WAN</span><span class="sxs-lookup"><span data-stu-id="c4da9-148">DT_WAN</span></span> 
  
> <span data-ttu-id="c4da9-149">广域网网络通讯簿。</span><span class="sxs-lookup"><span data-stu-id="c4da9-149">A wide area network address book.</span></span>
    
<span data-ttu-id="c4da9-150">通讯簿内容表使用 DT_AGENT、 DT_DISTLIST、 DT_FORUM、 DT_MAILUSER、 DT_ORGANIZATION、 DT_PRIVATE_DISTLIST 和 DT_REMOTE_MAILUSER 值。</span><span class="sxs-lookup"><span data-stu-id="c4da9-150">Address book contents tables use the DT_AGENT, DT_DISTLIST, DT_FORUM, DT_MAILUSER, DT_ORGANIZATION, DT_PRIVATE_DISTLIST, and DT_REMOTE_MAILUSER values.</span></span> <span data-ttu-id="c4da9-151">通讯簿层次结构表和一次性表使用 DT_GLOBAL、 DT_LOCAL、 DT_MODIFIABLE、 DT_NOT_SPECIFIC 和 DT_WAN 值。</span><span class="sxs-lookup"><span data-stu-id="c4da9-151">Address book hierarchy tables and one-off tables use the DT_GLOBAL, DT_LOCAL, DT_MODIFIABLE, DT_NOT_SPECIFIC, and DT_WAN values.</span></span> <span data-ttu-id="c4da9-152">文件夹层次结构表使用 DT_FOLDER、 DT_FOLDER_LINK 和 DT_FOLDER_SPECIAL 值。</span><span class="sxs-lookup"><span data-stu-id="c4da9-152">Folder hierarchy tables use the DT_FOLDER, DT_FOLDER_LINK, and DT_FOLDER_SPECIAL values.</span></span> 
  
<span data-ttu-id="c4da9-153">如果未设置此属性，客户端应采用默认类型适用于表、 通常 DT_FOLDER、 DT_LOCAL 或 DT_MAILUSER。</span><span class="sxs-lookup"><span data-stu-id="c4da9-153">If this property is not set, the client should assume the default type appropriate for the table, typically DT_FOLDER, DT_LOCAL, or DT_MAILUSER.</span></span> 
  
 <span data-ttu-id="c4da9-154">**注释**MAPI 的保留未进行归档的所有值。</span><span class="sxs-lookup"><span data-stu-id="c4da9-154">**Note** All values not documented are reserved for MAPI.</span></span> <span data-ttu-id="c4da9-155">客户端应用程序无需定义的任何新值，必须在准备好处理一个未记录的值。</span><span class="sxs-lookup"><span data-stu-id="c4da9-155">Client applications must not define any new values and must be prepared to deal with an undocumented value.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="c4da9-156">相关资源</span><span class="sxs-lookup"><span data-stu-id="c4da9-156">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="c4da9-157">协议规范</span><span class="sxs-lookup"><span data-stu-id="c4da9-157">Protocol specifications</span></span>

<span data-ttu-id="c4da9-158">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="c4da9-158">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="c4da9-159">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="c4da9-159">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="c4da9-160">[[MS OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="c4da9-160">[[MS-OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="c4da9-161">处理邮件和附件的对象。</span><span class="sxs-lookup"><span data-stu-id="c4da9-161">Handles message and attachment objects.</span></span>
    
<span data-ttu-id="c4da9-162">[[MS OXOABK]](http://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="c4da9-162">[[MS-OXOABK]](http://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="c4da9-163">指定的属性和操作所允许的地址簿模板。</span><span class="sxs-lookup"><span data-stu-id="c4da9-163">Specifies the properties and operations that are permissible for address book templates.</span></span>
    
<span data-ttu-id="c4da9-164">[[MS OXLDAP]](http://msdn.microsoft.com/library/727c090a-f05c-4eed-94aa-565724cfc550%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="c4da9-164">[[MS-OXLDAP]](http://msdn.microsoft.com/library/727c090a-f05c-4eed-94aa-565724cfc550%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="c4da9-165">启用目录访问。</span><span class="sxs-lookup"><span data-stu-id="c4da9-165">Enables directory access.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="c4da9-166">头文件</span><span class="sxs-lookup"><span data-stu-id="c4da9-166">Header files</span></span>

<span data-ttu-id="c4da9-167">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="c4da9-167">Mapidefs.h</span></span>
  
> <span data-ttu-id="c4da9-168">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="c4da9-168">Provides data type definitions.</span></span>
    
<span data-ttu-id="c4da9-169">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="c4da9-169">Mapitags.h</span></span>
  
> <span data-ttu-id="c4da9-170">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="c4da9-170">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="c4da9-171">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c4da9-171">See also</span></span>



[<span data-ttu-id="c4da9-172">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="c4da9-172">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="c4da9-173">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="c4da9-173">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="c4da9-174">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="c4da9-174">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="c4da9-175">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="c4da9-175">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

