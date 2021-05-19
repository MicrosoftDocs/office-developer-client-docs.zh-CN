---
title: PidTagReplyTime 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagReplyTime
api_type:
- COM
ms.assetid: d01f89bd-012e-4f08-9afa-e33aad9679a4
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 32de1e55fa03825a1f6391d7883107e8a853f6d0
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32346380"
---
# <a name="pidtagreplytime-canonical-property"></a><span data-ttu-id="2f9f6-103">PidTagReplyTime 规范属性</span><span class="sxs-lookup"><span data-stu-id="2f9f6-103">PidTagReplyTime Canonical Property</span></span>

  
  
<span data-ttu-id="2f9f6-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="2f9f6-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="2f9f6-105">包含邮件的截止时间。</span><span class="sxs-lookup"><span data-stu-id="2f9f6-105">Contains the deadline on a message.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="2f9f6-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="2f9f6-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="2f9f6-107">PR_REPLY_TIME</span><span class="sxs-lookup"><span data-stu-id="2f9f6-107">PR_REPLY_TIME</span></span>  <br/> |
|<span data-ttu-id="2f9f6-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="2f9f6-108">Identifier:</span></span>  <br/> |<span data-ttu-id="2f9f6-109">0x0030</span><span class="sxs-lookup"><span data-stu-id="2f9f6-109">0x0030</span></span>  <br/> |
|<span data-ttu-id="2f9f6-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="2f9f6-110">Data type:</span></span>  <br/> |<span data-ttu-id="2f9f6-111">PT_SYSTIME</span><span class="sxs-lookup"><span data-stu-id="2f9f6-111">PT_SYSTIME</span></span>  <br/> |
|<span data-ttu-id="2f9f6-112">区域：</span><span class="sxs-lookup"><span data-stu-id="2f9f6-112">Area:</span></span>  <br/> |<span data-ttu-id="2f9f6-113">MAPI 信封</span><span class="sxs-lookup"><span data-stu-id="2f9f6-113">MAPI envelope</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="2f9f6-114">相关资源</span><span class="sxs-lookup"><span data-stu-id="2f9f6-114">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="2f9f6-115">协议规范</span><span class="sxs-lookup"><span data-stu-id="2f9f6-115">Protocol specifications</span></span>

<span data-ttu-id="2f9f6-116">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="2f9f6-116">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="2f9f6-117">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="2f9f6-117">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="2f9f6-118">[[MS-OXOFLAG]](https://msdn.microsoft.com/library/f1e50be4-ed30-4c2a-b5cb-8ff3aaaf9b91%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="2f9f6-118">[[MS-OXOFLAG]](https://msdn.microsoft.com/library/f1e50be4-ed30-4c2a-b5cb-8ff3aaaf9b91%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="2f9f6-119">指定与标记相关的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="2f9f6-119">Specifies the properties and operations related to flagging.</span></span>
    
<span data-ttu-id="2f9f6-120">[[MS-OXORMDR]](https://msdn.microsoft.com/library/5454ebcc-e5d1-4da8-a598-d393b101caab%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="2f9f6-120">[[MS-OXORMDR]](https://msdn.microsoft.com/library/5454ebcc-e5d1-4da8-a598-d393b101caab%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="2f9f6-121">指定电子邮件和其他对象提醒的属性和交互模型。</span><span class="sxs-lookup"><span data-stu-id="2f9f6-121">Specifies the properties and the interaction model for email and other object reminders.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="2f9f6-122">头文件</span><span class="sxs-lookup"><span data-stu-id="2f9f6-122">Header files</span></span>

<span data-ttu-id="2f9f6-123">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="2f9f6-123">Mapidefs.h</span></span>
  
> <span data-ttu-id="2f9f6-124">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="2f9f6-124">Provides data type definitions.</span></span>
    
<span data-ttu-id="2f9f6-125">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="2f9f6-125">Mapitags.h</span></span>
  
> <span data-ttu-id="2f9f6-126">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="2f9f6-126">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="2f9f6-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2f9f6-127">See also</span></span>



[<span data-ttu-id="2f9f6-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="2f9f6-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="2f9f6-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="2f9f6-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="2f9f6-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="2f9f6-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="2f9f6-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="2f9f6-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

