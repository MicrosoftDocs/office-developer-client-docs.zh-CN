---
title: PidTagAttachTransportName 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagAttachTransportName
api_type:
- HeaderDef
ms.assetid: 701fca52-0f96-4019-80cd-c0ccd059ff9b
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 3899f7000bfa1365228864d97b4410833b774bed
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22570779"
---
# <a name="pidtagattachtransportname-canonical-property"></a><span data-ttu-id="be2bb-103">PidTagAttachTransportName 规范属性</span><span class="sxs-lookup"><span data-stu-id="be2bb-103">PidTagAttachTransportName Canonical Property</span></span>

  
  
<span data-ttu-id="be2bb-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="be2bb-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="be2bb-105">包含的修改，以便它可以与 TNEF 邮件相关联的附件文件的名称。</span><span class="sxs-lookup"><span data-stu-id="be2bb-105">Contains the name of an attachment file modified so that it can be associated with TNEF messages.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="be2bb-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="be2bb-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="be2bb-107">PR_ATTACH_TRANSPORT_NAME，PR_ATTACH_TRANSPORT_NAME_A，PR_ATTACH_TRANSPORT_NAME_W</span><span class="sxs-lookup"><span data-stu-id="be2bb-107">PR_ATTACH_TRANSPORT_NAME, PR_ATTACH_TRANSPORT_NAME_A, PR_ATTACH_TRANSPORT_NAME_W</span></span>  <br/> |
|<span data-ttu-id="be2bb-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="be2bb-108">Identifier:</span></span>  <br/> |<span data-ttu-id="be2bb-109">0x370C</span><span class="sxs-lookup"><span data-stu-id="be2bb-109">0x370C</span></span>  <br/> |
|<span data-ttu-id="be2bb-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="be2bb-110">Data type:</span></span>  <br/> |<span data-ttu-id="be2bb-111">PT_STRING8 PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="be2bb-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="be2bb-112">区域：</span><span class="sxs-lookup"><span data-stu-id="be2bb-112">Area:</span></span>  <br/> |<span data-ttu-id="be2bb-113">邮件附件</span><span class="sxs-lookup"><span data-stu-id="be2bb-113">Message attachment</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="be2bb-114">注解</span><span class="sxs-lookup"><span data-stu-id="be2bb-114">Remarks</span></span>

<span data-ttu-id="be2bb-115">TNEF 和传输提供程序使用这些属性。</span><span class="sxs-lookup"><span data-stu-id="be2bb-115">TNEF and the transport provider use these properties.</span></span> <span data-ttu-id="be2bb-116">他们通常是不供客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="be2bb-116">They are usually not available to client applications.</span></span> 
  
<span data-ttu-id="be2bb-117">通常由 TNEF 使用这些属性，当基础消息系统不支持提供的文件名。</span><span class="sxs-lookup"><span data-stu-id="be2bb-117">These properties are commonly used by TNEF when the underlying messaging system does not support the supplied filenames.</span></span> <span data-ttu-id="be2bb-118">例如，它们用于当用户附加具有相同名称，例如名为配置的五个文件的多个文件。系统。</span><span class="sxs-lookup"><span data-stu-id="be2bb-118">For example, they are used when the user attaches multiple files with the same name, such as five files named CONFIG.SYS.</span></span> <span data-ttu-id="be2bb-119">传输提供程序必须修改以确保它们都是唯一的名称。</span><span class="sxs-lookup"><span data-stu-id="be2bb-119">The transport provider must modify the names to make sure they are unique.</span></span> <span data-ttu-id="be2bb-120">每个已修改的名称显示在其附件**PR_ATTACH_TRANSPORT_NAME**和关联的属性。</span><span class="sxs-lookup"><span data-stu-id="be2bb-120">Each modified name appears in its attachment's **PR_ATTACH_TRANSPORT_NAME** and associated properties.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="be2bb-121">相关资源</span><span class="sxs-lookup"><span data-stu-id="be2bb-121">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="be2bb-122">协议规范</span><span class="sxs-lookup"><span data-stu-id="be2bb-122">Protocol specifications</span></span>

<span data-ttu-id="be2bb-123">[[MS OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="be2bb-123">[[MS-OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="be2bb-124">处理邮件和附件的对象。</span><span class="sxs-lookup"><span data-stu-id="be2bb-124">Handles message and attachment objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="be2bb-125">头文件</span><span class="sxs-lookup"><span data-stu-id="be2bb-125">Header files</span></span>

<span data-ttu-id="be2bb-126">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="be2bb-126">Mapidefs.h</span></span>
  
> <span data-ttu-id="be2bb-127">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="be2bb-127">Provides data type definitions.</span></span>
    
<span data-ttu-id="be2bb-128">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="be2bb-128">Mapitags.h</span></span>
  
> <span data-ttu-id="be2bb-129">包含列为相关属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="be2bb-129">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="be2bb-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="be2bb-130">See also</span></span>



[<span data-ttu-id="be2bb-131">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="be2bb-131">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="be2bb-132">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="be2bb-132">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="be2bb-133">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="be2bb-133">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="be2bb-134">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="be2bb-134">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

