---
title: PidTagObjectType 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagObjectType
api_type:
- HeaderDef
ms.assetid: 37da4ff5-300d-479f-a8b4-6fc36df997d9
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 2830da6aad561045a7ecdd953286c90edea88ca2
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777899"
---
# <a name="pidtagobjecttype-canonical-property"></a><span data-ttu-id="fed3b-103">PidTagObjectType 规范属性</span><span class="sxs-lookup"><span data-stu-id="fed3b-103">PidTagObjectType Canonical Property</span></span>

  
  
<span data-ttu-id="fed3b-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="fed3b-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="fed3b-105">包含对象的类型。</span><span class="sxs-lookup"><span data-stu-id="fed3b-105">Contains the type of an object.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="fed3b-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="fed3b-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="fed3b-107">PR_OBJECT_TYPE</span><span class="sxs-lookup"><span data-stu-id="fed3b-107">PR_OBJECT_TYPE</span></span>  <br/> |
|<span data-ttu-id="fed3b-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="fed3b-108">Identifier:</span></span>  <br/> |<span data-ttu-id="fed3b-109">0x0FFE</span><span class="sxs-lookup"><span data-stu-id="fed3b-109">0x0FFE</span></span>  <br/> |
|<span data-ttu-id="fed3b-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="fed3b-110">Data type:</span></span>  <br/> |<span data-ttu-id="fed3b-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="fed3b-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="fed3b-112">区域：</span><span class="sxs-lookup"><span data-stu-id="fed3b-112">Area:</span></span>  <br/> |<span data-ttu-id="fed3b-113">Common</span><span class="sxs-lookup"><span data-stu-id="fed3b-113">Common</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="fed3b-114">说明</span><span class="sxs-lookup"><span data-stu-id="fed3b-114">Remarks</span></span>

<span data-ttu-id="fed3b-115">此属性中包含的对象类型对应于可用于通过**OpenEntry**界面访问对象的主接口。</span><span class="sxs-lookup"><span data-stu-id="fed3b-115">The object type contained in this property corresponds to the primary interface available for an object accessible through the **OpenEntry** interface.</span></span> <span data-ttu-id="fed3b-116">它通常是由咨询相应**OpenEntry**方法返回的_lpulObjType_参数中获取。</span><span class="sxs-lookup"><span data-stu-id="fed3b-116">It is usually obtained by consulting the  _lpulObjType_ parameter returned by the appropriate **OpenEntry** method.</span></span> <span data-ttu-id="fed3b-117">以其他方式获取接口后，调用[IMAPIProp::GetProps](imapiprop-getprops.md)获取此属性的值。</span><span class="sxs-lookup"><span data-stu-id="fed3b-117">When the interface is obtained in other ways, call [IMAPIProp::GetProps](imapiprop-getprops.md) to obtain the value for this property.</span></span> 
  
<span data-ttu-id="fed3b-118">此属性可以具有完全下列值之一：</span><span class="sxs-lookup"><span data-stu-id="fed3b-118">This property can have exactly one of the following values:</span></span>
  
<span data-ttu-id="fed3b-119">MAPI_ABCONT</span><span class="sxs-lookup"><span data-stu-id="fed3b-119">MAPI_ABCONT</span></span> 
  
> <span data-ttu-id="fed3b-120">通讯簿容器对象</span><span class="sxs-lookup"><span data-stu-id="fed3b-120">Address book container object</span></span> 
    
<span data-ttu-id="fed3b-121">MAPI_ADDRBOOK</span><span class="sxs-lookup"><span data-stu-id="fed3b-121">MAPI_ADDRBOOK</span></span> 
  
> <span data-ttu-id="fed3b-122">通讯簿对象</span><span class="sxs-lookup"><span data-stu-id="fed3b-122">Address book object</span></span> 
    
<span data-ttu-id="fed3b-123">MAPI_ATTACH</span><span class="sxs-lookup"><span data-stu-id="fed3b-123">MAPI_ATTACH</span></span> 
  
> <span data-ttu-id="fed3b-124">消息 attachment 对象</span><span class="sxs-lookup"><span data-stu-id="fed3b-124">Message attachment object</span></span> 
    
<span data-ttu-id="fed3b-125">MAPI_DISTLIST</span><span class="sxs-lookup"><span data-stu-id="fed3b-125">MAPI_DISTLIST</span></span> 
  
> <span data-ttu-id="fed3b-126">通讯组列表对象</span><span class="sxs-lookup"><span data-stu-id="fed3b-126">Distribution list object</span></span> 
    
<span data-ttu-id="fed3b-127">MAPI_FOLDER</span><span class="sxs-lookup"><span data-stu-id="fed3b-127">MAPI_FOLDER</span></span> 
  
> <span data-ttu-id="fed3b-128">文件夹对象</span><span class="sxs-lookup"><span data-stu-id="fed3b-128">Folder object</span></span> 
    
<span data-ttu-id="fed3b-129">MAPI_FORMINFO</span><span class="sxs-lookup"><span data-stu-id="fed3b-129">MAPI_FORMINFO</span></span> 
  
> <span data-ttu-id="fed3b-130">Form 对象</span><span class="sxs-lookup"><span data-stu-id="fed3b-130">Form object</span></span> 
    
<span data-ttu-id="fed3b-131">MAPI_MAILUSER</span><span class="sxs-lookup"><span data-stu-id="fed3b-131">MAPI_MAILUSER</span></span> 
  
> <span data-ttu-id="fed3b-132">邮件用户对象</span><span class="sxs-lookup"><span data-stu-id="fed3b-132">Messaging user object</span></span> 
    
<span data-ttu-id="fed3b-133">MAPI_MESSAGE</span><span class="sxs-lookup"><span data-stu-id="fed3b-133">MAPI_MESSAGE</span></span> 
  
> <span data-ttu-id="fed3b-134">Message 对象</span><span class="sxs-lookup"><span data-stu-id="fed3b-134">Message object</span></span> 
    
<span data-ttu-id="fed3b-135">MAPI_PROFSECT</span><span class="sxs-lookup"><span data-stu-id="fed3b-135">MAPI_PROFSECT</span></span> 
  
> <span data-ttu-id="fed3b-136">配置文件 section 对象</span><span class="sxs-lookup"><span data-stu-id="fed3b-136">Profile section object</span></span> 
    
<span data-ttu-id="fed3b-137">MAPI_SESSION</span><span class="sxs-lookup"><span data-stu-id="fed3b-137">MAPI_SESSION</span></span> 
  
> <span data-ttu-id="fed3b-138">会话对象</span><span class="sxs-lookup"><span data-stu-id="fed3b-138">Session object</span></span> 
    
<span data-ttu-id="fed3b-139">MAPI_STATUS</span><span class="sxs-lookup"><span data-stu-id="fed3b-139">MAPI_STATUS</span></span> 
  
> <span data-ttu-id="fed3b-140">状态对象</span><span class="sxs-lookup"><span data-stu-id="fed3b-140">Status object</span></span> 
    
<span data-ttu-id="fed3b-141">MAPI_STORE</span><span class="sxs-lookup"><span data-stu-id="fed3b-141">MAPI_STORE</span></span> 
  
> <span data-ttu-id="fed3b-142">消息存储对象</span><span class="sxs-lookup"><span data-stu-id="fed3b-142">Message store object</span></span>
    
## <a name="related-resources"></a><span data-ttu-id="fed3b-143">相关资源</span><span class="sxs-lookup"><span data-stu-id="fed3b-143">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="fed3b-144">协议规范</span><span class="sxs-lookup"><span data-stu-id="fed3b-144">Protocol specifications</span></span>

<span data-ttu-id="fed3b-145">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="fed3b-145">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="fed3b-146">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="fed3b-146">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="fed3b-147">[[MS OXOABK]](http://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="fed3b-147">[[MS-OXOABK]](http://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="fed3b-148">指定的属性和用户、 联系人、 组和资源的操作列表。</span><span class="sxs-lookup"><span data-stu-id="fed3b-148">Specifies the properties and operations for lists of users, contacts, groups, and resources.</span></span>
    
<span data-ttu-id="fed3b-149">[[MS NSPI]](http://msdn.microsoft.com/library/6dd0a3ea-b4d4-4a73-a857-add03a89a543%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="fed3b-149">[[MS-NSPI]](http://msdn.microsoft.com/library/6dd0a3ea-b4d4-4a73-a857-add03a89a543%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="fed3b-150">处理与名称服务提供程序界面 (NSPI) 服务器的客户端的通信。</span><span class="sxs-lookup"><span data-stu-id="fed3b-150">Handles a client's communications with a Name Service Provider Interface (NSPI) server.</span></span>
    
<span data-ttu-id="fed3b-151">[[MS OXCFOLD]](http://msdn.microsoft.com/library/c0f31b95-c07f-486c-98d9-535ed9705fbf%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="fed3b-151">[[MS-OXCFOLD]](http://msdn.microsoft.com/library/c0f31b95-c07f-486c-98d9-535ed9705fbf%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="fed3b-152">处理文件夹的操作。</span><span class="sxs-lookup"><span data-stu-id="fed3b-152">Handles folder operations.</span></span>
    
<span data-ttu-id="fed3b-153">[[MS OXCFXICS]](http://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="fed3b-153">[[MS-OXCFXICS]](http://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="fed3b-154">处理顺序和客户端和服务器之间的数据传输的流。</span><span class="sxs-lookup"><span data-stu-id="fed3b-154">Handles the order and flow for data transfers between a client and server.</span></span>
    
<span data-ttu-id="fed3b-155">[[MS OXCMAIL]](http://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="fed3b-155">[[MS-OXCMAIL]](http://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="fed3b-156">从 Internet 标准电子邮件约定转换为消息对象。</span><span class="sxs-lookup"><span data-stu-id="fed3b-156">Converts from Internet standard email conventions to message objects.</span></span>
    
<span data-ttu-id="fed3b-157">[[MS OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="fed3b-157">[[MS-OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="fed3b-158">处理邮件和附件的对象。</span><span class="sxs-lookup"><span data-stu-id="fed3b-158">Handles message and attachment objects.</span></span>
    
<span data-ttu-id="fed3b-159">[[MS OXOAB]](http://msdn.microsoft.com/library/b4750386-66ec-4e69-abb6-208dd131c7de%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="fed3b-159">[[MS-OXOAB]](http://msdn.microsoft.com/library/b4750386-66ec-4e69-abb6-208dd131c7de%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="fed3b-160">指定本地地址簿对象缓存的脱机通讯簿 (OAB) 文件格式。</span><span class="sxs-lookup"><span data-stu-id="fed3b-160">Specifies the offline address book (OAB) file formats for the local address book objects cache.</span></span>
    
<span data-ttu-id="fed3b-161">[[MS OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="fed3b-161">[[MS-OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="fed3b-162">指定的属性和操作所允许的电子邮件消息对象。</span><span class="sxs-lookup"><span data-stu-id="fed3b-162">Specifies the properties and operations that are permissible for email message objects.</span></span>
    
<span data-ttu-id="fed3b-163">[[MS OXOSRCH]](http://msdn.microsoft.com/library/c72e49b8-78c7-4483-ad65-e46e9133673b%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="fed3b-163">[[MS-OXOSRCH]](http://msdn.microsoft.com/library/c72e49b8-78c7-4483-ad65-e46e9133673b%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="fed3b-164">指定的属性和操作的搜索文件夹列表配置的操作。</span><span class="sxs-lookup"><span data-stu-id="fed3b-164">Specifies the properties and operations for manipulating a search folder list configuration.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="fed3b-165">头文件</span><span class="sxs-lookup"><span data-stu-id="fed3b-165">Header files</span></span>

<span data-ttu-id="fed3b-166">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="fed3b-166">Mapidefs.h</span></span>
  
> <span data-ttu-id="fed3b-167">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="fed3b-167">Provides data type definitions.</span></span>
    
<span data-ttu-id="fed3b-168">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="fed3b-168">Mapitags.h</span></span>
  
> <span data-ttu-id="fed3b-169">包含列为相关属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="fed3b-169">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="fed3b-170">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fed3b-170">See also</span></span>



[<span data-ttu-id="fed3b-171">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="fed3b-171">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="fed3b-172">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="fed3b-172">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="fed3b-173">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="fed3b-173">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="fed3b-174">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="fed3b-174">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

