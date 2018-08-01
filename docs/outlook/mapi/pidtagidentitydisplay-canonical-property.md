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
ms.openlocfilehash: b88fc54f1db26277d8a8d5e54fcff0ae164b0eac
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777715"
---
# <a name="pidtagidentitydisplay-canonical-property"></a><span data-ttu-id="d6915-103">PidTagIdentityDisplay 规范属性</span><span class="sxs-lookup"><span data-stu-id="d6915-103">PidTagIdentityDisplay Canonical Property</span></span>

  
  
<span data-ttu-id="d6915-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="d6915-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="d6915-105">包含服务提供商的标识在邮件系统中定义的显示名称。</span><span class="sxs-lookup"><span data-stu-id="d6915-105">Contains the display name for a service provider's identity as defined within a messaging system.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="d6915-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="d6915-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="d6915-107">PR_IDENTITY_DISPLAY，PR_IDENTITY_DISPLAY_A，PR_IDENTITY_DISPLAY_W</span><span class="sxs-lookup"><span data-stu-id="d6915-107">PR_IDENTITY_DISPLAY, PR_IDENTITY_DISPLAY_A, PR_IDENTITY_DISPLAY_W</span></span>  <br/> |
|<span data-ttu-id="d6915-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="d6915-108">Identifier:</span></span>  <br/> |<span data-ttu-id="d6915-109">0x3E00</span><span class="sxs-lookup"><span data-stu-id="d6915-109">0x3E00</span></span>  <br/> |
|<span data-ttu-id="d6915-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="d6915-110">Data type:</span></span>  <br/> |<span data-ttu-id="d6915-111">PT_STRING8 PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="d6915-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="d6915-112">区域：</span><span class="sxs-lookup"><span data-stu-id="d6915-112">Area:</span></span>  <br/> |<span data-ttu-id="d6915-113">MAPI 状态</span><span class="sxs-lookup"><span data-stu-id="d6915-113">MAPI status</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="d6915-114">说明</span><span class="sxs-lookup"><span data-stu-id="d6915-114">Remarks</span></span>

<span data-ttu-id="d6915-115">作为对任何对象的属性，但只能作为状态表中的列不显示这些属性。</span><span class="sxs-lookup"><span data-stu-id="d6915-115">These properties do not appear as properties on any object but only as a column in a status table.</span></span> <span data-ttu-id="d6915-116">它是标识的公开状态表格行的服务提供程序的一部分。</span><span class="sxs-lookup"><span data-stu-id="d6915-116">It is part of the identity of the service provider exposing the status table row.</span></span> <span data-ttu-id="d6915-117">提供程序的标识通常是指其帐户的服务器上，但可以参考消息系统中定义的提供程序的任何表示。</span><span class="sxs-lookup"><span data-stu-id="d6915-117">The provider's identity typically refers to its account on the server, but can refer to any representation the provider defines within the messaging system.</span></span> 
  
<span data-ttu-id="d6915-118">Furnishing 任一标识属性的服务提供程序应提供所有这些。</span><span class="sxs-lookup"><span data-stu-id="d6915-118">A service provider furnishing any of the identity properties should furnish all of them.</span></span> <span data-ttu-id="d6915-119">属于同一消息服务的提供程序应公开的 identity 属性相同的值。</span><span class="sxs-lookup"><span data-stu-id="d6915-119">Providers that belong to the same message service should expose the same values for the identity properties.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="d6915-120">相关资源</span><span class="sxs-lookup"><span data-stu-id="d6915-120">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="d6915-121">头文件</span><span class="sxs-lookup"><span data-stu-id="d6915-121">Header files</span></span>

<span data-ttu-id="d6915-122">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="d6915-122">Mapidefs.h</span></span>
  
> <span data-ttu-id="d6915-123">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="d6915-123">Provides data type definitions.</span></span>
    
<span data-ttu-id="d6915-124">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="d6915-124">Mapitags.h</span></span>
  
> <span data-ttu-id="d6915-125">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="d6915-125">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="d6915-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d6915-126">See also</span></span>



[<span data-ttu-id="d6915-127">IMAPISession::QueryIdentity</span><span class="sxs-lookup"><span data-stu-id="d6915-127">IMAPISession::QueryIdentity</span></span>](imapisession-queryidentity.md)


[<span data-ttu-id="d6915-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="d6915-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="d6915-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="d6915-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="d6915-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="d6915-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="d6915-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="d6915-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

