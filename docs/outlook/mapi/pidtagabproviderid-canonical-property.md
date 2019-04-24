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
ms.openlocfilehash: 820df61ec23e2dd1459582e5a7bb35ad9525e0b4
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32315818"
---
# <a name="pidtagabproviderid-canonical-property"></a><span data-ttu-id="0a192-103">PidTagAbProviderId 规范属性</span><span class="sxs-lookup"><span data-stu-id="0a192-103">PidTagAbProviderId Canonical Property</span></span>

  
  
<span data-ttu-id="0a192-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="0a192-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="0a192-105">包含通讯簿提供程序的[MAPIUID](mapiuid.md)结构。</span><span class="sxs-lookup"><span data-stu-id="0a192-105">Contains an address book provider's [MAPIUID](mapiuid.md) structure.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="0a192-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="0a192-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="0a192-107">PR_AB_PROVIDER_ID</span><span class="sxs-lookup"><span data-stu-id="0a192-107">PR_AB_PROVIDER_ID</span></span>  <br/> |
|<span data-ttu-id="0a192-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="0a192-108">Identifier:</span></span>  <br/> |<span data-ttu-id="0a192-109">0x3615</span><span class="sxs-lookup"><span data-stu-id="0a192-109">0x3615</span></span>  <br/> |
|<span data-ttu-id="0a192-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="0a192-110">Data type:</span></span>  <br/> |<span data-ttu-id="0a192-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="0a192-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="0a192-112">区域：</span><span class="sxs-lookup"><span data-stu-id="0a192-112">Area:</span></span>  <br/> |<span data-ttu-id="0a192-113">通讯簿</span><span class="sxs-lookup"><span data-stu-id="0a192-113">Address book</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="0a192-114">注解</span><span class="sxs-lookup"><span data-stu-id="0a192-114">Remarks</span></span>

<span data-ttu-id="0a192-115">**MAPIUID**结构标识哪个通讯簿提供程序在容器层次结构中提供此特定容器。</span><span class="sxs-lookup"><span data-stu-id="0a192-115">The **MAPIUID** structure identifies which address book provider supplies this particular container in the container hierarchy.</span></span> <span data-ttu-id="0a192-116">每个提供程序的值都是唯一的。</span><span class="sxs-lookup"><span data-stu-id="0a192-116">The value is unique to each provider.</span></span> 
  
<span data-ttu-id="0a192-117">通讯簿提供程序可以提供一个以上的标识符。</span><span class="sxs-lookup"><span data-stu-id="0a192-117">An address book provider can provide more than one identifier.</span></span> <span data-ttu-id="0a192-118">例如, 提供两个不同容器的提供程序可以在每个容器的**PR_AB_PROVIDER_ID**唯一标识符中发布。</span><span class="sxs-lookup"><span data-stu-id="0a192-118">For example, a provider that supplies two different containers can publish in **PR_AB_PROVIDER_ID** unique identifiers for each container.</span></span> 
  
 <span data-ttu-id="0a192-119">**PR_AB_PROVIDER_ID**类似于邮件存储区的**PR_MDB_PROVIDER** ([PidTagStoreProvider](pidtagstoreprovider-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="0a192-119">**PR_AB_PROVIDER_ID** is analogous to the **PR_MDB_PROVIDER** ([PidTagStoreProvider](pidtagstoreprovider-canonical-property.md)) property for message stores.</span></span> <span data-ttu-id="0a192-120">客户端应用程序可以使用**PR_AB_PROVIDER_ID**来查找通讯簿层次结构表中的相关行。</span><span class="sxs-lookup"><span data-stu-id="0a192-120">Client applications can use **PR_AB_PROVIDER_ID** to find related rows in an address book hierarchy table.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="0a192-121">相关资源</span><span class="sxs-lookup"><span data-stu-id="0a192-121">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="0a192-122">头文件</span><span class="sxs-lookup"><span data-stu-id="0a192-122">Header files</span></span>

<span data-ttu-id="0a192-123">Mapitags</span><span class="sxs-lookup"><span data-stu-id="0a192-123">Mapitags.h</span></span>
  
> <span data-ttu-id="0a192-124">包含列为关联属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="0a192-124">Contains definitions of properties listed as associated properties.</span></span>
    
<span data-ttu-id="0a192-125">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="0a192-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="0a192-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="0a192-126">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="0a192-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0a192-127">See also</span></span>



[<span data-ttu-id="0a192-128">MAPIUID</span><span class="sxs-lookup"><span data-stu-id="0a192-128">MAPIUID</span></span>](mapiuid.md)
  
[<span data-ttu-id="0a192-129">PidTagStoreProvider 规范属性</span><span class="sxs-lookup"><span data-stu-id="0a192-129">PidTagStoreProvider Canonical Property</span></span>](pidtagstoreprovider-canonical-property.md)


[<span data-ttu-id="0a192-130">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="0a192-130">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="0a192-131">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="0a192-131">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="0a192-132">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="0a192-132">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

