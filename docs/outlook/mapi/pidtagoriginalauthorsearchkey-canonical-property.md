---
title: PidTagOriginalAuthorSearchKey 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagOriginalAuthorSearchKey
api_type:
- COM
ms.assetid: 4a10cf99-c5e6-4a24-b531-3aebb7800bfe
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 09331e1201b6f6e45bb9e26e618ee59e67efbf8d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33409578"
---
# <a name="pidtagoriginalauthorsearchkey-canonical-property"></a><span data-ttu-id="8a3e8-103">PidTagOriginalAuthorSearchKey 规范属性</span><span class="sxs-lookup"><span data-stu-id="8a3e8-103">PidTagOriginalAuthorSearchKey Canonical Property</span></span>

  
  
<span data-ttu-id="8a3e8-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="8a3e8-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="8a3e8-105">包含邮件第一版的作者的搜索关键字, 即邮件转发或答复前的邮件。</span><span class="sxs-lookup"><span data-stu-id="8a3e8-105">Contains the search key of the author of the first version of a message, that is, the message before being forwarded or replied to.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="8a3e8-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="8a3e8-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="8a3e8-107">PR_ORIGINAL_AUTHOR_SEARCH_KEY</span><span class="sxs-lookup"><span data-stu-id="8a3e8-107">PR_ORIGINAL_AUTHOR_SEARCH_KEY</span></span>  <br/> |
|<span data-ttu-id="8a3e8-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="8a3e8-108">Identifier:</span></span>  <br/> |<span data-ttu-id="8a3e8-109">0x0056</span><span class="sxs-lookup"><span data-stu-id="8a3e8-109">0x0056</span></span>  <br/> |
|<span data-ttu-id="8a3e8-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="8a3e8-110">Data type:</span></span>  <br/> |<span data-ttu-id="8a3e8-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="8a3e8-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="8a3e8-112">区域：</span><span class="sxs-lookup"><span data-stu-id="8a3e8-112">Area:</span></span>  <br/> |<span data-ttu-id="8a3e8-113">服务器</span><span class="sxs-lookup"><span data-stu-id="8a3e8-113">Server</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="8a3e8-114">说明</span><span class="sxs-lookup"><span data-stu-id="8a3e8-114">Remarks</span></span>

<span data-ttu-id="8a3e8-115">此属性是邮件作者的地址属性之一。</span><span class="sxs-lookup"><span data-stu-id="8a3e8-115">This property is one of the address properties for the author of a message.</span></span> <span data-ttu-id="8a3e8-116">首次提交邮件时, 客户端应用程序应将此属性设置为**PR_SENDER_SEARCH_KEY**[PidTagSenderSearchKey](pidtagsendersearchkey-canonical-property.md)属性的值。</span><span class="sxs-lookup"><span data-stu-id="8a3e8-116">At first submission of the message, the client application should set this property to the value of the **PR_SENDER_SEARCH_KEY**[PidTagSenderSearchKey](pidtagsendersearchkey-canonical-property.md) property.</span></span> <span data-ttu-id="8a3e8-117">转发或答复邮件时, 它永远不会更改。</span><span class="sxs-lookup"><span data-stu-id="8a3e8-117">It is never changed when the message is forwarded or replied to.</span></span> 
  
<span data-ttu-id="8a3e8-118">原始作者属性允许保留本地邮件域外部的信息。</span><span class="sxs-lookup"><span data-stu-id="8a3e8-118">The original author properties allow for preservation of information from outside the local messaging domain.</span></span> <span data-ttu-id="8a3e8-119">当邮件到达其他邮件域 (例如从 Internet) 时, 这些属性提供了一种确保原始信息不会丢失的方法。</span><span class="sxs-lookup"><span data-stu-id="8a3e8-119">When a message arrives from another messaging domain, such as from the Internet, these properties provide a way to ensure that original information is not lost.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="8a3e8-120">相关资源</span><span class="sxs-lookup"><span data-stu-id="8a3e8-120">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="8a3e8-121">头文件</span><span class="sxs-lookup"><span data-stu-id="8a3e8-121">Header files</span></span>

<span data-ttu-id="8a3e8-122">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="8a3e8-122">Mapidefs.h</span></span>
  
> <span data-ttu-id="8a3e8-123">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="8a3e8-123">Provides data type definitions.</span></span>
    
<span data-ttu-id="8a3e8-124">Mapitags</span><span class="sxs-lookup"><span data-stu-id="8a3e8-124">Mapitags.h</span></span>
  
> <span data-ttu-id="8a3e8-125">包含列为关联属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="8a3e8-125">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="8a3e8-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8a3e8-126">See also</span></span>



[<span data-ttu-id="8a3e8-127">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="8a3e8-127">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="8a3e8-128">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="8a3e8-128">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="8a3e8-129">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="8a3e8-129">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="8a3e8-130">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="8a3e8-130">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

