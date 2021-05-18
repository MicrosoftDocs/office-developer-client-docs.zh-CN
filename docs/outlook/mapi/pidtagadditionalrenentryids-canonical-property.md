---
title: PidTagAdditionalRenEntryIds 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagAdditionalRenEntryIds
api_type:
- HeaderDef
ms.assetid: 8c6e7ca2-1824-4cca-bf69-3c1ea52727de
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 4984055d370f3f8ab617b11b2d834ba277ef105a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32282359"
---
# <a name="pidtagadditionalrenentryids-canonical-property"></a><span data-ttu-id="46d6a-103">PidTagAdditionalRenEntryIds 规范属性</span><span class="sxs-lookup"><span data-stu-id="46d6a-103">PidTagAdditionalRenEntryIds Canonical Property</span></span>

  
  
<span data-ttu-id="46d6a-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="46d6a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="46d6a-105">包含某些特殊文件夹的条目 ID。</span><span class="sxs-lookup"><span data-stu-id="46d6a-105">Contains the entry IDs of certain special folders.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="46d6a-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="46d6a-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="46d6a-107">PR_ADDITIONAL_REN_ENTRYIDS</span><span class="sxs-lookup"><span data-stu-id="46d6a-107">PR_ADDITIONAL_REN_ENTRYIDS</span></span>  <br/> |
|<span data-ttu-id="46d6a-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="46d6a-108">Identifier:</span></span>  <br/> |<span data-ttu-id="46d6a-109">0x36D8</span><span class="sxs-lookup"><span data-stu-id="46d6a-109">0x36D8</span></span>  <br/> |
|<span data-ttu-id="46d6a-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="46d6a-110">Data type:</span></span>  <br/> |<span data-ttu-id="46d6a-111">PT_MV_BINARY</span><span class="sxs-lookup"><span data-stu-id="46d6a-111">PT_MV_BINARY</span></span>  <br/> |
|<span data-ttu-id="46d6a-112">区域：</span><span class="sxs-lookup"><span data-stu-id="46d6a-112">Area:</span></span>  <br/> |<span data-ttu-id="46d6a-113">Outlook 应用程序</span><span class="sxs-lookup"><span data-stu-id="46d6a-113">Outlook application</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="46d6a-114">备注</span><span class="sxs-lookup"><span data-stu-id="46d6a-114">Remarks</span></span>

<span data-ttu-id="46d6a-115">此多值属性的前五个条目适用于以下特殊文件夹（如果它们存在于存储区中）：</span><span class="sxs-lookup"><span data-stu-id="46d6a-115">The first five entries of this multi-valued property apply to following special folders, if they exist in the store:</span></span>
  
<span data-ttu-id="46d6a-116">0 - 冲突文件夹</span><span class="sxs-lookup"><span data-stu-id="46d6a-116">0 - conflicts folder</span></span>
  
<span data-ttu-id="46d6a-117">1 - 同步问题文件夹</span><span class="sxs-lookup"><span data-stu-id="46d6a-117">1 - sync issues folder</span></span>
  
<span data-ttu-id="46d6a-118">2 - 本地故障文件夹</span><span class="sxs-lookup"><span data-stu-id="46d6a-118">2 - local failures folder</span></span>
  
<span data-ttu-id="46d6a-119">3 - 服务器故障文件夹</span><span class="sxs-lookup"><span data-stu-id="46d6a-119">3 - server failures folder</span></span>
  
<span data-ttu-id="46d6a-120">4 - 垃圾邮件文件夹</span><span class="sxs-lookup"><span data-stu-id="46d6a-120">4 - junk email folder</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="46d6a-121">相关资源</span><span class="sxs-lookup"><span data-stu-id="46d6a-121">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="46d6a-122">协议规范</span><span class="sxs-lookup"><span data-stu-id="46d6a-122">Protocol specifications</span></span>

<span data-ttu-id="46d6a-123">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="46d6a-123">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="46d6a-124">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="46d6a-124">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="46d6a-125">[[MS-OXOSFLD]](https://msdn.microsoft.com/library/a60e9c16-2ba8-424b-b60c-385a8a2837cb%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="46d6a-125">[[MS-OXOSFLD]](https://msdn.microsoft.com/library/a60e9c16-2ba8-424b-b60c-385a8a2837cb%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="46d6a-126">指定用于创建和定位邮箱中特殊文件夹的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="46d6a-126">Specifies the properties and operations for creating and locating the special folders in a mailbox.</span></span>
    
<span data-ttu-id="46d6a-127">[[MS-OXPHISH]](https://msdn.microsoft.com/library/ed49ab26-ba13-4d4c-8a94-98d4ceecd4b7%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="46d6a-127">[[MS-OXPHISH]](https://msdn.microsoft.com/library/ed49ab26-ba13-4d4c-8a94-98d4ceecd4b7%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="46d6a-128">标识并标记旨在欺骗收件人将敏感信息泄露 (例如密码和其他个人信息) 到不可信来源的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="46d6a-128">Identifies and marks email messages that are designed to trick recipients into divulging sensitive information (such as passwords and other personal information) to a non-trustworthy source.</span></span>
    
<span data-ttu-id="46d6a-129">[[MS-OXCSPAM]](https://msdn.microsoft.com/library/522f8587-4aed-4cd6-831b-40bd87862189%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="46d6a-129">[[MS-OXCSPAM]](https://msdn.microsoft.com/library/522f8587-4aed-4cd6-831b-40bd87862189%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="46d6a-130">允许/阻止列表的处理和垃圾邮件的确定。</span><span class="sxs-lookup"><span data-stu-id="46d6a-130">Enables the handling of allow/block lists and the determination of junk email messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="46d6a-131">头文件</span><span class="sxs-lookup"><span data-stu-id="46d6a-131">Header files</span></span>

<span data-ttu-id="46d6a-132">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="46d6a-132">Mapitags.h</span></span>
  
> <span data-ttu-id="46d6a-133">包含作为关联属性列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="46d6a-133">Contains definitions of properties listed as associated properties.</span></span>
    
<span data-ttu-id="46d6a-134">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="46d6a-134">Mapidefs.h</span></span>
  
> <span data-ttu-id="46d6a-135">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="46d6a-135">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="46d6a-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="46d6a-136">See also</span></span>



[<span data-ttu-id="46d6a-137">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="46d6a-137">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="46d6a-138">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="46d6a-138">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="46d6a-139">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="46d6a-139">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)


[<span data-ttu-id="46d6a-140">关于存储 API</span><span class="sxs-lookup"><span data-stu-id="46d6a-140">About the Store API</span></span>](https://msdn.microsoft.com/library/aa192884.aspx)

