---
title: PidTagAbProviderId 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagAbProviderId
api_type:
- HeaderDef
ms.assetid: 23cfd1d0-8e9d-4508-93dd-a88c0ef77c51
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 84a2d5517d405ac6deb61f7c4679d6816e802404
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777270"
---
# <a name="pidtagabproviderid-canonical-property"></a><span data-ttu-id="b5f0f-103">PidTagAbProviderId 规范属性</span><span class="sxs-lookup"><span data-stu-id="b5f0f-103">PidTagAbProviderId Canonical Property</span></span>

  
  
<span data-ttu-id="b5f0f-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="b5f0f-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="b5f0f-105">包含通讯簿提供程序的[MAPIUID](mapiuid.md)结构。</span><span class="sxs-lookup"><span data-stu-id="b5f0f-105">Contains an address book provider's [MAPIUID](mapiuid.md) structure.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="b5f0f-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="b5f0f-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="b5f0f-107">PR_AB_PROVIDER_ID</span><span class="sxs-lookup"><span data-stu-id="b5f0f-107">PR_AB_PROVIDER_ID</span></span>  <br/> |
|<span data-ttu-id="b5f0f-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="b5f0f-108">Identifier:</span></span>  <br/> |<span data-ttu-id="b5f0f-109">0x3615</span><span class="sxs-lookup"><span data-stu-id="b5f0f-109">0x3615</span></span>  <br/> |
|<span data-ttu-id="b5f0f-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="b5f0f-110">Data type:</span></span>  <br/> |<span data-ttu-id="b5f0f-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="b5f0f-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="b5f0f-112">区域：</span><span class="sxs-lookup"><span data-stu-id="b5f0f-112">Area:</span></span>  <br/> |<span data-ttu-id="b5f0f-113">通讯簿</span><span class="sxs-lookup"><span data-stu-id="b5f0f-113">Address book</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="b5f0f-114">说明</span><span class="sxs-lookup"><span data-stu-id="b5f0f-114">Remarks</span></span>

<span data-ttu-id="b5f0f-115">**MAPIUID**结构标识的通讯簿提供程序提供此容器层次结构中的特定容器。</span><span class="sxs-lookup"><span data-stu-id="b5f0f-115">The **MAPIUID** structure identifies which address book provider supplies this particular container in the container hierarchy.</span></span> <span data-ttu-id="b5f0f-116">值是唯一的每个提供程序。</span><span class="sxs-lookup"><span data-stu-id="b5f0f-116">The value is unique to each provider.</span></span> 
  
<span data-ttu-id="b5f0f-117">通讯簿提供程序可以提供多个标识符。</span><span class="sxs-lookup"><span data-stu-id="b5f0f-117">An address book provider can provide more than one identifier.</span></span> <span data-ttu-id="b5f0f-118">例如，提供两个不同的容器的提供程序可以发布**PR_AB_PROVIDER_ID**对每个容器的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="b5f0f-118">For example, a provider that supplies two different containers can publish in **PR_AB_PROVIDER_ID** unique identifiers for each container.</span></span> 
  
 <span data-ttu-id="b5f0f-119">**PR_AB_PROVIDER_ID**是类似于邮件存储的**PR_MDB_PROVIDER** ([PidTagStoreProvider](pidtagstoreprovider-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="b5f0f-119">**PR_AB_PROVIDER_ID** is analogous to the **PR_MDB_PROVIDER** ([PidTagStoreProvider](pidtagstoreprovider-canonical-property.md)) property for message stores.</span></span> <span data-ttu-id="b5f0f-120">客户端应用程序可以使用**PR_AB_PROVIDER_ID**通讯簿层次结构表中查找相关的行。</span><span class="sxs-lookup"><span data-stu-id="b5f0f-120">Client applications can use **PR_AB_PROVIDER_ID** to find related rows in an address book hierarchy table.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="b5f0f-121">相关资源</span><span class="sxs-lookup"><span data-stu-id="b5f0f-121">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="b5f0f-122">头文件</span><span class="sxs-lookup"><span data-stu-id="b5f0f-122">Header files</span></span>

<span data-ttu-id="b5f0f-123">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="b5f0f-123">Mapitags.h</span></span>
  
> <span data-ttu-id="b5f0f-124">包含列为相关属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="b5f0f-124">Contains definitions of properties listed as associated properties.</span></span>
    
<span data-ttu-id="b5f0f-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="b5f0f-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="b5f0f-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="b5f0f-126">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="b5f0f-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b5f0f-127">See also</span></span>



[<span data-ttu-id="b5f0f-128">MAPIUID</span><span class="sxs-lookup"><span data-stu-id="b5f0f-128">MAPIUID</span></span>](mapiuid.md)
  
[<span data-ttu-id="b5f0f-129">PidTagStoreProvider 规范属性</span><span class="sxs-lookup"><span data-stu-id="b5f0f-129">PidTagStoreProvider Canonical Property</span></span>](pidtagstoreprovider-canonical-property.md)


[<span data-ttu-id="b5f0f-130">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="b5f0f-130">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="b5f0f-131">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="b5f0f-131">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="b5f0f-132">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="b5f0f-132">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

