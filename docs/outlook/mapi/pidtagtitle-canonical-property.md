---
title: PidTagTitle 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagTitle
api_type:
- COM
ms.assetid: f35bbcc3-15dd-40ab-9bf4-bdb21f95d464
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: c19a757b8adf474a3624f90a7cf19cc2308fa0d0
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22582264"
---
# <a name="pidtagtitle-canonical-property"></a><span data-ttu-id="70a40-103">PidTagTitle 规范属性</span><span class="sxs-lookup"><span data-stu-id="70a40-103">PidTagTitle Canonical Property</span></span>

  
  
<span data-ttu-id="70a40-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="70a40-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="70a40-105">包含收件人的职务。</span><span class="sxs-lookup"><span data-stu-id="70a40-105">Contains the recipient's job title.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="70a40-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="70a40-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="70a40-107">PR_TITLE，PR_TITLE_A，PR_TITLE_W</span><span class="sxs-lookup"><span data-stu-id="70a40-107">PR_TITLE, PR_TITLE_A, PR_TITLE_W</span></span>  <br/> |
|<span data-ttu-id="70a40-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="70a40-108">Identifier:</span></span>  <br/> |<span data-ttu-id="70a40-109">0x3A17</span><span class="sxs-lookup"><span data-stu-id="70a40-109">0x3A17</span></span>  <br/> |
|<span data-ttu-id="70a40-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="70a40-110">Data type:</span></span>  <br/> |<span data-ttu-id="70a40-111">PT_STRING8 PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="70a40-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="70a40-112">区域：</span><span class="sxs-lookup"><span data-stu-id="70a40-112">Area:</span></span>  <br/> |<span data-ttu-id="70a40-113">MAPI 邮件用户</span><span class="sxs-lookup"><span data-stu-id="70a40-113">MAPI mail user</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="70a40-114">注解</span><span class="sxs-lookup"><span data-stu-id="70a40-114">Remarks</span></span>

<span data-ttu-id="70a40-115">这些属性提供标识和访问收件人的信息。</span><span class="sxs-lookup"><span data-stu-id="70a40-115">These properties provide identification and access information for a recipient.</span></span> <span data-ttu-id="70a40-116">它们是按收件人和收件人的组织定义的。</span><span class="sxs-lookup"><span data-stu-id="70a40-116">They are defined by the recipient and the recipient's organization.</span></span> 
  
<span data-ttu-id="70a40-117">这些属性通常用于指示收件人的正式作业标题，例如高级程序员，而不是职业类，如程序员。</span><span class="sxs-lookup"><span data-stu-id="70a40-117">These properties are commonly used to indicate the recipient's formal job title, such as Senior Programmer, rather than occupational class, such as programmer.</span></span> <span data-ttu-id="70a40-118">它是通常不用于如先生"后缀"标题</span><span class="sxs-lookup"><span data-stu-id="70a40-118">It is not typically used for "suffix" titles such as Esq.</span></span> <span data-ttu-id="70a40-119">或 DD。</span><span class="sxs-lookup"><span data-stu-id="70a40-119">or DDS.</span></span>
  
<span data-ttu-id="70a40-120">常见的此属性的值包括： 管理控制器、 程序员 II、 关联教授和开发导致。</span><span class="sxs-lookup"><span data-stu-id="70a40-120">Common values for this property include: Managing Director, Programmer II, Associate Professor, and Development Lead.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="70a40-121">相关资源</span><span class="sxs-lookup"><span data-stu-id="70a40-121">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="70a40-122">协议规范</span><span class="sxs-lookup"><span data-stu-id="70a40-122">Protocol specifications</span></span>

<span data-ttu-id="70a40-123">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="70a40-123">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="70a40-124">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="70a40-124">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="70a40-125">[[MS OXOCNTC]](http://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="70a40-125">[[MS-OXOCNTC]](http://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="70a40-126">指定的属性和操作所允许的联系人和个人通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="70a40-126">Specifies the properties and operations that are permissible for contacts and personal distribution lists.</span></span>
    
<span data-ttu-id="70a40-127">[[MS OXOABK]](http://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="70a40-127">[[MS-OXOABK]](http://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="70a40-128">指定的属性和用户、 联系人、 组和资源的操作列表。</span><span class="sxs-lookup"><span data-stu-id="70a40-128">Specifies the properties and operations for lists of users, contacts, groups, and resources.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="70a40-129">头文件</span><span class="sxs-lookup"><span data-stu-id="70a40-129">Header files</span></span>

<span data-ttu-id="70a40-130">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="70a40-130">Mapidefs.h</span></span>
  
> <span data-ttu-id="70a40-131">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="70a40-131">Provides data type definitions.</span></span>
    
<span data-ttu-id="70a40-132">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="70a40-132">Mapitags.h</span></span>
  
> <span data-ttu-id="70a40-133">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="70a40-133">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="70a40-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="70a40-134">See also</span></span>



[<span data-ttu-id="70a40-135">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="70a40-135">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="70a40-136">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="70a40-136">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="70a40-137">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="70a40-137">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="70a40-138">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="70a40-138">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

