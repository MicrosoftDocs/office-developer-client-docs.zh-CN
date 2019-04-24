---
title: PidTagIdentityDisplay 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagIdentityDisplay
api_type:
- HeaderDef
ms.assetid: ad9756c1-c1f9-4ab3-a58a-31e574dd9530
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: d6e189f78dec2fc92f1804be93e7885b61734b03
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32327949"
---
# <a name="pidtagidentitydisplay-canonical-property"></a><span data-ttu-id="a05ab-103">PidTagIdentityDisplay 规范属性</span><span class="sxs-lookup"><span data-stu-id="a05ab-103">PidTagIdentityDisplay Canonical Property</span></span>

  
  
<span data-ttu-id="a05ab-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a05ab-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="a05ab-105">包含在邮件系统中定义的服务提供商标识的显示名称。</span><span class="sxs-lookup"><span data-stu-id="a05ab-105">Contains the display name for a service provider's identity as defined within a messaging system.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="a05ab-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="a05ab-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="a05ab-107">PR_IDENTITY_DISPLAY、PR_IDENTITY_DISPLAY_A、PR_IDENTITY_DISPLAY_W</span><span class="sxs-lookup"><span data-stu-id="a05ab-107">PR_IDENTITY_DISPLAY, PR_IDENTITY_DISPLAY_A, PR_IDENTITY_DISPLAY_W</span></span>  <br/> |
|<span data-ttu-id="a05ab-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="a05ab-108">Identifier:</span></span>  <br/> |<span data-ttu-id="a05ab-109">0x3E00</span><span class="sxs-lookup"><span data-stu-id="a05ab-109">0x3E00</span></span>  <br/> |
|<span data-ttu-id="a05ab-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="a05ab-110">Data type:</span></span>  <br/> |<span data-ttu-id="a05ab-111">PT_STRING8、PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="a05ab-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="a05ab-112">区域：</span><span class="sxs-lookup"><span data-stu-id="a05ab-112">Area:</span></span>  <br/> |<span data-ttu-id="a05ab-113">MAPI 状态</span><span class="sxs-lookup"><span data-stu-id="a05ab-113">MAPI status</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="a05ab-114">注解</span><span class="sxs-lookup"><span data-stu-id="a05ab-114">Remarks</span></span>

<span data-ttu-id="a05ab-115">这些属性不显示为任何对象的属性, 而只是作为状态表中的一列。</span><span class="sxs-lookup"><span data-stu-id="a05ab-115">These properties do not appear as properties on any object but only as a column in a status table.</span></span> <span data-ttu-id="a05ab-116">它是公开状态表行的服务提供程序的标识的一部分。</span><span class="sxs-lookup"><span data-stu-id="a05ab-116">It is part of the identity of the service provider exposing the status table row.</span></span> <span data-ttu-id="a05ab-117">提供程序的标识通常是指它在服务器上的帐户, 但可以引用在邮件系统中提供程序定义的任何表示形式。</span><span class="sxs-lookup"><span data-stu-id="a05ab-117">The provider's identity typically refers to its account on the server, but can refer to any representation the provider defines within the messaging system.</span></span> 
  
<span data-ttu-id="a05ab-118">提供任何标识属性的服务提供商应提供所有这些标识属性。</span><span class="sxs-lookup"><span data-stu-id="a05ab-118">A service provider furnishing any of the identity properties should furnish all of them.</span></span> <span data-ttu-id="a05ab-119">属于同一邮件服务的提供程序应公开 identity 属性的相同值。</span><span class="sxs-lookup"><span data-stu-id="a05ab-119">Providers that belong to the same message service should expose the same values for the identity properties.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="a05ab-120">相关资源</span><span class="sxs-lookup"><span data-stu-id="a05ab-120">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="a05ab-121">头文件</span><span class="sxs-lookup"><span data-stu-id="a05ab-121">Header files</span></span>

<span data-ttu-id="a05ab-122">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="a05ab-122">Mapidefs.h</span></span>
  
> <span data-ttu-id="a05ab-123">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="a05ab-123">Provides data type definitions.</span></span>
    
<span data-ttu-id="a05ab-124">Mapitags</span><span class="sxs-lookup"><span data-stu-id="a05ab-124">Mapitags.h</span></span>
  
> <span data-ttu-id="a05ab-125">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="a05ab-125">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="a05ab-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a05ab-126">See also</span></span>



[<span data-ttu-id="a05ab-127">IMAPISession::QueryIdentity</span><span class="sxs-lookup"><span data-stu-id="a05ab-127">IMAPISession::QueryIdentity</span></span>](imapisession-queryidentity.md)


[<span data-ttu-id="a05ab-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="a05ab-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="a05ab-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="a05ab-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="a05ab-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="a05ab-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="a05ab-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="a05ab-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

