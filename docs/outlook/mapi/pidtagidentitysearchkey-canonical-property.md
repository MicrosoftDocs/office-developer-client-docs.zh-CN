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
ms.openlocfilehash: 5f5f5eaa41d6256bed69b2cd9a91208181d5bda1
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32346632"
---
# <a name="pidtagidentitysearchkey-canonical-property"></a><span data-ttu-id="c42f2-103">PidTagIdentitySearchKey 规范属性</span><span class="sxs-lookup"><span data-stu-id="c42f2-103">PidTagIdentitySearchKey Canonical Property</span></span>

  
  
<span data-ttu-id="c42f2-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="c42f2-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="c42f2-105">包含在邮件系统中定义的服务提供商标识的搜索关键字。</span><span class="sxs-lookup"><span data-stu-id="c42f2-105">Contains the search key for a service provider's identity as defined within a messaging system.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="c42f2-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="c42f2-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="c42f2-107">PR_IDENTITY_SEARCH_KEY</span><span class="sxs-lookup"><span data-stu-id="c42f2-107">PR_IDENTITY_SEARCH_KEY</span></span>  <br/> |
|<span data-ttu-id="c42f2-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="c42f2-108">Identifier:</span></span>  <br/> |<span data-ttu-id="c42f2-109">0x3E05</span><span class="sxs-lookup"><span data-stu-id="c42f2-109">0x3E05</span></span>  <br/> |
|<span data-ttu-id="c42f2-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="c42f2-110">Data type:</span></span>  <br/> |<span data-ttu-id="c42f2-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="c42f2-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="c42f2-112">区域：</span><span class="sxs-lookup"><span data-stu-id="c42f2-112">Area:</span></span>  <br/> |<span data-ttu-id="c42f2-113">MAPI 状态</span><span class="sxs-lookup"><span data-stu-id="c42f2-113">MAPI status</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="c42f2-114">注解</span><span class="sxs-lookup"><span data-stu-id="c42f2-114">Remarks</span></span>

<span data-ttu-id="c42f2-115">此属性不显示为任何对象的属性, 而只是作为状态表中的一列。</span><span class="sxs-lookup"><span data-stu-id="c42f2-115">This property does not appear as a property on any object but only as a column in a status table.</span></span> <span data-ttu-id="c42f2-116">它是公开状态表行的服务提供程序的标识的一部分。</span><span class="sxs-lookup"><span data-stu-id="c42f2-116">It is part of the identity of the service provider exposing the status table row.</span></span> <span data-ttu-id="c42f2-117">提供程序的标识通常是指它在服务器上的帐户, 但可以引用在邮件系统中提供程序定义的任何表示形式。</span><span class="sxs-lookup"><span data-stu-id="c42f2-117">The provider's identity typically refers to its account on the server, but can refer to any representation the provider defines within the messaging system.</span></span> 
  
<span data-ttu-id="c42f2-118">提供任何标识属性的服务提供商应提供所有这些标识属性。</span><span class="sxs-lookup"><span data-stu-id="c42f2-118">A service provider furnishing any of the identity properties should furnish all of them.</span></span> <span data-ttu-id="c42f2-119">属于同一邮件服务的提供程序应公开 identity 属性的相同值。</span><span class="sxs-lookup"><span data-stu-id="c42f2-119">Providers that belong to the same message service should expose the same values for the identity properties.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="c42f2-120">相关资源</span><span class="sxs-lookup"><span data-stu-id="c42f2-120">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="c42f2-121">头文件</span><span class="sxs-lookup"><span data-stu-id="c42f2-121">Header files</span></span>

<span data-ttu-id="c42f2-122">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="c42f2-122">Mapidefs.h</span></span>
  
> <span data-ttu-id="c42f2-123">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="c42f2-123">Provides data type definitions.</span></span>
    
<span data-ttu-id="c42f2-124">Mapitags</span><span class="sxs-lookup"><span data-stu-id="c42f2-124">Mapitags.h</span></span>
  
> <span data-ttu-id="c42f2-125">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="c42f2-125">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="c42f2-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c42f2-126">See also</span></span>



[<span data-ttu-id="c42f2-127">IMAPISession::QueryIdentity</span><span class="sxs-lookup"><span data-stu-id="c42f2-127">IMAPISession::QueryIdentity</span></span>](imapisession-queryidentity.md)


[<span data-ttu-id="c42f2-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="c42f2-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="c42f2-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="c42f2-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="c42f2-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="c42f2-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="c42f2-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="c42f2-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

