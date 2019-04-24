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
ms.openlocfilehash: 90e5b370dace12dbe529465259b8551516fda491
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32338057"
---
# <a name="pidnamekeywords-canonical-property"></a><span data-ttu-id="46898-103">PidNameKeywords 规范属性</span><span class="sxs-lookup"><span data-stu-id="46898-103">PidNameKeywords Canonical Property</span></span>

  
  
<span data-ttu-id="46898-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="46898-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="46898-105">包含 message 对象的关键字或类别。</span><span class="sxs-lookup"><span data-stu-id="46898-105">Contains keywords or categories for the message object.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="46898-106">友好名称:</span><span class="sxs-lookup"><span data-stu-id="46898-106">Friendly names:</span></span>  <br/> |<span data-ttu-id="46898-107">无</span><span class="sxs-lookup"><span data-stu-id="46898-107">None</span></span>  <br/> |
|<span data-ttu-id="46898-108">属性集:</span><span class="sxs-lookup"><span data-stu-id="46898-108">Property set:</span></span>  <br/> |<span data-ttu-id="46898-109">PS_PUBLIC_STRINGS</span><span class="sxs-lookup"><span data-stu-id="46898-109">PS_PUBLIC_STRINGS</span></span>  <br/> |
|<span data-ttu-id="46898-110">属性名称:</span><span class="sxs-lookup"><span data-stu-id="46898-110">Property name:</span></span>  <br/> |<span data-ttu-id="46898-111">关键字</span><span class="sxs-lookup"><span data-stu-id="46898-111">Keywords</span></span>  <br/> |
|<span data-ttu-id="46898-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="46898-112">Data type:</span></span>  <br/> |<span data-ttu-id="46898-113">PT_MV_UNICODE</span><span class="sxs-lookup"><span data-stu-id="46898-113">PT_MV_UNICODE</span></span>  <br/> |
|<span data-ttu-id="46898-114">区域：</span><span class="sxs-lookup"><span data-stu-id="46898-114">Area:</span></span>  <br/> |<span data-ttu-id="46898-115">常规邮件</span><span class="sxs-lookup"><span data-stu-id="46898-115">General messaging</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="46898-116">注解</span><span class="sxs-lookup"><span data-stu-id="46898-116">Remarks</span></span>

<span data-ttu-id="46898-117">指定邮件对象的类别的多字符串值 (此属性中的多值字符串中的每个字符串的长度) 必须小于256。</span><span class="sxs-lookup"><span data-stu-id="46898-117">A multi-string value that specifies the categories for a message object, the length of each string within this property multi-value string, must be less than 256.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="46898-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="46898-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="46898-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="46898-119">Protocol specifications</span></span>

<span data-ttu-id="46898-120">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="46898-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="46898-121">提供属性集定义和对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="46898-121">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="46898-122">[[毫秒-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="46898-122">[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="46898-123">处理邮件和附件对象。</span><span class="sxs-lookup"><span data-stu-id="46898-123">Handles message and attachment objects.</span></span>
    
<span data-ttu-id="46898-124">[[毫秒-OXODOC]](https://msdn.microsoft.com/library/103007c8-5066-4bed-84e3-4465907af098%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="46898-124">[[MS-OXODOC]](https://msdn.microsoft.com/library/103007c8-5066-4bed-84e3-4465907af098%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="46898-125">指定在文档中允许的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="46898-125">Specifies the properties and operations that are permissible on documents.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="46898-126">头文件</span><span class="sxs-lookup"><span data-stu-id="46898-126">Header files</span></span>

<span data-ttu-id="46898-127">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="46898-127">Mapidefs.h</span></span>
  
> <span data-ttu-id="46898-128">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="46898-128">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="46898-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="46898-129">See also</span></span>



[<span data-ttu-id="46898-130">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="46898-130">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="46898-131">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="46898-131">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="46898-132">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="46898-132">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="46898-133">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="46898-133">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

