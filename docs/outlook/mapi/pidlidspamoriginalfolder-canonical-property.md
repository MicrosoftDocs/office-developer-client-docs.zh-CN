---
title: PidLidSpamOriginalFolder 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidSpamOriginalFolder
api_type:
- COM
ms.assetid: 45846fe3-7ab3-4019-98bb-fe615889c31c
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 561008782e7c1ffb8bc71cf4e3bc17befe69bbca
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32331554"
---
# <a name="pidlidspamoriginalfolder-canonical-property"></a><span data-ttu-id="7e14f-103">PidLidSpamOriginalFolder 规范属性</span><span class="sxs-lookup"><span data-stu-id="7e14f-103">PidLidSpamOriginalFolder Canonical Property</span></span>

  
  
<span data-ttu-id="7e14f-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7e14f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="7e14f-105">指示邮件在被筛选到 "垃圾邮件" 文件夹中之前的所在的文件夹。</span><span class="sxs-lookup"><span data-stu-id="7e14f-105">Indicates which folder a message was in before it was filtered into the junk email folder.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="7e14f-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="7e14f-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="7e14f-107">dispidSpamOriginalFolder</span><span class="sxs-lookup"><span data-stu-id="7e14f-107">dispidSpamOriginalFolder</span></span>  <br/> |
|<span data-ttu-id="7e14f-108">属性集:</span><span class="sxs-lookup"><span data-stu-id="7e14f-108">Property set:</span></span>  <br/> |<span data-ttu-id="7e14f-109">PSETID_Common</span><span class="sxs-lookup"><span data-stu-id="7e14f-109">PSETID_Common</span></span>  <br/> |
|<span data-ttu-id="7e14f-110">长 ID (盖子):</span><span class="sxs-lookup"><span data-stu-id="7e14f-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="7e14f-111">0x0000859C</span><span class="sxs-lookup"><span data-stu-id="7e14f-111">0x0000859C</span></span>  <br/> |
|<span data-ttu-id="7e14f-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="7e14f-112">Data type:</span></span>  <br/> |<span data-ttu-id="7e14f-113">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="7e14f-113">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="7e14f-114">区域：</span><span class="sxs-lookup"><span data-stu-id="7e14f-114">Area:</span></span>  <br/> |<span data-ttu-id="7e14f-115">垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="7e14f-115">Spam</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="7e14f-116">注解</span><span class="sxs-lookup"><span data-stu-id="7e14f-116">Remarks</span></span>

<span data-ttu-id="7e14f-117">此属性的值是在移动邮件之前包含邮件的文件夹的**EntryID** 。</span><span class="sxs-lookup"><span data-stu-id="7e14f-117">The value of this property is the **EntryID** of the folder that contained the message before it was moved.</span></span> <span data-ttu-id="7e14f-118">将邮件标记为垃圾邮件时, 应设置此属性。</span><span class="sxs-lookup"><span data-stu-id="7e14f-118">This property should be set when a message is marked as spam.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="7e14f-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="7e14f-119">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="7e14f-120">协议规范</span><span class="sxs-lookup"><span data-stu-id="7e14f-120">Protocol specifications</span></span>

<span data-ttu-id="7e14f-121">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="7e14f-121">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="7e14f-122">提供属性集定义和对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="7e14f-122">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="7e14f-123">[[毫秒-OXCSPAM]](https://msdn.microsoft.com/library/522f8587-4aed-4cd6-831b-40bd87862189%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="7e14f-123">[[MS-OXCSPAM]](https://msdn.microsoft.com/library/522f8587-4aed-4cd6-831b-40bd87862189%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="7e14f-124">启用对允许/阻止列表的处理以及确定垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="7e14f-124">Enables the handling of allow/block lists and the determination of junk email messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="7e14f-125">头文件</span><span class="sxs-lookup"><span data-stu-id="7e14f-125">Header files</span></span>

<span data-ttu-id="7e14f-126">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="7e14f-126">Mapidefs.h</span></span>
  
> <span data-ttu-id="7e14f-127">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="7e14f-127">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="7e14f-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7e14f-128">See also</span></span>



[<span data-ttu-id="7e14f-129">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="7e14f-129">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="7e14f-130">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="7e14f-130">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="7e14f-131">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="7e14f-131">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="7e14f-132">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="7e14f-132">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

