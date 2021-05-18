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
ms.openlocfilehash: b433db7cb157afbf8c3b506f2ed95b04b7b88564
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32329223"
---
# <a name="pidtagobjecttype-canonical-property"></a><span data-ttu-id="38471-103">PidTagObjectType 规范属性</span><span class="sxs-lookup"><span data-stu-id="38471-103">PidTagObjectType Canonical Property</span></span>

  
  
<span data-ttu-id="38471-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="38471-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="38471-105">包含对象的类型。</span><span class="sxs-lookup"><span data-stu-id="38471-105">Contains the type of an object.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="38471-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="38471-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="38471-107">PR_OBJECT_TYPE</span><span class="sxs-lookup"><span data-stu-id="38471-107">PR_OBJECT_TYPE</span></span>  <br/> |
|<span data-ttu-id="38471-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="38471-108">Identifier:</span></span>  <br/> |<span data-ttu-id="38471-109">0x0FFE</span><span class="sxs-lookup"><span data-stu-id="38471-109">0x0FFE</span></span>  <br/> |
|<span data-ttu-id="38471-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="38471-110">Data type:</span></span>  <br/> |<span data-ttu-id="38471-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="38471-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="38471-112">区域：</span><span class="sxs-lookup"><span data-stu-id="38471-112">Area:</span></span>  <br/> |<span data-ttu-id="38471-113">常见</span><span class="sxs-lookup"><span data-stu-id="38471-113">Common</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="38471-114">备注</span><span class="sxs-lookup"><span data-stu-id="38471-114">Remarks</span></span>

<span data-ttu-id="38471-115">此属性对象类型的对象对应于可通过 **OpenEntry** 接口访问的对象的主接口。</span><span class="sxs-lookup"><span data-stu-id="38471-115">The object type contained in this property corresponds to the primary interface available for an object accessible through the **OpenEntry** interface.</span></span> <span data-ttu-id="38471-116">它通常通过咨询相应的 **OpenEntry** 方法返回 _的 lpulObjType_ 参数获得。</span><span class="sxs-lookup"><span data-stu-id="38471-116">It is usually obtained by consulting the  _lpulObjType_ parameter returned by the appropriate **OpenEntry** method.</span></span> <span data-ttu-id="38471-117">以其他方式获取接口时，调用 [IMAPIProp：：GetProps](imapiprop-getprops.md) 以获取此属性的值。</span><span class="sxs-lookup"><span data-stu-id="38471-117">When the interface is obtained in other ways, call [IMAPIProp::GetProps](imapiprop-getprops.md) to obtain the value for this property.</span></span> 
  
<span data-ttu-id="38471-118">此属性可以正好具有下列值之一：</span><span class="sxs-lookup"><span data-stu-id="38471-118">This property can have exactly one of the following values:</span></span>
  
<span data-ttu-id="38471-119">MAPI_ABCONT</span><span class="sxs-lookup"><span data-stu-id="38471-119">MAPI_ABCONT</span></span> 
  
> <span data-ttu-id="38471-120">通讯簿容器对象</span><span class="sxs-lookup"><span data-stu-id="38471-120">Address book container object</span></span> 
    
<span data-ttu-id="38471-121">MAPI_ADDRBOOK</span><span class="sxs-lookup"><span data-stu-id="38471-121">MAPI_ADDRBOOK</span></span> 
  
> <span data-ttu-id="38471-122">通讯簿对象</span><span class="sxs-lookup"><span data-stu-id="38471-122">Address book object</span></span> 
    
<span data-ttu-id="38471-123">MAPI_ATTACH</span><span class="sxs-lookup"><span data-stu-id="38471-123">MAPI_ATTACH</span></span> 
  
> <span data-ttu-id="38471-124">邮件附件对象</span><span class="sxs-lookup"><span data-stu-id="38471-124">Message attachment object</span></span> 
    
<span data-ttu-id="38471-125">MAPI_DISTLIST</span><span class="sxs-lookup"><span data-stu-id="38471-125">MAPI_DISTLIST</span></span> 
  
> <span data-ttu-id="38471-126">通讯组列表对象</span><span class="sxs-lookup"><span data-stu-id="38471-126">Distribution list object</span></span> 
    
<span data-ttu-id="38471-127">MAPI_FOLDER</span><span class="sxs-lookup"><span data-stu-id="38471-127">MAPI_FOLDER</span></span> 
  
> <span data-ttu-id="38471-128">Folder 对象</span><span class="sxs-lookup"><span data-stu-id="38471-128">Folder object</span></span> 
    
<span data-ttu-id="38471-129">MAPI_FORMINFO</span><span class="sxs-lookup"><span data-stu-id="38471-129">MAPI_FORMINFO</span></span> 
  
> <span data-ttu-id="38471-130">Form 对象</span><span class="sxs-lookup"><span data-stu-id="38471-130">Form object</span></span> 
    
<span data-ttu-id="38471-131">MAPI_MAILUSER</span><span class="sxs-lookup"><span data-stu-id="38471-131">MAPI_MAILUSER</span></span> 
  
> <span data-ttu-id="38471-132">消息传递用户对象</span><span class="sxs-lookup"><span data-stu-id="38471-132">Messaging user object</span></span> 
    
<span data-ttu-id="38471-133">MAPI_MESSAGE</span><span class="sxs-lookup"><span data-stu-id="38471-133">MAPI_MESSAGE</span></span> 
  
> <span data-ttu-id="38471-134">Message 对象</span><span class="sxs-lookup"><span data-stu-id="38471-134">Message object</span></span> 
    
<span data-ttu-id="38471-135">MAPI_PROFSECT</span><span class="sxs-lookup"><span data-stu-id="38471-135">MAPI_PROFSECT</span></span> 
  
> <span data-ttu-id="38471-136">配置文件节对象</span><span class="sxs-lookup"><span data-stu-id="38471-136">Profile section object</span></span> 
    
<span data-ttu-id="38471-137">MAPI_SESSION</span><span class="sxs-lookup"><span data-stu-id="38471-137">MAPI_SESSION</span></span> 
  
> <span data-ttu-id="38471-138">Session 对象</span><span class="sxs-lookup"><span data-stu-id="38471-138">Session object</span></span> 
    
<span data-ttu-id="38471-139">MAPI_STATUS</span><span class="sxs-lookup"><span data-stu-id="38471-139">MAPI_STATUS</span></span> 
  
> <span data-ttu-id="38471-140">Status 对象</span><span class="sxs-lookup"><span data-stu-id="38471-140">Status object</span></span> 
    
<span data-ttu-id="38471-141">MAPI_STORE</span><span class="sxs-lookup"><span data-stu-id="38471-141">MAPI_STORE</span></span> 
  
> <span data-ttu-id="38471-142">邮件存储对象</span><span class="sxs-lookup"><span data-stu-id="38471-142">Message store object</span></span>
    
## <a name="related-resources"></a><span data-ttu-id="38471-143">相关资源</span><span class="sxs-lookup"><span data-stu-id="38471-143">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="38471-144">协议规范</span><span class="sxs-lookup"><span data-stu-id="38471-144">Protocol specifications</span></span>

<span data-ttu-id="38471-145">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="38471-145">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="38471-146">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="38471-146">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="38471-147">[[MS-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="38471-147">[[MS-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="38471-148">指定用户、联系人、组和资源的列表的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="38471-148">Specifies the properties and operations for lists of users, contacts, groups, and resources.</span></span>
    
<span data-ttu-id="38471-149">[[MS-NSPI]](https://msdn.microsoft.com/library/6dd0a3ea-b4d4-4a73-a857-add03a89a543%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="38471-149">[[MS-NSPI]](https://msdn.microsoft.com/library/6dd0a3ea-b4d4-4a73-a857-add03a89a543%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="38471-150">处理客户端与 NSPI 服务器的名称服务提供程序 (的通信) 。</span><span class="sxs-lookup"><span data-stu-id="38471-150">Handles a client's communications with a Name Service Provider Interface (NSPI) server.</span></span>
    
<span data-ttu-id="38471-151">[[MS-OXCFOLD]](https://msdn.microsoft.com/library/c0f31b95-c07f-486c-98d9-535ed9705fbf%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="38471-151">[[MS-OXCFOLD]](https://msdn.microsoft.com/library/c0f31b95-c07f-486c-98d9-535ed9705fbf%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="38471-152">处理文件夹操作。</span><span class="sxs-lookup"><span data-stu-id="38471-152">Handles folder operations.</span></span>
    
<span data-ttu-id="38471-153">[[MS-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="38471-153">[[MS-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="38471-154">处理客户端和服务器之间数据传输的顺序和流。</span><span class="sxs-lookup"><span data-stu-id="38471-154">Handles the order and flow for data transfers between a client and server.</span></span>
    
<span data-ttu-id="38471-155">[[MS-OXCMAIL]](https://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="38471-155">[[MS-OXCMAIL]](https://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="38471-156">从 Internet 标准电子邮件约定转换为邮件对象。</span><span class="sxs-lookup"><span data-stu-id="38471-156">Converts from Internet standard email conventions to message objects.</span></span>
    
<span data-ttu-id="38471-157">[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="38471-157">[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="38471-158">处理邮件和附件对象。</span><span class="sxs-lookup"><span data-stu-id="38471-158">Handles message and attachment objects.</span></span>
    
<span data-ttu-id="38471-159">[[MS-OXOAB]](https://msdn.microsoft.com/library/b4750386-66ec-4e69-abb6-208dd131c7de%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="38471-159">[[MS-OXOAB]](https://msdn.microsoft.com/library/b4750386-66ec-4e69-abb6-208dd131c7de%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="38471-160">指定脱机通讯簿 (OAB) 本地通讯簿对象缓存的文件格式。</span><span class="sxs-lookup"><span data-stu-id="38471-160">Specifies the offline address book (OAB) file formats for the local address book objects cache.</span></span>
    
<span data-ttu-id="38471-161">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="38471-161">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="38471-162">指定电子邮件对象允许的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="38471-162">Specifies the properties and operations that are permissible for email message objects.</span></span>
    
<span data-ttu-id="38471-163">[[MS-OXOSRCH]](https://msdn.microsoft.com/library/c72e49b8-78c7-4483-ad65-e46e9133673b%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="38471-163">[[MS-OXOSRCH]](https://msdn.microsoft.com/library/c72e49b8-78c7-4483-ad65-e46e9133673b%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="38471-164">指定用于操作搜索文件夹列表配置的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="38471-164">Specifies the properties and operations for manipulating a search folder list configuration.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="38471-165">头文件</span><span class="sxs-lookup"><span data-stu-id="38471-165">Header files</span></span>

<span data-ttu-id="38471-166">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="38471-166">Mapidefs.h</span></span>
  
> <span data-ttu-id="38471-167">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="38471-167">Provides data type definitions.</span></span>
    
<span data-ttu-id="38471-168">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="38471-168">Mapitags.h</span></span>
  
> <span data-ttu-id="38471-169">包含作为关联属性列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="38471-169">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="38471-170">另请参阅</span><span class="sxs-lookup"><span data-stu-id="38471-170">See also</span></span>



[<span data-ttu-id="38471-171">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="38471-171">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="38471-172">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="38471-172">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="38471-173">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="38471-173">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="38471-174">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="38471-174">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

