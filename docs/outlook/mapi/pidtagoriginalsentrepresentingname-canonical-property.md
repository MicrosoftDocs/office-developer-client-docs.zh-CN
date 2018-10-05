---
title: PidTagOriginalSentRepresentingName 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagOriginalSentRepresentingName
api_type:
- COM
ms.assetid: 1be45cad-05a2-44cb-8c3d-7f6ac092fa0d
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 771a7c9cdf37a94875c881d8d7e8fd292893a0ba
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25401480"
---
# <a name="pidtagoriginalsentrepresentingname-canonical-property"></a><span data-ttu-id="80834-103">PidTagOriginalSentRepresentingName 规范属性</span><span class="sxs-lookup"><span data-stu-id="80834-103">PidTagOriginalSentRepresentingName Canonical Property</span></span>

  
  
<span data-ttu-id="80834-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="80834-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="80834-105">包含的名义原始邮件已发送的邮件用户的显示名称。</span><span class="sxs-lookup"><span data-stu-id="80834-105">Contains the display name of the messaging user on whose behalf the original message was sent.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="80834-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="80834-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="80834-107">PR_ORIGINAL_SENT_REPRESENTING_NAME，PR_ORIGINAL_SENT_REPRESENTING_NAME_A，PR_ORIGINAL_SENT_REPRESENTING_NAME_W</span><span class="sxs-lookup"><span data-stu-id="80834-107">PR_ORIGINAL_SENT_REPRESENTING_NAME, PR_ORIGINAL_SENT_REPRESENTING_NAME_A, PR_ORIGINAL_SENT_REPRESENTING_NAME_W</span></span>  <br/> |
|<span data-ttu-id="80834-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="80834-108">Identifier:</span></span>  <br/> |<span data-ttu-id="80834-109">0x005D</span><span class="sxs-lookup"><span data-stu-id="80834-109">0x005D</span></span>  <br/> |
|<span data-ttu-id="80834-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="80834-110">Data type:</span></span>  <br/> |<span data-ttu-id="80834-111">PT_STRING8 PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="80834-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="80834-112">区域：</span><span class="sxs-lookup"><span data-stu-id="80834-112">Area:</span></span>  <br/> |<span data-ttu-id="80834-113">常规消息</span><span class="sxs-lookup"><span data-stu-id="80834-113">General messaging</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="80834-114">说明</span><span class="sxs-lookup"><span data-stu-id="80834-114">Remarks</span></span>

<span data-ttu-id="80834-115">原始表示邮件发件人的地址属性这些属性示例。</span><span class="sxs-lookup"><span data-stu-id="80834-115">These properties examples of the address properties for the original represented sender of a message.</span></span> <span data-ttu-id="80834-116">在对话的线程中使用它。</span><span class="sxs-lookup"><span data-stu-id="80834-116">It is used in a conversation thread.</span></span>
  
<span data-ttu-id="80834-117">发送一条消息，代表另一个客户端的客户端应用程序应将这些属性设置为在首次提交邮件**PR_SENT_REPRESENTING_NAME** ([PidTagSentRepresentingName](pidtagsentrepresentingname-canonical-property.md)) 属性的值。</span><span class="sxs-lookup"><span data-stu-id="80834-117">A client application sending a message on behalf of another client should set these properties to the value of the **PR_SENT_REPRESENTING_NAME** ([PidTagSentRepresentingName](pidtagsentrepresentingname-canonical-property.md)) property at the first submission of the message.</span></span> <span data-ttu-id="80834-118">设置后，它应永远不会更改。</span><span class="sxs-lookup"><span data-stu-id="80834-118">Once set, it should never be changed.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="80834-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="80834-119">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="80834-120">协议规范</span><span class="sxs-lookup"><span data-stu-id="80834-120">Protocol specifications</span></span>

<span data-ttu-id="80834-121">[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="80834-121">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="80834-122">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="80834-122">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="80834-123">[[MS OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="80834-123">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="80834-124">指定的属性和电子邮件消息对象在允许的操作。</span><span class="sxs-lookup"><span data-stu-id="80834-124">Specifies the properties and operations that are permissible on email message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="80834-125">头文件</span><span class="sxs-lookup"><span data-stu-id="80834-125">Header files</span></span>

<span data-ttu-id="80834-126">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="80834-126">Mapidefs.h</span></span>
  
> <span data-ttu-id="80834-127">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="80834-127">Provides data type definitions.</span></span>
    
<span data-ttu-id="80834-128">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="80834-128">Mapitags.h</span></span>
  
> <span data-ttu-id="80834-129">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="80834-129">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="80834-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="80834-130">See also</span></span>



[<span data-ttu-id="80834-131">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="80834-131">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="80834-132">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="80834-132">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="80834-133">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="80834-133">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="80834-134">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="80834-134">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

