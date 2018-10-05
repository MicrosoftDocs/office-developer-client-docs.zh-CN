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
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25387844"
---
# <a name="pidlidspamoriginalfolder-canonical-property"></a><span data-ttu-id="ec00d-103">PidLidSpamOriginalFolder 规范属性</span><span class="sxs-lookup"><span data-stu-id="ec00d-103">PidLidSpamOriginalFolder Canonical Property</span></span>

  
  
<span data-ttu-id="ec00d-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ec00d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ec00d-105">指示一条消息之前已在哪个文件夹而被筛选出到垃圾邮件文件夹。</span><span class="sxs-lookup"><span data-stu-id="ec00d-105">Indicates which folder a message was in before it was filtered into the junk email folder.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="ec00d-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="ec00d-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="ec00d-107">dispidSpamOriginalFolder</span><span class="sxs-lookup"><span data-stu-id="ec00d-107">dispidSpamOriginalFolder</span></span>  <br/> |
|<span data-ttu-id="ec00d-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="ec00d-108">Property set:</span></span>  <br/> |<span data-ttu-id="ec00d-109">PSETID_Common</span><span class="sxs-lookup"><span data-stu-id="ec00d-109">PSETID_Common</span></span>  <br/> |
|<span data-ttu-id="ec00d-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="ec00d-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="ec00d-111">0x0000859C</span><span class="sxs-lookup"><span data-stu-id="ec00d-111">0x0000859C</span></span>  <br/> |
|<span data-ttu-id="ec00d-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="ec00d-112">Data type:</span></span>  <br/> |<span data-ttu-id="ec00d-113">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="ec00d-113">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="ec00d-114">区域：</span><span class="sxs-lookup"><span data-stu-id="ec00d-114">Area:</span></span>  <br/> |<span data-ttu-id="ec00d-115">垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="ec00d-115">Spam</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="ec00d-116">说明</span><span class="sxs-lookup"><span data-stu-id="ec00d-116">Remarks</span></span>

<span data-ttu-id="ec00d-117">此属性的值是文件夹的包含邮件之前它已移动的**EntryID** 。</span><span class="sxs-lookup"><span data-stu-id="ec00d-117">The value of this property is the **EntryID** of the folder that contained the message before it was moved.</span></span> <span data-ttu-id="ec00d-118">邮件标记为垃圾邮件时，应设置该属性。</span><span class="sxs-lookup"><span data-stu-id="ec00d-118">This property should be set when a message is marked as spam.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="ec00d-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="ec00d-119">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="ec00d-120">协议规范</span><span class="sxs-lookup"><span data-stu-id="ec00d-120">Protocol specifications</span></span>

<span data-ttu-id="ec00d-121">[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="ec00d-121">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="ec00d-122">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="ec00d-122">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="ec00d-123">[[MS OXCSPAM]](https://msdn.microsoft.com/library/522f8587-4aed-4cd6-831b-40bd87862189%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="ec00d-123">[[MS-OXCSPAM]](https://msdn.microsoft.com/library/522f8587-4aed-4cd6-831b-40bd87862189%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="ec00d-124">允许处理的允许/阻止列表，并确定的垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="ec00d-124">Enables the handling of allow/block lists and the determination of junk email messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="ec00d-125">头文件</span><span class="sxs-lookup"><span data-stu-id="ec00d-125">Header files</span></span>

<span data-ttu-id="ec00d-126">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="ec00d-126">Mapidefs.h</span></span>
  
> <span data-ttu-id="ec00d-127">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="ec00d-127">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="ec00d-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ec00d-128">See also</span></span>



[<span data-ttu-id="ec00d-129">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="ec00d-129">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="ec00d-130">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="ec00d-130">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="ec00d-131">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="ec00d-131">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="ec00d-132">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="ec00d-132">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

