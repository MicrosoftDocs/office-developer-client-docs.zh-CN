---
title: PidTagRpcOverHttpProxyAuthScheme 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 6da78f1a-6423-460c-b3a9-fd6441df9cef
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: b8c68c2cd34ba037dc725a7d15575159466d8123
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778233"
---
# <a name="pidtagrpcoverhttpproxyauthscheme-canonical-property"></a><span data-ttu-id="e7da9-103">PidTagRpcOverHttpProxyAuthScheme 规范属性</span><span class="sxs-lookup"><span data-stu-id="e7da9-103">PidTagRpcOverHttpProxyAuthScheme Canonical Property</span></span>

  
  
<span data-ttu-id="e7da9-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="e7da9-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="e7da9-105">代表要用于此配置文件的身份验证协议。</span><span class="sxs-lookup"><span data-stu-id="e7da9-105">Represents the authentication protocol to be used for this profile.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="e7da9-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="e7da9-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="e7da9-107">PR_ROH_PROXY_AUTH_SCHEME</span><span class="sxs-lookup"><span data-stu-id="e7da9-107">PR_ROH_PROXY_AUTH_SCHEME</span></span>  <br/> |
|<span data-ttu-id="e7da9-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="e7da9-108">Identifier:</span></span>  <br/> |<span data-ttu-id="e7da9-109">0x6627</span><span class="sxs-lookup"><span data-stu-id="e7da9-109">0x6627</span></span>  <br/> |
|<span data-ttu-id="e7da9-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="e7da9-110">Data type:</span></span>  <br/> |<span data-ttu-id="e7da9-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="e7da9-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="e7da9-112">区域：</span><span class="sxs-lookup"><span data-stu-id="e7da9-112">Area:</span></span>  <br/> |<span data-ttu-id="e7da9-113">其他</span><span class="sxs-lookup"><span data-stu-id="e7da9-113">Miscellaneous</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="e7da9-114">备注</span><span class="sxs-lookup"><span data-stu-id="e7da9-114">Remarks</span></span>

<span data-ttu-id="e7da9-115">此属性可为基本身份验证或 NT LAN Manager (NTLM) 身份验证设置。</span><span class="sxs-lookup"><span data-stu-id="e7da9-115">This property can be set for either basic authentication or NT LAN Manager (NTLM) authentication.</span></span> <span data-ttu-id="e7da9-116">此属性的可能值如下所示。</span><span class="sxs-lookup"><span data-stu-id="e7da9-116">The possible values for this property are as follow.</span></span>
  
|<span data-ttu-id="e7da9-117">**名称**</span><span class="sxs-lookup"><span data-stu-id="e7da9-117">**Name**</span></span>|<span data-ttu-id="e7da9-118">**值**</span><span class="sxs-lookup"><span data-stu-id="e7da9-118">**Value**</span></span>|<span data-ttu-id="e7da9-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="e7da9-119">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e7da9-120">**ROHAUTH_BASIC**</span><span class="sxs-lookup"><span data-stu-id="e7da9-120">**ROHAUTH_BASIC**</span></span> <br/> |<span data-ttu-id="e7da9-121">0x1</span><span class="sxs-lookup"><span data-stu-id="e7da9-121">0x1</span></span>  <br/> |<span data-ttu-id="e7da9-122">基本身份验证</span><span class="sxs-lookup"><span data-stu-id="e7da9-122">Basic authentication</span></span>  <br/> |
|<span data-ttu-id="e7da9-123">**ROHAUTH_NTLM**</span><span class="sxs-lookup"><span data-stu-id="e7da9-123">**ROHAUTH_NTLM**</span></span> <br/> |<span data-ttu-id="e7da9-124">0x2</span><span class="sxs-lookup"><span data-stu-id="e7da9-124">0x2</span></span>  <br/> |<span data-ttu-id="e7da9-125">NTLM 身份验证</span><span class="sxs-lookup"><span data-stu-id="e7da9-125">NTLM authentication</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="e7da9-126">相关资源</span><span class="sxs-lookup"><span data-stu-id="e7da9-126">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="e7da9-127">协议规范</span><span class="sxs-lookup"><span data-stu-id="e7da9-127">Protocol specifications</span></span>

<span data-ttu-id="e7da9-128">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="e7da9-128">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="e7da9-129">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="e7da9-129">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="e7da9-130">[[MS OXCFXICS]](http://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="e7da9-130">[[MS-OXCFXICS]](http://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="e7da9-131">定义所使用的基本的数据结构中远程操作。</span><span class="sxs-lookup"><span data-stu-id="e7da9-131">Defines the basic data structures that are used in remote operations.</span></span>
    
<span data-ttu-id="e7da9-132">[[MS OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="e7da9-132">[[MS-OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="e7da9-133">指定的属性和操作所允许的电子邮件消息对象。</span><span class="sxs-lookup"><span data-stu-id="e7da9-133">Specifies the properties and operations that are permissible for email message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="e7da9-134">头文件</span><span class="sxs-lookup"><span data-stu-id="e7da9-134">Header files</span></span>

<span data-ttu-id="e7da9-135">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="e7da9-135">Mapidefs.h</span></span>
  
> <span data-ttu-id="e7da9-136">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="e7da9-136">Provides data type definitions.</span></span>
    
<span data-ttu-id="e7da9-137">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="e7da9-137">Mapitags.h</span></span>
  
> <span data-ttu-id="e7da9-138">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="e7da9-138">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="e7da9-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e7da9-139">See also</span></span>



[<span data-ttu-id="e7da9-140">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="e7da9-140">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="e7da9-141">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="e7da9-141">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="e7da9-142">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="e7da9-142">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="e7da9-143">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="e7da9-143">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

