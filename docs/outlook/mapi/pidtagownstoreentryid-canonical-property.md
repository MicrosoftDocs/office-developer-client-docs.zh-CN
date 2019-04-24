---
title: PidTagOwnStoreEntryId 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagOwnStoreEntryId
api_type:
- COM
ms.assetid: 6a82ee90-10a1-49e0-8f3a-a2cd9f490f99
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 16a23c4e711bf9f7b670dff8b3e8f65371aa6bda
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32335446"
---
# <a name="pidtagownstoreentryid-canonical-property"></a><span data-ttu-id="cd43a-103">PidTagOwnStoreEntryId 规范属性</span><span class="sxs-lookup"><span data-stu-id="cd43a-103">PidTagOwnStoreEntryId Canonical Property</span></span>

  
  
<span data-ttu-id="cd43a-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="cd43a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="cd43a-105">包含传输的紧密耦合邮件存储区的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="cd43a-105">Contains the entry identifier of a transport's tightly coupled message store.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="cd43a-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="cd43a-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="cd43a-107">PR_OWN_STORE_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="cd43a-107">PR_OWN_STORE_ENTRYID</span></span>  <br/> |
|<span data-ttu-id="cd43a-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="cd43a-108">Identifier:</span></span>  <br/> |<span data-ttu-id="cd43a-109">0x3E06</span><span class="sxs-lookup"><span data-stu-id="cd43a-109">0x3E06</span></span>  <br/> |
|<span data-ttu-id="cd43a-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="cd43a-110">Data type:</span></span>  <br/> |<span data-ttu-id="cd43a-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="cd43a-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="cd43a-112">区域：</span><span class="sxs-lookup"><span data-stu-id="cd43a-112">Area:</span></span>  <br/> |<span data-ttu-id="cd43a-113">邮件存储库属性</span><span class="sxs-lookup"><span data-stu-id="cd43a-113">Message Store Properties</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="cd43a-114">注解</span><span class="sxs-lookup"><span data-stu-id="cd43a-114">Remarks</span></span>

<span data-ttu-id="cd43a-115">此属性指定紧耦合存储区的条目标识符 (如果存在)。</span><span class="sxs-lookup"><span data-stu-id="cd43a-115">This property specifies the entry identifier for the tightly coupled store, if one exists.</span></span> <span data-ttu-id="cd43a-116">例如, 传输提供程序可以指定专用文件夹存储项标识符, 以便 MAPI 后台处理程序可以将传输提供程序连接到存储区。</span><span class="sxs-lookup"><span data-stu-id="cd43a-116">For example, a transport provider can specify the private folder store entry identifier so that the MAPI spooler can connect the transport provider to the store.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="cd43a-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="cd43a-117">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="cd43a-118">头文件</span><span class="sxs-lookup"><span data-stu-id="cd43a-118">Header files</span></span>

<span data-ttu-id="cd43a-119">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="cd43a-119">Mapidefs.h</span></span>
  
> <span data-ttu-id="cd43a-120">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="cd43a-120">Provides data type definitions.</span></span>
    
<span data-ttu-id="cd43a-121">Mapitags</span><span class="sxs-lookup"><span data-stu-id="cd43a-121">Mapitags.h</span></span>
  
> <span data-ttu-id="cd43a-122">包含列为关联属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="cd43a-122">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="cd43a-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cd43a-123">See also</span></span>



[<span data-ttu-id="cd43a-124">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="cd43a-124">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="cd43a-125">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="cd43a-125">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="cd43a-126">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="cd43a-126">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="cd43a-127">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="cd43a-127">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

