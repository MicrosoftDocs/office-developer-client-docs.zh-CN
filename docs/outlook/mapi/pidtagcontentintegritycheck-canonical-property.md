---
title: PidTagContentIntegrityCheck 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagContentIntegrityCheck
api_type:
- HeaderDef
ms.assetid: c7f10b8a-6b20-44cf-bde6-8d2b711c1c14
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 30ed8053c9c3d77f4831da37ddd2456ad0564a5a
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33415724"
---
# <a name="pidtagcontentintegritycheck-canonical-property"></a><span data-ttu-id="eecdb-103">PidTagContentIntegrityCheck 规范属性</span><span class="sxs-lookup"><span data-stu-id="eecdb-103">PidTagContentIntegrityCheck Canonical Property</span></span>

  
  
<span data-ttu-id="eecdb-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="eecdb-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="eecdb-105">包含一个 ASN.1 内容完整性检查值，它允许邮件发件人保护邮件内容，防止向未经授权的收件人泄露。</span><span class="sxs-lookup"><span data-stu-id="eecdb-105">Contains an ASN.1 content integrity check value that allows a message sender to protect message content from disclosure to unauthorized recipients.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="eecdb-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="eecdb-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="eecdb-107">PR_CONTENT_INTEGRITY_CHECK</span><span class="sxs-lookup"><span data-stu-id="eecdb-107">PR_CONTENT_INTEGRITY_CHECK</span></span>  <br/> |
|<span data-ttu-id="eecdb-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="eecdb-108">Identifier:</span></span>  <br/> |<span data-ttu-id="eecdb-109">0x0C00</span><span class="sxs-lookup"><span data-stu-id="eecdb-109">0x0C00</span></span>  <br/> |
|<span data-ttu-id="eecdb-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="eecdb-110">Data type:</span></span>  <br/> |<span data-ttu-id="eecdb-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="eecdb-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="eecdb-112">区域：</span><span class="sxs-lookup"><span data-stu-id="eecdb-112">Area:</span></span>  <br/> |<span data-ttu-id="eecdb-113">Exchange</span><span class="sxs-lookup"><span data-stu-id="eecdb-113">Exchange</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="eecdb-114">备注</span><span class="sxs-lookup"><span data-stu-id="eecdb-114">Remarks</span></span>

<span data-ttu-id="eecdb-115">此属性提供不拒绝邮件内容。</span><span class="sxs-lookup"><span data-stu-id="eecdb-115">This property provides for non-repudiation of message content.</span></span> <span data-ttu-id="eecdb-116">结合[PidTagMessageToken PR_MESSAGE_TOKEN (PidTagMessageToken](pidtagmessagetoken-canonical-property.md)) ，它可确保邮件的内容到达其目标位置不变。 </span><span class="sxs-lookup"><span data-stu-id="eecdb-116">In conjunction with **PR_MESSAGE_TOKEN** ([PidTagMessageToken](pidtagmessagetoken-canonical-property.md)), it ensures that the content of a message arrives at its destination unchanged.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="eecdb-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="eecdb-117">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="eecdb-118">头文件</span><span class="sxs-lookup"><span data-stu-id="eecdb-118">Header files</span></span>

<span data-ttu-id="eecdb-119">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="eecdb-119">Mapidefs.h</span></span>
  
> <span data-ttu-id="eecdb-120">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="eecdb-120">Provides data type definitions.</span></span>
    
<span data-ttu-id="eecdb-121">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="eecdb-121">Mapitags.h</span></span>
  
> <span data-ttu-id="eecdb-122">包含作为关联属性列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="eecdb-122">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="eecdb-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="eecdb-123">See also</span></span>



[<span data-ttu-id="eecdb-124">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="eecdb-124">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="eecdb-125">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="eecdb-125">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="eecdb-126">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="eecdb-126">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="eecdb-127">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="eecdb-127">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

