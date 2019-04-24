---
title: PidTagViewsEntryId 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagViewsEntryId
api_type:
- COM
ms.assetid: 8350a37c-6f42-4bef-82e0-35aa12b09fcf
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7d261ac0e9aaf36f2333b04b45edfaf8e24fa30d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32350692"
---
# <a name="pidtagviewsentryid-canonical-property"></a><span data-ttu-id="18d6d-103">PidTagViewsEntryId 规范属性</span><span class="sxs-lookup"><span data-stu-id="18d6d-103">PidTagViewsEntryId Canonical Property</span></span>

  
  
<span data-ttu-id="18d6d-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="18d6d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="18d6d-105">包含用户定义的视图文件夹的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="18d6d-105">Contains the entry identifier of the user-defined Views folder.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="18d6d-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="18d6d-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="18d6d-107">PR_VIEWS_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="18d6d-107">PR_VIEWS_ENTRYID</span></span>  <br/> |
|<span data-ttu-id="18d6d-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="18d6d-108">Identifier:</span></span>  <br/> |<span data-ttu-id="18d6d-109">0x35E5</span><span class="sxs-lookup"><span data-stu-id="18d6d-109">0x35E5</span></span>  <br/> |
|<span data-ttu-id="18d6d-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="18d6d-110">Data type:</span></span>  <br/> |<span data-ttu-id="18d6d-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="18d6d-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="18d6d-112">区域：</span><span class="sxs-lookup"><span data-stu-id="18d6d-112">Area:</span></span>  <br/> |<span data-ttu-id="18d6d-113">MAPI 邮件存储</span><span class="sxs-lookup"><span data-stu-id="18d6d-113">MAPI message store</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="18d6d-114">注解</span><span class="sxs-lookup"><span data-stu-id="18d6d-114">Remarks</span></span>

<span data-ttu-id="18d6d-115">公共视图文件夹包含一组预定义的标准视图说明符, 而 view 文件夹包含由邮件用户定义的说明符。</span><span class="sxs-lookup"><span data-stu-id="18d6d-115">The common view folder contains a predefined set of standard view specifiers, while the view folder contains specifiers defined by a messaging user.</span></span> <span data-ttu-id="18d6d-116">这些文件夹在人际邮件 (IPM) 层次结构中不可见, 可以包含多个视图说明符, 每个都存储为一条消息。</span><span class="sxs-lookup"><span data-stu-id="18d6d-116">These folders, which are not visible in the interpersonal message (IPM) hierarchy, can hold many view specifiers, each one stored as a message.</span></span> <span data-ttu-id="18d6d-117">客户端应用程序可以选择合并两组说明符, 并使它们都可用。</span><span class="sxs-lookup"><span data-stu-id="18d6d-117">The client application can choose to merge the two sets of specifiers and make them both available.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="18d6d-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="18d6d-118">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="18d6d-119">头文件</span><span class="sxs-lookup"><span data-stu-id="18d6d-119">Header files</span></span>

<span data-ttu-id="18d6d-120">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="18d6d-120">Mapidefs.h</span></span>
  
> <span data-ttu-id="18d6d-121">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="18d6d-121">Provides data type definitions.</span></span>
    
<span data-ttu-id="18d6d-122">Mapitags</span><span class="sxs-lookup"><span data-stu-id="18d6d-122">Mapitags.h</span></span>
  
> <span data-ttu-id="18d6d-123">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="18d6d-123">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="18d6d-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="18d6d-124">See also</span></span>



[<span data-ttu-id="18d6d-125">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="18d6d-125">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="18d6d-126">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="18d6d-126">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="18d6d-127">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="18d6d-127">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="18d6d-128">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="18d6d-128">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

