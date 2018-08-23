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
ms.openlocfilehash: 02d2c30fede7e554910a1bedb01b79c488447bb3
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22595354"
---
# <a name="pidtagstoreprovider-canonical-property"></a><span data-ttu-id="d3c41-103">PidTagStoreProvider 规范属性</span><span class="sxs-lookup"><span data-stu-id="d3c41-103">PidTagStoreProvider Canonical Property</span></span>

  
  
<span data-ttu-id="d3c41-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d3c41-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d3c41-105">包含一个提供程序定义[MAPIUID](mapiuid.md)结构，指示邮件存储的类型。</span><span class="sxs-lookup"><span data-stu-id="d3c41-105">Contains a provider-defined [MAPIUID](mapiuid.md) structure that indicates the type of the message store.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="d3c41-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="d3c41-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="d3c41-107">PR_MDB_PROVIDER</span><span class="sxs-lookup"><span data-stu-id="d3c41-107">PR_MDB_PROVIDER</span></span>  <br/> |
|<span data-ttu-id="d3c41-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="d3c41-108">Identifier:</span></span>  <br/> |<span data-ttu-id="d3c41-109">0x3414</span><span class="sxs-lookup"><span data-stu-id="d3c41-109">0x3414</span></span>  <br/> |
|<span data-ttu-id="d3c41-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="d3c41-110">Data type:</span></span>  <br/> |<span data-ttu-id="d3c41-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="d3c41-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="d3c41-112">区域：</span><span class="sxs-lookup"><span data-stu-id="d3c41-112">Area:</span></span>  <br/> |<span data-ttu-id="d3c41-113">ID 属性</span><span class="sxs-lookup"><span data-stu-id="d3c41-113">ID properties</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="d3c41-114">注解</span><span class="sxs-lookup"><span data-stu-id="d3c41-114">Remarks</span></span>

<span data-ttu-id="d3c41-115">[MAPIUID](mapiuid.md)结构标识消息存储库的类型。</span><span class="sxs-lookup"><span data-stu-id="d3c41-115">The [MAPIUID](mapiuid.md) structure identifies the type of message store.</span></span> <span data-ttu-id="d3c41-116">此值计算的消息存储对象上的消息存储提供程序，并且是唯一的每个提供程序。</span><span class="sxs-lookup"><span data-stu-id="d3c41-116">The value is computed by message store providers on message store objects and is unique to each provider.</span></span> <span data-ttu-id="d3c41-117">它通常用于浏览消息存储表如公用文件夹中查找所需类型的存储区。</span><span class="sxs-lookup"><span data-stu-id="d3c41-117">It is typically used for browsing through the message store table to find a store of the desired type, such as public folders.</span></span> 
  
<span data-ttu-id="d3c41-118">此属性是类似于通讯簿的**PR_AB_PROVIDER_ID** ([PidTagAbProviderId](pidtagabproviderid-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="d3c41-118">This property is analogous to the **PR_AB_PROVIDER_ID** ([PidTagAbProviderId](pidtagabproviderid-canonical-property.md)) property for address books.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="d3c41-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="d3c41-119">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="d3c41-120">头文件</span><span class="sxs-lookup"><span data-stu-id="d3c41-120">Header files</span></span>

<span data-ttu-id="d3c41-121">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="d3c41-121">Mapidefs.h</span></span>
  
> <span data-ttu-id="d3c41-122">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="d3c41-122">Provides data type definitions.</span></span>
    
<span data-ttu-id="d3c41-123">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="d3c41-123">Mapitags.h</span></span>
  
> <span data-ttu-id="d3c41-124">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="d3c41-124">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="d3c41-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d3c41-125">See also</span></span>



[<span data-ttu-id="d3c41-126">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="d3c41-126">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="d3c41-127">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="d3c41-127">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="d3c41-128">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="d3c41-128">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="d3c41-129">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="d3c41-129">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

