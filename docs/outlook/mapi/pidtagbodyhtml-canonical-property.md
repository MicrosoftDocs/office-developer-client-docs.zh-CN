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
ms.openlocfilehash: 19f0398d5e36cce13467a4fae86c4ea1d4019dd1
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777390"
---
# <a name="pidtagbodyhtml-canonical-property"></a><span data-ttu-id="3b74f-103">PidTagBodyHtml 规范属性</span><span class="sxs-lookup"><span data-stu-id="3b74f-103">PidTagBodyHtml Canonical Property</span></span>

  
  
<span data-ttu-id="3b74f-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="3b74f-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="3b74f-105">包含消息文本的超文本标记语言 (HTML) 版本。</span><span class="sxs-lookup"><span data-stu-id="3b74f-105">Contains the Hypertext Markup Language (HTML) version of the message text.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="3b74f-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="3b74f-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="3b74f-107">PR_BODY_HTML，PR_BODY_HTML_A，PR_BODY_HTML_W</span><span class="sxs-lookup"><span data-stu-id="3b74f-107">PR_BODY_HTML, PR_BODY_HTML_A, PR_BODY_HTML_W</span></span>  <br/> |
|<span data-ttu-id="3b74f-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="3b74f-108">Identifier:</span></span>  <br/> |<span data-ttu-id="3b74f-109">0x1013</span><span class="sxs-lookup"><span data-stu-id="3b74f-109">0x1013</span></span>  <br/> |
|<span data-ttu-id="3b74f-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="3b74f-110">Data type:</span></span>  <br/> |<span data-ttu-id="3b74f-111">PT_UNICODE PT_STRING8</span><span class="sxs-lookup"><span data-stu-id="3b74f-111">PT_UNICODE, PT_STRING8</span></span>  <br/> |
|<span data-ttu-id="3b74f-112">区域：</span><span class="sxs-lookup"><span data-stu-id="3b74f-112">Area:</span></span>  <br/> |<span data-ttu-id="3b74f-113">常规消息</span><span class="sxs-lookup"><span data-stu-id="3b74f-113">General messaging</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="3b74f-114">说明</span><span class="sxs-lookup"><span data-stu-id="3b74f-114">Remarks</span></span>

<span data-ttu-id="3b74f-115">这些属性包含相同的消息文本**PR_BODY_CONTENT_LOCATION** ([PidTagBodyContentLocation](pidtagbodycontentlocation-canonical-property.md))，但在 HTML。</span><span class="sxs-lookup"><span data-stu-id="3b74f-115">These properties contain the same message text as the **PR_BODY_CONTENT_LOCATION** ([PidTagBodyContentLocation](pidtagbodycontentlocation-canonical-property.md)), but in HTML.</span></span> 
  
<span data-ttu-id="3b74f-116">支持 HTML 的消息存储指示这可以通过在其**PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) 中设置**STORE_HTML_OK**标志。</span><span class="sxs-lookup"><span data-stu-id="3b74f-116">A message store that supports HTML indicates this by setting the **STORE_HTML_OK** flag in its **PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)).</span></span> 
  
 <span data-ttu-id="3b74f-117">**注释****STORE_HTML_OK** Mapidefs.h 包含使用 Microsoft® Exchange 2000 Server 或更早版本中未定义。</span><span class="sxs-lookup"><span data-stu-id="3b74f-117">**Note** **STORE_HTML_OK** is not defined in versions of Mapidefs.h included with Microsoft® Exchange 2000 Server and earlier.</span></span> <span data-ttu-id="3b74f-118">如果未定义**STORE_HTML_OK** ，改用 0x00010000 的值。</span><span class="sxs-lookup"><span data-stu-id="3b74f-118">If **STORE_HTML_OK** is undefined, use the value 0x00010000 instead.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="3b74f-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="3b74f-119">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="3b74f-120">协议规范</span><span class="sxs-lookup"><span data-stu-id="3b74f-120">Protocol specifications</span></span>

<span data-ttu-id="3b74f-121">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="3b74f-121">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="3b74f-122">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="3b74f-122">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="3b74f-123">[[MS OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="3b74f-123">[[MS-OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="3b74f-124">处理邮件和附件的对象。</span><span class="sxs-lookup"><span data-stu-id="3b74f-124">Handles message and attachment objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="3b74f-125">头文件</span><span class="sxs-lookup"><span data-stu-id="3b74f-125">Header files</span></span>

<span data-ttu-id="3b74f-126">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="3b74f-126">Mapidefs.h</span></span>
  
> <span data-ttu-id="3b74f-127">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="3b74f-127">Provides data type definitions.</span></span>
    
<span data-ttu-id="3b74f-128">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="3b74f-128">Mapitags.h</span></span>
  
> <span data-ttu-id="3b74f-129">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="3b74f-129">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="3b74f-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3b74f-130">See also</span></span>



[<span data-ttu-id="3b74f-131">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="3b74f-131">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="3b74f-132">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="3b74f-132">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="3b74f-133">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="3b74f-133">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="3b74f-134">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="3b74f-134">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

