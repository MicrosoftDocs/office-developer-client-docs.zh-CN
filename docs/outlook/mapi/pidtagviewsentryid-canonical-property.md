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
ms.openlocfilehash: 73ed7213ea2bd5079458ccc237b65590f06e8d53
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22586261"
---
# <a name="pidtagviewsentryid-canonical-property"></a><span data-ttu-id="f543b-103">PidTagViewsEntryId 规范属性</span><span class="sxs-lookup"><span data-stu-id="f543b-103">PidTagViewsEntryId Canonical Property</span></span>

  
  
<span data-ttu-id="f543b-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f543b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f543b-105">包含用户定义的视图文件夹的项标识符。</span><span class="sxs-lookup"><span data-stu-id="f543b-105">Contains the entry identifier of the user-defined Views folder.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="f543b-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="f543b-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="f543b-107">PR_VIEWS_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="f543b-107">PR_VIEWS_ENTRYID</span></span>  <br/> |
|<span data-ttu-id="f543b-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="f543b-108">Identifier:</span></span>  <br/> |<span data-ttu-id="f543b-109">0x35E5</span><span class="sxs-lookup"><span data-stu-id="f543b-109">0x35E5</span></span>  <br/> |
|<span data-ttu-id="f543b-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="f543b-110">Data type:</span></span>  <br/> |<span data-ttu-id="f543b-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="f543b-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="f543b-112">区域：</span><span class="sxs-lookup"><span data-stu-id="f543b-112">Area:</span></span>  <br/> |<span data-ttu-id="f543b-113">MAPI 邮件存储</span><span class="sxs-lookup"><span data-stu-id="f543b-113">MAPI message store</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="f543b-114">注解</span><span class="sxs-lookup"><span data-stu-id="f543b-114">Remarks</span></span>

<span data-ttu-id="f543b-115">公共视图文件夹包含一组预定义的标准视图说明符，而视图文件夹包含由消息的用户定义的说明符。</span><span class="sxs-lookup"><span data-stu-id="f543b-115">The common view folder contains a predefined set of standard view specifiers, while the view folder contains specifiers defined by a messaging user.</span></span> <span data-ttu-id="f543b-116">这些文件夹，不可见人际邮件 (IPM) 层次结构中，可以包含多个视图说明符，每个存储为邮件。</span><span class="sxs-lookup"><span data-stu-id="f543b-116">These folders, which are not visible in the interpersonal message (IPM) hierarchy, can hold many view specifiers, each one stored as a message.</span></span> <span data-ttu-id="f543b-117">客户端应用程序可以选择合并两个说明符集并使其同时可用。</span><span class="sxs-lookup"><span data-stu-id="f543b-117">The client application can choose to merge the two sets of specifiers and make them both available.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="f543b-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="f543b-118">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="f543b-119">头文件</span><span class="sxs-lookup"><span data-stu-id="f543b-119">Header files</span></span>

<span data-ttu-id="f543b-120">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="f543b-120">Mapidefs.h</span></span>
  
> <span data-ttu-id="f543b-121">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="f543b-121">Provides data type definitions.</span></span>
    
<span data-ttu-id="f543b-122">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="f543b-122">Mapitags.h</span></span>
  
> <span data-ttu-id="f543b-123">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="f543b-123">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="f543b-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f543b-124">See also</span></span>



[<span data-ttu-id="f543b-125">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="f543b-125">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="f543b-126">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="f543b-126">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="f543b-127">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="f543b-127">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="f543b-128">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="f543b-128">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

