---
title: PidNameKeywords 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidNameKeywords
api_type:
- COM
ms.assetid: bcc0cda0-02bc-49a5-9fb9-850b4c2867c1
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: caa337541b45c2cb602f0848769b3b07028ea0fd
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22590538"
---
# <a name="pidnamekeywords-canonical-property"></a><span data-ttu-id="1523c-103">PidNameKeywords 规范属性</span><span class="sxs-lookup"><span data-stu-id="1523c-103">PidNameKeywords Canonical Property</span></span>

  
  
<span data-ttu-id="1523c-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="1523c-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="1523c-105">包含关键字或 message 对象的类别。</span><span class="sxs-lookup"><span data-stu-id="1523c-105">Contains keywords or categories for the message object.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="1523c-106">友好名称：</span><span class="sxs-lookup"><span data-stu-id="1523c-106">Friendly names:</span></span>  <br/> |<span data-ttu-id="1523c-107">无</span><span class="sxs-lookup"><span data-stu-id="1523c-107">None</span></span>  <br/> |
|<span data-ttu-id="1523c-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="1523c-108">Property set:</span></span>  <br/> |<span data-ttu-id="1523c-109">PS_PUBLIC_STRINGS</span><span class="sxs-lookup"><span data-stu-id="1523c-109">PS_PUBLIC_STRINGS</span></span>  <br/> |
|<span data-ttu-id="1523c-110">属性名称：</span><span class="sxs-lookup"><span data-stu-id="1523c-110">Property name:</span></span>  <br/> |<span data-ttu-id="1523c-111">Keywords</span><span class="sxs-lookup"><span data-stu-id="1523c-111">Keywords</span></span>  <br/> |
|<span data-ttu-id="1523c-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="1523c-112">Data type:</span></span>  <br/> |<span data-ttu-id="1523c-113">PT_MV_UNICODE</span><span class="sxs-lookup"><span data-stu-id="1523c-113">PT_MV_UNICODE</span></span>  <br/> |
|<span data-ttu-id="1523c-114">区域：</span><span class="sxs-lookup"><span data-stu-id="1523c-114">Area:</span></span>  <br/> |<span data-ttu-id="1523c-115">常规消息</span><span class="sxs-lookup"><span data-stu-id="1523c-115">General messaging</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="1523c-116">注解</span><span class="sxs-lookup"><span data-stu-id="1523c-116">Remarks</span></span>

<span data-ttu-id="1523c-117">多字符串值，该值指定的类别的消息对象，在此属性多值字符串，每个字符串的长度必须少于 256。</span><span class="sxs-lookup"><span data-stu-id="1523c-117">A multi-string value that specifies the categories for a message object, the length of each string within this property multi-value string, must be less than 256.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="1523c-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="1523c-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="1523c-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="1523c-119">Protocol specifications</span></span>

<span data-ttu-id="1523c-120">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="1523c-120">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="1523c-121">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="1523c-121">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="1523c-122">[[MS OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="1523c-122">[[MS-OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="1523c-123">处理邮件和附件的对象。</span><span class="sxs-lookup"><span data-stu-id="1523c-123">Handles message and attachment objects.</span></span>
    
<span data-ttu-id="1523c-124">[[MS OXODOC]](http://msdn.microsoft.com/library/103007c8-5066-4bed-84e3-4465907af098%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="1523c-124">[[MS-OXODOC]](http://msdn.microsoft.com/library/103007c8-5066-4bed-84e3-4465907af098%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="1523c-125">指定的属性和允许对文档的操作。</span><span class="sxs-lookup"><span data-stu-id="1523c-125">Specifies the properties and operations that are permissible on documents.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="1523c-126">头文件</span><span class="sxs-lookup"><span data-stu-id="1523c-126">Header files</span></span>

<span data-ttu-id="1523c-127">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="1523c-127">Mapidefs.h</span></span>
  
> <span data-ttu-id="1523c-128">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="1523c-128">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="1523c-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1523c-129">See also</span></span>



[<span data-ttu-id="1523c-130">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="1523c-130">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="1523c-131">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="1523c-131">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="1523c-132">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="1523c-132">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="1523c-133">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="1523c-133">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

