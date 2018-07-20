---
title: PidTagDisplayName 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagDisplayName
api_type:
- HeaderDef
ms.assetid: bd094e00-5c60-4bb3-9a45-b943fab52876
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: d914d071d0845dee7d402e45d281cd774095a5a0
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777587"
---
# <a name="pidtagdisplayname-canonical-property"></a><span data-ttu-id="707b1-103">PidTagDisplayName 规范属性</span><span class="sxs-lookup"><span data-stu-id="707b1-103">PidTagDisplayName Canonical Property</span></span>

  
  
<span data-ttu-id="707b1-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="707b1-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="707b1-105">包含给定的 MAPI 对象的显示名称。</span><span class="sxs-lookup"><span data-stu-id="707b1-105">Contains the display name for a given MAPI object.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="707b1-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="707b1-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="707b1-107">PR_DISPLAY_NAME，PR_DISPLAY_NAME_A，PR_DISPLAY_NAME_W</span><span class="sxs-lookup"><span data-stu-id="707b1-107">PR_DISPLAY_NAME, PR_DISPLAY_NAME_A, PR_DISPLAY_NAME_W</span></span>  <br/> |
|<span data-ttu-id="707b1-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="707b1-108">Identifier:</span></span>  <br/> |<span data-ttu-id="707b1-109">0x3001</span><span class="sxs-lookup"><span data-stu-id="707b1-109">0x3001</span></span>  <br/> |
|<span data-ttu-id="707b1-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="707b1-110">Data type:</span></span>  <br/> |<span data-ttu-id="707b1-111">PT_STRING8 PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="707b1-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="707b1-112">区域：</span><span class="sxs-lookup"><span data-stu-id="707b1-112">Area:</span></span>  <br/> |<span data-ttu-id="707b1-113">常见的 MAPI</span><span class="sxs-lookup"><span data-stu-id="707b1-113">MAPI common</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="707b1-114">备注</span><span class="sxs-lookup"><span data-stu-id="707b1-114">Remarks</span></span>

<span data-ttu-id="707b1-115">文件夹要求同级子文件夹具有唯一的显示名称。</span><span class="sxs-lookup"><span data-stu-id="707b1-115">Folders require sibling subfolders to have unique display names.</span></span> <span data-ttu-id="707b1-116">例如，如果文件夹包含两个子文件夹，两个子文件夹无法对此属性使用相同的值。</span><span class="sxs-lookup"><span data-stu-id="707b1-116">For example, if a folder contains two subfolders, the two subfolders cannot use the same value for this property.</span></span> <span data-ttu-id="707b1-117">此限制不适用于其他容器，如通讯簿和通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="707b1-117">This restriction does not apply to other containers, such as address books and distribution lists.</span></span> 
  
<span data-ttu-id="707b1-118">服务提供商应将此属性的值，以使其包含的提供程序类型和配置信息。</span><span class="sxs-lookup"><span data-stu-id="707b1-118">Service providers should set the value of this property so that it contains both the provider type and configuration information.</span></span> <span data-ttu-id="707b1-119">其他信息有助于区分同一类型的提供程序的实例。</span><span class="sxs-lookup"><span data-stu-id="707b1-119">The additional information helps to distinguish between instances of providers of the same type.</span></span> <span data-ttu-id="707b1-120">未配置提供程序应使用命名提供程序的字符串。</span><span class="sxs-lookup"><span data-stu-id="707b1-120">Unconfigured providers should use a string that names the provider.</span></span> <span data-ttu-id="707b1-121">配置提供程序应使用括号的区分字符串后跟相同的字符串。</span><span class="sxs-lookup"><span data-stu-id="707b1-121">Configured providers should use the same string followed by a distinguishing string in parentheses.</span></span> <span data-ttu-id="707b1-122">例如，未配置的消息存储提供程序可能会将这些属性设置为：</span><span class="sxs-lookup"><span data-stu-id="707b1-122">For example, an unconfigured message store provider might set these properties to:</span></span> 
  
<span data-ttu-id="707b1-123">个人信息存储</span><span class="sxs-lookup"><span data-stu-id="707b1-123">Personal Information Store</span></span>
  
<span data-ttu-id="707b1-124">已配置的版本然后无法将这些属性设置为：</span><span class="sxs-lookup"><span data-stu-id="707b1-124">The configured version could then set these properties to:</span></span> 
  
<span data-ttu-id="707b1-125">个人信息存储 （1998 年 2 月 6日日）</span><span class="sxs-lookup"><span data-stu-id="707b1-125">Personal Information Store (February 6, 1998)</span></span>
  
<span data-ttu-id="707b1-126">对于状态对象，这些属性包含可显示用户界面组件的名称。</span><span class="sxs-lookup"><span data-stu-id="707b1-126">For status objects, these properties contain the name of the component that can be displayed by the user interface.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="707b1-127">MAPI 消息中的收件人姓名中不能使用分号。</span><span class="sxs-lookup"><span data-stu-id="707b1-127">Semicolons cannot be used within recipient names in MAPI messaging.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="707b1-128">相关资源</span><span class="sxs-lookup"><span data-stu-id="707b1-128">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="707b1-129">协议规范</span><span class="sxs-lookup"><span data-stu-id="707b1-129">Protocol specifications</span></span>

<span data-ttu-id="707b1-130">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="707b1-130">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="707b1-131">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="707b1-131">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="707b1-132">[[MS OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="707b1-132">[[MS-OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="707b1-133">处理邮件和附件的对象。</span><span class="sxs-lookup"><span data-stu-id="707b1-133">Handles message and attachment objects.</span></span>
    
<span data-ttu-id="707b1-134">[[MS OXCFOLD]](http://msdn.microsoft.com/library/c0f31b95-c07f-486c-98d9-535ed9705fbf%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="707b1-134">[[MS-OXCFOLD]](http://msdn.microsoft.com/library/c0f31b95-c07f-486c-98d9-535ed9705fbf%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="707b1-135">处理文件夹的操作。</span><span class="sxs-lookup"><span data-stu-id="707b1-135">Handles folder operations.</span></span>
    
<span data-ttu-id="707b1-136">[[MS OXOCNTC]](http://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="707b1-136">[[MS-OXOCNTC]](http://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="707b1-137">指定的属性和操作所允许的联系人和个人通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="707b1-137">Specifies the properties and operations that are permissible for contacts and personal distribution lists.</span></span>
    
<span data-ttu-id="707b1-138">[[MS OXOABK]](http://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="707b1-138">[[MS-OXOABK]](http://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="707b1-139">指定的属性和用户、 联系人、 组和资源的操作列表。</span><span class="sxs-lookup"><span data-stu-id="707b1-139">Specifies the properties and operations for lists of users, contacts, groups, and resources.</span></span>
    
<span data-ttu-id="707b1-140">[[MS OXCMAIL]](http://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="707b1-140">[[MS-OXCMAIL]](http://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="707b1-141">从 Internet 标准电子邮件约定转换为消息对象。</span><span class="sxs-lookup"><span data-stu-id="707b1-141">Converts from Internet standard email conventions to message objects.</span></span>
    
<span data-ttu-id="707b1-142">[[MS XWDVSEC]](http://msdn.microsoft.com/library/dc043d09-6b76-4392-aea3-68f8e81c64d8%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="707b1-142">[[MS-XWDVSEC]](http://msdn.microsoft.com/library/dc043d09-6b76-4392-aea3-68f8e81c64d8%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="707b1-143">扩展指定如何请求和设置通过 WebDAV 方法的 Exchange 安全描述符的 WebDAV 协议。</span><span class="sxs-lookup"><span data-stu-id="707b1-143">Extends the WebDAV protocol that specifies how to request and set the Exchange security descriptor via WebDAV methods.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="707b1-144">头文件</span><span class="sxs-lookup"><span data-stu-id="707b1-144">Header files</span></span>

<span data-ttu-id="707b1-145">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="707b1-145">Mapidefs.h</span></span>
  
> <span data-ttu-id="707b1-146">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="707b1-146">Provides data type definitions.</span></span>
    
<span data-ttu-id="707b1-147">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="707b1-147">Mapitags.h</span></span>
  
> <span data-ttu-id="707b1-148">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="707b1-148">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="707b1-149">另请参阅</span><span class="sxs-lookup"><span data-stu-id="707b1-149">See also</span></span>



[<span data-ttu-id="707b1-150">PidTagTransmittableDisplayName 规范属性</span><span class="sxs-lookup"><span data-stu-id="707b1-150">PidTagTransmittableDisplayName Canonical Property</span></span>](pidtagtransmittabledisplayname-canonical-property.md)


[<span data-ttu-id="707b1-151">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="707b1-151">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="707b1-152">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="707b1-152">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="707b1-153">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="707b1-153">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="707b1-154">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="707b1-154">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)
