---
title: PidTagBodyHtml 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagBodyHtml
api_type:
- HeaderDef
ms.assetid: 93b9215a-5900-411c-a0ae-6bba62cd5a1e
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 6ed59228ee06a1d3e362115a99bf4b859dfeb698
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32359043"
---
# <a name="pidtagbodyhtml-canonical-property"></a><span data-ttu-id="55106-103">PidTagBodyHtml 规范属性</span><span class="sxs-lookup"><span data-stu-id="55106-103">PidTagBodyHtml Canonical Property</span></span>

  
  
<span data-ttu-id="55106-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="55106-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="55106-105">包含超文本标记 (HTML) 版本的邮件文本。</span><span class="sxs-lookup"><span data-stu-id="55106-105">Contains the Hypertext Markup Language (HTML) version of the message text.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="55106-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="55106-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="55106-107">PR_BODY_HTML、PR_BODY_HTML_A、PR_BODY_HTML_W</span><span class="sxs-lookup"><span data-stu-id="55106-107">PR_BODY_HTML, PR_BODY_HTML_A, PR_BODY_HTML_W</span></span>  <br/> |
|<span data-ttu-id="55106-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="55106-108">Identifier:</span></span>  <br/> |<span data-ttu-id="55106-109">0x1013</span><span class="sxs-lookup"><span data-stu-id="55106-109">0x1013</span></span>  <br/> |
|<span data-ttu-id="55106-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="55106-110">Data type:</span></span>  <br/> |<span data-ttu-id="55106-111">PT_UNICODE、PT_STRING8</span><span class="sxs-lookup"><span data-stu-id="55106-111">PT_UNICODE, PT_STRING8</span></span>  <br/> |
|<span data-ttu-id="55106-112">区域：</span><span class="sxs-lookup"><span data-stu-id="55106-112">Area:</span></span>  <br/> |<span data-ttu-id="55106-113">常规消息</span><span class="sxs-lookup"><span data-stu-id="55106-113">General messaging</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="55106-114">备注</span><span class="sxs-lookup"><span data-stu-id="55106-114">Remarks</span></span>

<span data-ttu-id="55106-115">这些属性包含的邮件文本与[PidTagBodyContentLocation](pidtagbodycontentlocation-canonical-property.md) PR_BODY_CONTENT_LOCATION (相同，) HTML 格式。 </span><span class="sxs-lookup"><span data-stu-id="55106-115">These properties contain the same message text as the **PR_BODY_CONTENT_LOCATION** ([PidTagBodyContentLocation](pidtagbodycontentlocation-canonical-property.md)), but in HTML.</span></span> 
  
<span data-ttu-id="55106-116">支持 HTML 的邮件存储通过在其 STORE_HTML_OK [PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md) PR_STORE_SUPPORT_MASK (标记来指示) 。  </span><span class="sxs-lookup"><span data-stu-id="55106-116">A message store that supports HTML indicates this by setting the **STORE_HTML_OK** flag in its **PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)).</span></span> 
  
 <span data-ttu-id="55106-117">**请注意\*\*\*\*STORE_HTML_OK** Microsoft® Exchange 2000 Server 及更早版本中未定义 Mapidefs.h 版本。</span><span class="sxs-lookup"><span data-stu-id="55106-117">**Note** **STORE_HTML_OK** is not defined in versions of Mapidefs.h included with Microsoft® Exchange 2000 Server and earlier.</span></span> <span data-ttu-id="55106-118">如果 **STORE_HTML_OK** 未定义，请改为使用0x00010000值。</span><span class="sxs-lookup"><span data-stu-id="55106-118">If **STORE_HTML_OK** is undefined, use the value 0x00010000 instead.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="55106-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="55106-119">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="55106-120">协议规范</span><span class="sxs-lookup"><span data-stu-id="55106-120">Protocol specifications</span></span>

<span data-ttu-id="55106-121">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="55106-121">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="55106-122">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="55106-122">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="55106-123">[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="55106-123">[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="55106-124">处理邮件和附件对象。</span><span class="sxs-lookup"><span data-stu-id="55106-124">Handles message and attachment objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="55106-125">头文件</span><span class="sxs-lookup"><span data-stu-id="55106-125">Header files</span></span>

<span data-ttu-id="55106-126">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="55106-126">Mapidefs.h</span></span>
  
> <span data-ttu-id="55106-127">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="55106-127">Provides data type definitions.</span></span>
    
<span data-ttu-id="55106-128">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="55106-128">Mapitags.h</span></span>
  
> <span data-ttu-id="55106-129">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="55106-129">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="55106-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="55106-130">See also</span></span>



[<span data-ttu-id="55106-131">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="55106-131">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="55106-132">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="55106-132">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="55106-133">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="55106-133">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="55106-134">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="55106-134">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

