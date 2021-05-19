---
title: PidTagPostalAddress 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagPostalAddress
api_type:
- COM
ms.assetid: cf400713-3b42-4ee7-9dea-d52b8bf03ac3
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: f6f67572914ae7dbcc6e6d6b992fb2f8ee463117
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32338694"
---
# <a name="pidtagpostaladdress-canonical-property"></a><span data-ttu-id="57c49-103">PidTagPostalAddress 规范属性</span><span class="sxs-lookup"><span data-stu-id="57c49-103">PidTagPostalAddress Canonical Property</span></span>

  
  
<span data-ttu-id="57c49-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="57c49-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="57c49-105">包含收件人的邮寄地址。</span><span class="sxs-lookup"><span data-stu-id="57c49-105">Contains the recipient's postal address.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="57c49-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="57c49-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="57c49-107">PR_POSTAL_ADDRESS、PR_POSTAL_ADDRESS_A、PR_POSTAL_ADDRESS_W</span><span class="sxs-lookup"><span data-stu-id="57c49-107">PR_POSTAL_ADDRESS, PR_POSTAL_ADDRESS_A, PR_POSTAL_ADDRESS_W</span></span>  <br/> |
|<span data-ttu-id="57c49-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="57c49-108">Identifier:</span></span>  <br/> |<span data-ttu-id="57c49-109">0x3A15</span><span class="sxs-lookup"><span data-stu-id="57c49-109">0x3A15</span></span>  <br/> |
|<span data-ttu-id="57c49-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="57c49-110">Data type:</span></span>  <br/> |<span data-ttu-id="57c49-111">PT_STRING8、PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="57c49-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="57c49-112">区域：</span><span class="sxs-lookup"><span data-stu-id="57c49-112">Area:</span></span>  <br/> |<span data-ttu-id="57c49-113">MAPI 邮件用户</span><span class="sxs-lookup"><span data-stu-id="57c49-113">MAPI mail user</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="57c49-114">备注</span><span class="sxs-lookup"><span data-stu-id="57c49-114">Remarks</span></span>

<span data-ttu-id="57c49-115">这些属性为收件人提供标识和访问信息。</span><span class="sxs-lookup"><span data-stu-id="57c49-115">These properties provide identification and access information for a recipient.</span></span> <span data-ttu-id="57c49-116">它们由收件人和收件人的组织定义。</span><span class="sxs-lookup"><span data-stu-id="57c49-116">They are defined by the recipient and the recipient's organization.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="57c49-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="57c49-117">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="57c49-118">协议规范</span><span class="sxs-lookup"><span data-stu-id="57c49-118">Protocol specifications</span></span>

<span data-ttu-id="57c49-119">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="57c49-119">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="57c49-120">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="57c49-120">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="57c49-121">[[MS-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="57c49-121">[[MS-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="57c49-122">指定用户、联系人、组和资源的列表的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="57c49-122">Specifies the properties and operations for lists of users, contacts, groups, and resources.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="57c49-123">头文件</span><span class="sxs-lookup"><span data-stu-id="57c49-123">Header files</span></span>

<span data-ttu-id="57c49-124">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="57c49-124">Mapidefs.h</span></span>
  
> <span data-ttu-id="57c49-125">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="57c49-125">Provides data type definitions.</span></span>
    
<span data-ttu-id="57c49-126">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="57c49-126">Mapitags.h</span></span>
  
> <span data-ttu-id="57c49-127">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="57c49-127">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="57c49-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="57c49-128">See also</span></span>



[<span data-ttu-id="57c49-129">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="57c49-129">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="57c49-130">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="57c49-130">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="57c49-131">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="57c49-131">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="57c49-132">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="57c49-132">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

