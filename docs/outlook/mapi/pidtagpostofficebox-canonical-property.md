---
title: PidTagPostOfficeBox 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagPostOfficeBox
api_type:
- COM
ms.assetid: 3c2968bb-9625-4ebe-a8a0-cce8ef1651f4
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: c56d6d1301f15596eeda8dd5361a236226431b06
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25382510"
---
# <a name="pidtagpostofficebox-canonical-property"></a><span data-ttu-id="0b19c-103">PidTagPostOfficeBox 规范属性</span><span class="sxs-lookup"><span data-stu-id="0b19c-103">PidTagPostOfficeBox Canonical Property</span></span>

  
  
<span data-ttu-id="0b19c-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="0b19c-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="0b19c-105">包含编号或收件人的邮箱的标识符。</span><span class="sxs-lookup"><span data-stu-id="0b19c-105">Contains the number or identifier of the recipient's post office box.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="0b19c-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="0b19c-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="0b19c-107">PR_POST_OFFICE_BOX、 PR_POST_OFFICE_BOX_A、 PR_POST_OFFICE_BOX_W、 PR_BUSINESS_ADDRESS_POST_OFFICE_BOX、 PR_BUSINESS_ADDRESS_POST_OFFICE_BOX_A、 PR_BUSINESS_ADDRESS_POST_OFFICE_BOX_W</span><span class="sxs-lookup"><span data-stu-id="0b19c-107">PR_POST_OFFICE_BOX, PR_POST_OFFICE_BOX_A, PR_POST_OFFICE_BOX_W, PR_BUSINESS_ADDRESS_POST_OFFICE_BOX, PR_BUSINESS_ADDRESS_POST_OFFICE_BOX_A, PR_BUSINESS_ADDRESS_POST_OFFICE_BOX_W</span></span>  <br/> |
|<span data-ttu-id="0b19c-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="0b19c-108">Identifier:</span></span>  <br/> |<span data-ttu-id="0b19c-109">0x3A2B</span><span class="sxs-lookup"><span data-stu-id="0b19c-109">0x3A2B</span></span>  <br/> |
|<span data-ttu-id="0b19c-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="0b19c-110">Data type:</span></span>  <br/> |<span data-ttu-id="0b19c-111">PT_STRING8 PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="0b19c-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="0b19c-112">区域：</span><span class="sxs-lookup"><span data-stu-id="0b19c-112">Area:</span></span>  <br/> |<span data-ttu-id="0b19c-113">MAPI 邮件用户</span><span class="sxs-lookup"><span data-stu-id="0b19c-113">MAPI mail user</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="0b19c-114">说明</span><span class="sxs-lookup"><span data-stu-id="0b19c-114">Remarks</span></span>

<span data-ttu-id="0b19c-115">这些属性提供标识和访问收件人的信息。</span><span class="sxs-lookup"><span data-stu-id="0b19c-115">These properties provide identification and access information for a recipient.</span></span> <span data-ttu-id="0b19c-116">它们是按收件人和组织定义的。</span><span class="sxs-lookup"><span data-stu-id="0b19c-116">They are defined by the recipient and their organization.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="0b19c-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="0b19c-117">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="0b19c-118">协议规范</span><span class="sxs-lookup"><span data-stu-id="0b19c-118">Protocol specifications</span></span>

<span data-ttu-id="0b19c-119">[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="0b19c-119">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="0b19c-120">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="0b19c-120">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="0b19c-121">[[MS OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="0b19c-121">[[MS-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="0b19c-122">指定的属性和操作所允许的联系人和个人通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="0b19c-122">Specifies the properties and operations that are permissible for contacts and personal distribution lists.</span></span>
    
<span data-ttu-id="0b19c-123">[[MS OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="0b19c-123">[[MS-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="0b19c-124">指定的属性和用户、 联系人、 组和资源的操作列表。</span><span class="sxs-lookup"><span data-stu-id="0b19c-124">Specifies the properties and operations for lists of users, contacts, groups, and resources.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="0b19c-125">头文件</span><span class="sxs-lookup"><span data-stu-id="0b19c-125">Header files</span></span>

<span data-ttu-id="0b19c-126">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="0b19c-126">Mapidefs.h</span></span>
  
> <span data-ttu-id="0b19c-127">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="0b19c-127">Provides data type definitions.</span></span>
    
<span data-ttu-id="0b19c-128">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="0b19c-128">Mapitags.h</span></span>
  
> <span data-ttu-id="0b19c-129">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="0b19c-129">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="0b19c-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0b19c-130">See also</span></span>



[<span data-ttu-id="0b19c-131">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="0b19c-131">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="0b19c-132">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="0b19c-132">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="0b19c-133">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="0b19c-133">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="0b19c-134">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="0b19c-134">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

