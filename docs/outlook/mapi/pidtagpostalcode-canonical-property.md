---
title: PidTagPostalCode 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagPostalCode
api_type:
- COM
ms.assetid: dd8e04b3-8959-4df4-ba2c-f6371180929b
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: e6e03d6461a9f12fb4f7bad2058cd3a8c0f57044
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778038"
---
# <a name="pidtagpostalcode-canonical-property"></a><span data-ttu-id="4ffbd-103">PidTagPostalCode 规范属性</span><span class="sxs-lookup"><span data-stu-id="4ffbd-103">PidTagPostalCode Canonical Property</span></span>

  
  
<span data-ttu-id="4ffbd-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="4ffbd-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="4ffbd-105">包含收信人的邮政地址的邮政编码。</span><span class="sxs-lookup"><span data-stu-id="4ffbd-105">Contains the postal code for the recipient's postal address.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="4ffbd-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="4ffbd-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="4ffbd-107">PR_POSTAL_CODE、 PR_POSTAL_CODE_A、 PR_POSTAL_CODE_W、 PR_BUSINESS_ADDRESS_POSTAL_CODE、 PR_BUSINESS_ADDRESS_POSTAL_CODE_A、 PR_BUSINESS_ADDRESS_POSTAL_CODE_W</span><span class="sxs-lookup"><span data-stu-id="4ffbd-107">PR_POSTAL_CODE, PR_POSTAL_CODE_A, PR_POSTAL_CODE_W, PR_BUSINESS_ADDRESS_POSTAL_CODE, PR_BUSINESS_ADDRESS_POSTAL_CODE_A, PR_BUSINESS_ADDRESS_POSTAL_CODE_W</span></span>  <br/> |
|<span data-ttu-id="4ffbd-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="4ffbd-108">Identifier:</span></span>  <br/> |<span data-ttu-id="4ffbd-109">0x3A2A</span><span class="sxs-lookup"><span data-stu-id="4ffbd-109">0x3A2A</span></span>  <br/> |
|<span data-ttu-id="4ffbd-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="4ffbd-110">Data type:</span></span>  <br/> |<span data-ttu-id="4ffbd-111">PT_UNICODE PT_STRING8</span><span class="sxs-lookup"><span data-stu-id="4ffbd-111">PT_UNICODE, PT_STRING8</span></span>  <br/> |
|<span data-ttu-id="4ffbd-112">区域：</span><span class="sxs-lookup"><span data-stu-id="4ffbd-112">Area:</span></span>  <br/> |<span data-ttu-id="4ffbd-113">MAPI 邮件用户</span><span class="sxs-lookup"><span data-stu-id="4ffbd-113">MAPI mail user</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="4ffbd-114">说明</span><span class="sxs-lookup"><span data-stu-id="4ffbd-114">Remarks</span></span>

<span data-ttu-id="4ffbd-115">这些属性提供标识和访问收件人的信息。</span><span class="sxs-lookup"><span data-stu-id="4ffbd-115">These properties provide identification and access information for a recipient.</span></span> <span data-ttu-id="4ffbd-116">它们是按收件人和组织定义的。</span><span class="sxs-lookup"><span data-stu-id="4ffbd-116">They are defined by the recipient and their organization.</span></span> 
  
<span data-ttu-id="4ffbd-117">特定于收件人的国家/地区的邮政编码。</span><span class="sxs-lookup"><span data-stu-id="4ffbd-117">The postal code is specific to the recipient's country/region.</span></span> <span data-ttu-id="4ffbd-118">在美国，此属性包含邮政编码。</span><span class="sxs-lookup"><span data-stu-id="4ffbd-118">In the United States of America, this property contains the ZIP code.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="4ffbd-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="4ffbd-119">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="4ffbd-120">协议规范</span><span class="sxs-lookup"><span data-stu-id="4ffbd-120">Protocol specifications</span></span>

<span data-ttu-id="4ffbd-121">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="4ffbd-121">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="4ffbd-122">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="4ffbd-122">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="4ffbd-123">[[MS OXOCNTC]](http://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="4ffbd-123">[[MS-OXOCNTC]](http://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="4ffbd-124">指定的属性和操作所允许的联系人和个人通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="4ffbd-124">Specifies the properties and operations that are permissible for contacts and personal distribution lists.</span></span>
    
<span data-ttu-id="4ffbd-125">[[MS OXOABK]](http://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="4ffbd-125">[[MS-OXOABK]](http://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="4ffbd-126">指定的属性和用户、 联系人、 组和资源的操作列表。</span><span class="sxs-lookup"><span data-stu-id="4ffbd-126">Specifies the properties and operations for lists of users, contacts, groups, and resources.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="4ffbd-127">头文件</span><span class="sxs-lookup"><span data-stu-id="4ffbd-127">Header files</span></span>

<span data-ttu-id="4ffbd-128">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="4ffbd-128">Mapidefs.h</span></span>
  
> <span data-ttu-id="4ffbd-129">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="4ffbd-129">Provides data type definitions.</span></span>
    
<span data-ttu-id="4ffbd-130">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="4ffbd-130">Mapitags.h</span></span>
  
> <span data-ttu-id="4ffbd-131">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="4ffbd-131">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="4ffbd-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4ffbd-132">See also</span></span>



[<span data-ttu-id="4ffbd-133">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="4ffbd-133">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="4ffbd-134">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="4ffbd-134">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="4ffbd-135">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="4ffbd-135">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="4ffbd-136">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="4ffbd-136">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

