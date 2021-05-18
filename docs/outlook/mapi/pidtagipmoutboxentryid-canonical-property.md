---
title: PidTagIpmOutboxEntryId 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagIpmOutboxEntryId
api_type:
- HeaderDef
ms.assetid: fa03d819-2621-4990-80ae-4140b83a8a85
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: ec73a456f87b18905c180803d26720ef09254c7e
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33405056"
---
# <a name="pidtagipmoutboxentryid-canonical-property"></a><span data-ttu-id="5aed5-103">PidTagIpmOutboxEntryId 规范属性</span><span class="sxs-lookup"><span data-stu-id="5aed5-103">PidTagIpmOutboxEntryId Canonical Property</span></span>

  
  
<span data-ttu-id="5aed5-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="5aed5-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="5aed5-105">包含标准性邮件的条目标识符 (IPM) 发件箱文件夹。</span><span class="sxs-lookup"><span data-stu-id="5aed5-105">Contains the entry identifier of the standard interpersonal message (IPM) Outbox folder.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="5aed5-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="5aed5-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="5aed5-107">PR_IPM_OUTBOX_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="5aed5-107">PR_IPM_OUTBOX_ENTRYID</span></span>  <br/> |
|<span data-ttu-id="5aed5-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="5aed5-108">Identifier:</span></span>  <br/> |<span data-ttu-id="5aed5-109">0x35E2</span><span class="sxs-lookup"><span data-stu-id="5aed5-109">0x35E2</span></span>  <br/> |
|<span data-ttu-id="5aed5-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="5aed5-110">Data type:</span></span>  <br/> |<span data-ttu-id="5aed5-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="5aed5-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="5aed5-112">区域：</span><span class="sxs-lookup"><span data-stu-id="5aed5-112">Area:</span></span>  <br/> |<span data-ttu-id="5aed5-113">文件夹</span><span class="sxs-lookup"><span data-stu-id="5aed5-113">Folder</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="5aed5-114">备注</span><span class="sxs-lookup"><span data-stu-id="5aed5-114">Remarks</span></span>

<span data-ttu-id="5aed5-115">出站邮件通常在发件箱文件夹中创建。</span><span class="sxs-lookup"><span data-stu-id="5aed5-115">Outbound messages are usually created in the Outbox folder.</span></span> <span data-ttu-id="5aed5-116">应当将邮件放入此文件夹中进行提交。</span><span class="sxs-lookup"><span data-stu-id="5aed5-116">Interpersonal messages should be placed in this folder for submission.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="5aed5-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="5aed5-117">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="5aed5-118">头文件</span><span class="sxs-lookup"><span data-stu-id="5aed5-118">Header files</span></span>

<span data-ttu-id="5aed5-119">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="5aed5-119">Mapidefs.h</span></span>
  
> <span data-ttu-id="5aed5-120">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="5aed5-120">Provides data type definitions.</span></span>
    
<span data-ttu-id="5aed5-121">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="5aed5-121">Mapitags.h</span></span>
  
> <span data-ttu-id="5aed5-122">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="5aed5-122">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="5aed5-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5aed5-123">See also</span></span>



[<span data-ttu-id="5aed5-124">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="5aed5-124">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="5aed5-125">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="5aed5-125">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="5aed5-126">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="5aed5-126">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="5aed5-127">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="5aed5-127">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

