---
title: PidTagStoreState 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagStoreState
api_type:
- COM
ms.assetid: 36e49cf5-1411-42c5-9112-09958243996d
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 8f00addf7abdd765d97c54350e46979f788f06ba
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32341151"
---
# <a name="pidtagstorestate-canonical-property"></a><span data-ttu-id="cc1be-103">PidTagStoreState 规范属性</span><span class="sxs-lookup"><span data-stu-id="cc1be-103">PidTagStoreState Canonical Property</span></span>

  
  
<span data-ttu-id="cc1be-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="cc1be-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="cc1be-105">包含描述邮件存储状态的标志。</span><span class="sxs-lookup"><span data-stu-id="cc1be-105">Contains a flag that describes the state of the message store.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="cc1be-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="cc1be-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="cc1be-107">PR_STORE_STATE</span><span class="sxs-lookup"><span data-stu-id="cc1be-107">PR_STORE_STATE</span></span>  <br/> |
|<span data-ttu-id="cc1be-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="cc1be-108">Identifier:</span></span>  <br/> |<span data-ttu-id="cc1be-109">0x340E</span><span class="sxs-lookup"><span data-stu-id="cc1be-109">0x340E</span></span>  <br/> |
|<span data-ttu-id="cc1be-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="cc1be-110">Data type:</span></span>  <br/> |<span data-ttu-id="cc1be-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="cc1be-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="cc1be-112">区域：</span><span class="sxs-lookup"><span data-stu-id="cc1be-112">Area:</span></span>  <br/> |<span data-ttu-id="cc1be-113">MAPI 邮件存储</span><span class="sxs-lookup"><span data-stu-id="cc1be-113">MAPI message store</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="cc1be-114">备注</span><span class="sxs-lookup"><span data-stu-id="cc1be-114">Remarks</span></span>

<span data-ttu-id="cc1be-115">此属性是动态的，并且可基于用户操作更改，PR_STORE_SUPPORT_MASK ( [PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="cc1be-115">This property is dynamic and can change based on user actions, unlike the **PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) property.</span></span> 
  
<span data-ttu-id="cc1be-116">可以设置以下值：</span><span class="sxs-lookup"><span data-stu-id="cc1be-116">The following value can be set:</span></span>
  
<span data-ttu-id="cc1be-117">STORE_HAS_SEARCHES</span><span class="sxs-lookup"><span data-stu-id="cc1be-117">STORE_HAS_SEARCHES</span></span> 
  
> <span data-ttu-id="cc1be-118">用户已创建存储区中的一个或多个活动搜索。</span><span class="sxs-lookup"><span data-stu-id="cc1be-118">The user has created one or more active searches in the store.</span></span>
    
## <a name="related-resources"></a><span data-ttu-id="cc1be-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="cc1be-119">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="cc1be-120">协议规范</span><span class="sxs-lookup"><span data-stu-id="cc1be-120">Protocol specifications</span></span>

<span data-ttu-id="cc1be-121">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="cc1be-121">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="cc1be-122">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="cc1be-122">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="cc1be-123">[[MS-OXCSTOR]](https://msdn.microsoft.com/library/d42ed1e0-3e77-4264-bd59-7afc583510e2%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="cc1be-123">[[MS-OXCSTOR]](https://msdn.microsoft.com/library/d42ed1e0-3e77-4264-bd59-7afc583510e2%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="cc1be-124">指定核心邮件存储对象的允许操作。</span><span class="sxs-lookup"><span data-stu-id="cc1be-124">Specifies permissible operations for the core message store objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="cc1be-125">头文件</span><span class="sxs-lookup"><span data-stu-id="cc1be-125">Header files</span></span>

<span data-ttu-id="cc1be-126">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="cc1be-126">Mapidefs.h</span></span>
  
> <span data-ttu-id="cc1be-127">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="cc1be-127">Provides data type definitions.</span></span>
    
<span data-ttu-id="cc1be-128">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="cc1be-128">Mapitags.h</span></span>
  
> <span data-ttu-id="cc1be-129">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="cc1be-129">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="cc1be-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cc1be-130">See also</span></span>



[<span data-ttu-id="cc1be-131">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="cc1be-131">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="cc1be-132">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="cc1be-132">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="cc1be-133">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="cc1be-133">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="cc1be-134">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="cc1be-134">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

