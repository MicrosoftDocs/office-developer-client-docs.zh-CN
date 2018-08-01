---
title: PidTagIdentitySearchKey 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagIdentitySearchKey
api_type:
- HeaderDef
ms.assetid: 5fe55ba7-4ecd-4a43-ab5b-2ef595c2cdd9
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 28c269db15d0c0a81950a61ee9e6629ad067b789
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777695"
---
# <a name="pidtagidentitysearchkey-canonical-property"></a><span data-ttu-id="69397-103">PidTagIdentitySearchKey 规范属性</span><span class="sxs-lookup"><span data-stu-id="69397-103">PidTagIdentitySearchKey Canonical Property</span></span>

  
  
<span data-ttu-id="69397-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="69397-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="69397-105">包含服务提供商的标识在邮件系统中定义的搜索键。</span><span class="sxs-lookup"><span data-stu-id="69397-105">Contains the search key for a service provider's identity as defined within a messaging system.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="69397-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="69397-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="69397-107">PR_IDENTITY_SEARCH_KEY</span><span class="sxs-lookup"><span data-stu-id="69397-107">PR_IDENTITY_SEARCH_KEY</span></span>  <br/> |
|<span data-ttu-id="69397-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="69397-108">Identifier:</span></span>  <br/> |<span data-ttu-id="69397-109">0x3E05</span><span class="sxs-lookup"><span data-stu-id="69397-109">0x3E05</span></span>  <br/> |
|<span data-ttu-id="69397-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="69397-110">Data type:</span></span>  <br/> |<span data-ttu-id="69397-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="69397-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="69397-112">区域：</span><span class="sxs-lookup"><span data-stu-id="69397-112">Area:</span></span>  <br/> |<span data-ttu-id="69397-113">MAPI 状态</span><span class="sxs-lookup"><span data-stu-id="69397-113">MAPI status</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="69397-114">说明</span><span class="sxs-lookup"><span data-stu-id="69397-114">Remarks</span></span>

<span data-ttu-id="69397-115">此属性不显示任何对象的属性但只能作为状态表中的列。</span><span class="sxs-lookup"><span data-stu-id="69397-115">This property does not appear as a property on any object but only as a column in a status table.</span></span> <span data-ttu-id="69397-116">它是标识的公开状态表格行的服务提供程序的一部分。</span><span class="sxs-lookup"><span data-stu-id="69397-116">It is part of the identity of the service provider exposing the status table row.</span></span> <span data-ttu-id="69397-117">提供程序的标识通常是指其帐户的服务器上，但可以参考消息系统中定义的提供程序的任何表示。</span><span class="sxs-lookup"><span data-stu-id="69397-117">The provider's identity typically refers to its account on the server, but can refer to any representation the provider defines within the messaging system.</span></span> 
  
<span data-ttu-id="69397-118">Furnishing 任一标识属性的服务提供程序应提供所有这些。</span><span class="sxs-lookup"><span data-stu-id="69397-118">A service provider furnishing any of the identity properties should furnish all of them.</span></span> <span data-ttu-id="69397-119">属于同一消息服务的提供程序应公开的 identity 属性相同的值。</span><span class="sxs-lookup"><span data-stu-id="69397-119">Providers that belong to the same message service should expose the same values for the identity properties.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="69397-120">相关资源</span><span class="sxs-lookup"><span data-stu-id="69397-120">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="69397-121">头文件</span><span class="sxs-lookup"><span data-stu-id="69397-121">Header files</span></span>

<span data-ttu-id="69397-122">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="69397-122">Mapidefs.h</span></span>
  
> <span data-ttu-id="69397-123">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="69397-123">Provides data type definitions.</span></span>
    
<span data-ttu-id="69397-124">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="69397-124">Mapitags.h</span></span>
  
> <span data-ttu-id="69397-125">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="69397-125">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="69397-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="69397-126">See also</span></span>



[<span data-ttu-id="69397-127">IMAPISession::QueryIdentity</span><span class="sxs-lookup"><span data-stu-id="69397-127">IMAPISession::QueryIdentity</span></span>](imapisession-queryidentity.md)


[<span data-ttu-id="69397-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="69397-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="69397-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="69397-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="69397-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="69397-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="69397-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="69397-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

