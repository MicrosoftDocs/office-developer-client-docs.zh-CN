---
title: PidTagIpmWastebasketEntryId 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagIpmWastebasketEntryId
api_type:
- HeaderDef
ms.assetid: 0f8dd043-66f0-4193-9b95-853bc3827f73
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 3794386c4461c90f973e4028132cb8220dfaa19b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33426350"
---
# <a name="pidtagipmwastebasketentryid-canonical-property"></a><span data-ttu-id="8441b-103">PidTagIpmWastebasketEntryId 规范属性</span><span class="sxs-lookup"><span data-stu-id="8441b-103">PidTagIpmWastebasketEntryId Canonical Property</span></span>

  
  
<span data-ttu-id="8441b-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="8441b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="8441b-105">包含标准人际邮件 (IPM) "已删除邮件" 文件夹的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="8441b-105">Contains the entry identifier of the standard interpersonal message (IPM) Deleted Items folder.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="8441b-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="8441b-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="8441b-107">PR_IPM_WASTEBASKET_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="8441b-107">PR_IPM_WASTEBASKET_ENTRYID</span></span>  <br/> |
|<span data-ttu-id="8441b-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="8441b-108">Identifier:</span></span>  <br/> |<span data-ttu-id="8441b-109">0x35E3</span><span class="sxs-lookup"><span data-stu-id="8441b-109">0x35E3</span></span>  <br/> |
|<span data-ttu-id="8441b-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="8441b-110">Data type:</span></span>  <br/> |<span data-ttu-id="8441b-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="8441b-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="8441b-112">区域：</span><span class="sxs-lookup"><span data-stu-id="8441b-112">Area:</span></span>  <br/> |<span data-ttu-id="8441b-113">Folder</span><span class="sxs-lookup"><span data-stu-id="8441b-113">Folder</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="8441b-114">说明</span><span class="sxs-lookup"><span data-stu-id="8441b-114">Remarks</span></span>

<span data-ttu-id="8441b-115">客户端应用程序应将已删除的人际邮件移动到 "已删除邮件" 文件夹。</span><span class="sxs-lookup"><span data-stu-id="8441b-115">A client application should move deleted interpersonal messages to the Deleted Items folder.</span></span> <span data-ttu-id="8441b-116">如果邮件已在此文件夹中, 或者如果该属性不受支持, 客户端应删除该邮件。</span><span class="sxs-lookup"><span data-stu-id="8441b-116">If the message is already in this folder, or if this property is not supported, the client should delete the message.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="8441b-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="8441b-117">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="8441b-118">头文件</span><span class="sxs-lookup"><span data-stu-id="8441b-118">Header files</span></span>

<span data-ttu-id="8441b-119">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="8441b-119">Mapidefs.h</span></span>
  
> <span data-ttu-id="8441b-120">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="8441b-120">Provides data type definitions.</span></span>
    
<span data-ttu-id="8441b-121">Mapitags</span><span class="sxs-lookup"><span data-stu-id="8441b-121">Mapitags.h</span></span>
  
> <span data-ttu-id="8441b-122">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="8441b-122">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="8441b-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8441b-123">See also</span></span>



[<span data-ttu-id="8441b-124">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="8441b-124">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="8441b-125">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="8441b-125">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="8441b-126">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="8441b-126">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="8441b-127">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="8441b-127">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

