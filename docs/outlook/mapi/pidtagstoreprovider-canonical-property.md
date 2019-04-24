---
title: PidTagStoreProvider 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagStoreProvider
api_type:
- COM
ms.assetid: 6f6cc66f-a08e-4f8e-b33a-d3674319248e
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 6266c9293f54ce764c5b5b0e41d43767490abcf7
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32278706"
---
# <a name="pidtagstoreprovider-canonical-property"></a><span data-ttu-id="d3f3b-103">PidTagStoreProvider 规范属性</span><span class="sxs-lookup"><span data-stu-id="d3f3b-103">PidTagStoreProvider Canonical Property</span></span>

  
  
<span data-ttu-id="d3f3b-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d3f3b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d3f3b-105">包含提供程序定义的[MAPIUID](mapiuid.md)结构, 该结构指示邮件存储区的类型。</span><span class="sxs-lookup"><span data-stu-id="d3f3b-105">Contains a provider-defined [MAPIUID](mapiuid.md) structure that indicates the type of the message store.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="d3f3b-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="d3f3b-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="d3f3b-107">PR_MDB_PROVIDER</span><span class="sxs-lookup"><span data-stu-id="d3f3b-107">PR_MDB_PROVIDER</span></span>  <br/> |
|<span data-ttu-id="d3f3b-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="d3f3b-108">Identifier:</span></span>  <br/> |<span data-ttu-id="d3f3b-109">0x3414</span><span class="sxs-lookup"><span data-stu-id="d3f3b-109">0x3414</span></span>  <br/> |
|<span data-ttu-id="d3f3b-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="d3f3b-110">Data type:</span></span>  <br/> |<span data-ttu-id="d3f3b-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="d3f3b-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="d3f3b-112">区域：</span><span class="sxs-lookup"><span data-stu-id="d3f3b-112">Area:</span></span>  <br/> |<span data-ttu-id="d3f3b-113">ID 属性</span><span class="sxs-lookup"><span data-stu-id="d3f3b-113">ID properties</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="d3f3b-114">注解</span><span class="sxs-lookup"><span data-stu-id="d3f3b-114">Remarks</span></span>

<span data-ttu-id="d3f3b-115">[MAPIUID](mapiuid.md)结构标识邮件存储的类型。</span><span class="sxs-lookup"><span data-stu-id="d3f3b-115">The [MAPIUID](mapiuid.md) structure identifies the type of message store.</span></span> <span data-ttu-id="d3f3b-116">值由邮件存储区对象的邮件存储提供程序计算, 并且每个提供程序都是唯一的。</span><span class="sxs-lookup"><span data-stu-id="d3f3b-116">The value is computed by message store providers on message store objects and is unique to each provider.</span></span> <span data-ttu-id="d3f3b-117">它通常用于浏览邮件存储区表以查找所需类型的存储, 例如公用文件夹。</span><span class="sxs-lookup"><span data-stu-id="d3f3b-117">It is typically used for browsing through the message store table to find a store of the desired type, such as public folders.</span></span> 
  
<span data-ttu-id="d3f3b-118">此属性类似于通讯簿的**PR_AB_PROVIDER_ID** ([PidTagAbProviderId](pidtagabproviderid-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="d3f3b-118">This property is analogous to the **PR_AB_PROVIDER_ID** ([PidTagAbProviderId](pidtagabproviderid-canonical-property.md)) property for address books.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="d3f3b-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="d3f3b-119">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="d3f3b-120">头文件</span><span class="sxs-lookup"><span data-stu-id="d3f3b-120">Header files</span></span>

<span data-ttu-id="d3f3b-121">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="d3f3b-121">Mapidefs.h</span></span>
  
> <span data-ttu-id="d3f3b-122">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="d3f3b-122">Provides data type definitions.</span></span>
    
<span data-ttu-id="d3f3b-123">Mapitags</span><span class="sxs-lookup"><span data-stu-id="d3f3b-123">Mapitags.h</span></span>
  
> <span data-ttu-id="d3f3b-124">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="d3f3b-124">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="d3f3b-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d3f3b-125">See also</span></span>



[<span data-ttu-id="d3f3b-126">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="d3f3b-126">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="d3f3b-127">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="d3f3b-127">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="d3f3b-128">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="d3f3b-128">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="d3f3b-129">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="d3f3b-129">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

