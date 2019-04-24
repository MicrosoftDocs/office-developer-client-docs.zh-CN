---
title: PidTagRpcOverHttpProxyAuthScheme 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 6da78f1a-6423-460c-b3a9-fd6441df9cef
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: ea4b90bf1190fd71701f82d43aaee384c7987ed0
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32331309"
---
# <a name="pidtagrpcoverhttpproxyauthscheme-canonical-property"></a><span data-ttu-id="09987-103">PidTagRpcOverHttpProxyAuthScheme 规范属性</span><span class="sxs-lookup"><span data-stu-id="09987-103">PidTagRpcOverHttpProxyAuthScheme Canonical Property</span></span>

  
  
<span data-ttu-id="09987-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="09987-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="09987-105">表示要用于此配置文件的身份验证协议。</span><span class="sxs-lookup"><span data-stu-id="09987-105">Represents the authentication protocol to be used for this profile.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="09987-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="09987-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="09987-107">PR_ROH_PROXY_AUTH_SCHEME</span><span class="sxs-lookup"><span data-stu-id="09987-107">PR_ROH_PROXY_AUTH_SCHEME</span></span>  <br/> |
|<span data-ttu-id="09987-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="09987-108">Identifier:</span></span>  <br/> |<span data-ttu-id="09987-109">0x6627</span><span class="sxs-lookup"><span data-stu-id="09987-109">0x6627</span></span>  <br/> |
|<span data-ttu-id="09987-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="09987-110">Data type:</span></span>  <br/> |<span data-ttu-id="09987-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="09987-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="09987-112">区域：</span><span class="sxs-lookup"><span data-stu-id="09987-112">Area:</span></span>  <br/> |<span data-ttu-id="09987-113">其他</span><span class="sxs-lookup"><span data-stu-id="09987-113">Miscellaneous</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="09987-114">注解</span><span class="sxs-lookup"><span data-stu-id="09987-114">Remarks</span></span>

<span data-ttu-id="09987-115">此属性可以设置为基本身份验证或 NT LAN Manager (NTLM) 身份验证。</span><span class="sxs-lookup"><span data-stu-id="09987-115">This property can be set for either basic authentication or NT LAN Manager (NTLM) authentication.</span></span> <span data-ttu-id="09987-116">此属性的可能值如下所示。</span><span class="sxs-lookup"><span data-stu-id="09987-116">The possible values for this property are as follow.</span></span>
  
|<span data-ttu-id="09987-117">**Name**</span><span class="sxs-lookup"><span data-stu-id="09987-117">**Name**</span></span>|<span data-ttu-id="09987-118">**Value**</span><span class="sxs-lookup"><span data-stu-id="09987-118">**Value**</span></span>|<span data-ttu-id="09987-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="09987-119">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="09987-120">**ROHAUTH_BASIC**</span><span class="sxs-lookup"><span data-stu-id="09987-120">**ROHAUTH_BASIC**</span></span> <br/> |<span data-ttu-id="09987-121">0x1</span><span class="sxs-lookup"><span data-stu-id="09987-121">0x1</span></span>  <br/> |<span data-ttu-id="09987-122">基本身份验证</span><span class="sxs-lookup"><span data-stu-id="09987-122">Basic authentication</span></span>  <br/> |
|<span data-ttu-id="09987-123">**ROHAUTH_NTLM**</span><span class="sxs-lookup"><span data-stu-id="09987-123">**ROHAUTH_NTLM**</span></span> <br/> |<span data-ttu-id="09987-124">0x2</span><span class="sxs-lookup"><span data-stu-id="09987-124">0x2</span></span>  <br/> |<span data-ttu-id="09987-125">NTLM 身份验证</span><span class="sxs-lookup"><span data-stu-id="09987-125">NTLM authentication</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="09987-126">相关资源</span><span class="sxs-lookup"><span data-stu-id="09987-126">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="09987-127">协议规范</span><span class="sxs-lookup"><span data-stu-id="09987-127">Protocol specifications</span></span>

<span data-ttu-id="09987-128">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="09987-128">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="09987-129">提供对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="09987-129">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="09987-130">[[毫秒-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="09987-130">[[MS-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="09987-131">定义在远程操作中使用的基本数据结构。</span><span class="sxs-lookup"><span data-stu-id="09987-131">Defines the basic data structures that are used in remote operations.</span></span>
    
<span data-ttu-id="09987-132">[[毫秒-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="09987-132">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="09987-133">指定允许用于电子邮件对象的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="09987-133">Specifies the properties and operations that are permissible for email message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="09987-134">头文件</span><span class="sxs-lookup"><span data-stu-id="09987-134">Header files</span></span>

<span data-ttu-id="09987-135">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="09987-135">Mapidefs.h</span></span>
  
> <span data-ttu-id="09987-136">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="09987-136">Provides data type definitions.</span></span>
    
<span data-ttu-id="09987-137">Mapitags</span><span class="sxs-lookup"><span data-stu-id="09987-137">Mapitags.h</span></span>
  
> <span data-ttu-id="09987-138">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="09987-138">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="09987-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="09987-139">See also</span></span>



[<span data-ttu-id="09987-140">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="09987-140">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="09987-141">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="09987-141">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="09987-142">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="09987-142">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="09987-143">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="09987-143">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

