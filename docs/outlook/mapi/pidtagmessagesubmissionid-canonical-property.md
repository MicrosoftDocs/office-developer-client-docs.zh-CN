---
title: PidTagMessageSubmissionId 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagMessageSubmissionId
api_type:
- HeaderDef
ms.assetid: 0a799fe5-04e2-4e1d-b0cd-9bdd2577d299
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 3a26a8483e584ccc5cf9f33e0dbd75f379c01633
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22569664"
---
# <a name="pidtagmessagesubmissionid-canonical-property"></a><span data-ttu-id="abec2-103">PidTagMessageSubmissionId 规范属性</span><span class="sxs-lookup"><span data-stu-id="abec2-103">PidTagMessageSubmissionId Canonical Property</span></span>

  
  
<span data-ttu-id="abec2-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="abec2-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="abec2-105">包含的邮件传输代理 (MTA) 的邮件传输系统 (MTS) 标识符。</span><span class="sxs-lookup"><span data-stu-id="abec2-105">Contains a message transfer system (MTS) identifier for the message transfer agent (MTA).</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="abec2-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="abec2-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="abec2-107">PR_MESSAGE_SUBMISSION_ID</span><span class="sxs-lookup"><span data-stu-id="abec2-107">PR_MESSAGE_SUBMISSION_ID</span></span>  <br/> |
|<span data-ttu-id="abec2-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="abec2-108">Identifier:</span></span>  <br/> |<span data-ttu-id="abec2-109">0x0047</span><span class="sxs-lookup"><span data-stu-id="abec2-109">0x0047</span></span>  <br/> |
|<span data-ttu-id="abec2-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="abec2-110">Data type:</span></span>  <br/> |<span data-ttu-id="abec2-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="abec2-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="abec2-112">区域：</span><span class="sxs-lookup"><span data-stu-id="abec2-112">Area:</span></span>  <br/> |<span data-ttu-id="abec2-113">电子邮件</span><span class="sxs-lookup"><span data-stu-id="abec2-113">Email</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="abec2-114">注解</span><span class="sxs-lookup"><span data-stu-id="abec2-114">Remarks</span></span>

<span data-ttu-id="abec2-115">此属性返回的邮件提交的成功完成后 MTA。</span><span class="sxs-lookup"><span data-stu-id="abec2-115">This property is returned by the MTA upon successful completion of message submission.</span></span> <span data-ttu-id="abec2-116">有关此消息，如请求取消 MTA 与任何将来联系人使用此属性中 MTS 标识符。</span><span class="sxs-lookup"><span data-stu-id="abec2-116">Any future contact with the MTA regarding this message, such as requesting cancellation, uses the MTS identifier in this property.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="abec2-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="abec2-117">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="abec2-118">协议规范</span><span class="sxs-lookup"><span data-stu-id="abec2-118">Protocol specifications</span></span>

<span data-ttu-id="abec2-119">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="abec2-119">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="abec2-120">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="abec2-120">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="abec2-121">[[MS OXTNEF]](http://msdn.microsoft.com/library/1f0544d7-30b7-4194-b58f-adc82f3763bb%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="abec2-121">[[MS-OXTNEF]](http://msdn.microsoft.com/library/1f0544d7-30b7-4194-b58f-adc82f3763bb%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="abec2-122">进行编码和解码为有效的流表示形式的消息和附件对象。</span><span class="sxs-lookup"><span data-stu-id="abec2-122">Encodes and decodes message and attachment objects to an efficient stream representation.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="abec2-123">头文件</span><span class="sxs-lookup"><span data-stu-id="abec2-123">Header files</span></span>

<span data-ttu-id="abec2-124">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="abec2-124">Mapidefs.h</span></span>
  
> <span data-ttu-id="abec2-125">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="abec2-125">Provides data type definitions.</span></span>
    
<span data-ttu-id="abec2-126">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="abec2-126">Mapitags.h</span></span>
  
> <span data-ttu-id="abec2-127">包含列为相关属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="abec2-127">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="abec2-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="abec2-128">See also</span></span>



[<span data-ttu-id="abec2-129">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="abec2-129">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="abec2-130">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="abec2-130">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="abec2-131">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="abec2-131">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="abec2-132">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="abec2-132">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

