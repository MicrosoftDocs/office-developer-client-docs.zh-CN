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
# <a name="pidlidspamoriginalfolder-canonical-property"></a><span data-ttu-id="8932a-103">PidLidSpamOriginalFolder 规范属性</span><span class="sxs-lookup"><span data-stu-id="8932a-103">PidLidSpamOriginalFolder Canonical Property</span></span>

  
  
<span data-ttu-id="8932a-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="8932a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="8932a-105">指示邮件在被筛选到垃圾邮件文件夹之前位于哪个文件夹。</span><span class="sxs-lookup"><span data-stu-id="8932a-105">Indicates which folder a message was in before it was filtered into the junk email folder.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="8932a-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="8932a-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="8932a-107">dispidSpamOriginalFolder</span><span class="sxs-lookup"><span data-stu-id="8932a-107">dispidSpamOriginalFolder</span></span>  <br/> |
|<span data-ttu-id="8932a-108">属性集：</span><span class="sxs-lookup"><span data-stu-id="8932a-108">Property set:</span></span>  <br/> |<span data-ttu-id="8932a-109">PSETID_Common</span><span class="sxs-lookup"><span data-stu-id="8932a-109">PSETID_Common</span></span>  <br/> |
|<span data-ttu-id="8932a-110">LONG ID (的一) ：</span><span class="sxs-lookup"><span data-stu-id="8932a-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="8932a-111">0x0000859C</span><span class="sxs-lookup"><span data-stu-id="8932a-111">0x0000859C</span></span>  <br/> |
|<span data-ttu-id="8932a-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="8932a-112">Data type:</span></span>  <br/> |<span data-ttu-id="8932a-113">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="8932a-113">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="8932a-114">区域：</span><span class="sxs-lookup"><span data-stu-id="8932a-114">Area:</span></span>  <br/> |<span data-ttu-id="8932a-115">垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="8932a-115">Spam</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="8932a-116">备注</span><span class="sxs-lookup"><span data-stu-id="8932a-116">Remarks</span></span>

<span data-ttu-id="8932a-117">此属性的值是移动邮件之前包含邮件的文件夹的 **EntryID。**</span><span class="sxs-lookup"><span data-stu-id="8932a-117">The value of this property is the **EntryID** of the folder that contained the message before it was moved.</span></span> <span data-ttu-id="8932a-118">当邮件被标记为垃圾邮件时，应设置此属性。</span><span class="sxs-lookup"><span data-stu-id="8932a-118">This property should be set when a message is marked as spam.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="8932a-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="8932a-119">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="8932a-120">协议规范</span><span class="sxs-lookup"><span data-stu-id="8932a-120">Protocol specifications</span></span>

<span data-ttu-id="8932a-121">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="8932a-121">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="8932a-122">提供属性集定义和对相关协议规范Exchange Server引用。</span><span class="sxs-lookup"><span data-stu-id="8932a-122">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="8932a-123">[[MS-OXCSPAM]](https://msdn.microsoft.com/library/522f8587-4aed-4cd6-831b-40bd87862189%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="8932a-123">[[MS-OXCSPAM]](https://msdn.microsoft.com/library/522f8587-4aed-4cd6-831b-40bd87862189%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="8932a-124">允许/阻止列表的处理和垃圾邮件的确定。</span><span class="sxs-lookup"><span data-stu-id="8932a-124">Enables the handling of allow/block lists and the determination of junk email messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="8932a-125">头文件</span><span class="sxs-lookup"><span data-stu-id="8932a-125">Header files</span></span>

<span data-ttu-id="8932a-126">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="8932a-126">Mapidefs.h</span></span>
  
> <span data-ttu-id="8932a-127">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="8932a-127">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="8932a-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8932a-128">See also</span></span>



[<span data-ttu-id="8932a-129">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="8932a-129">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="8932a-130">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="8932a-130">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="8932a-131">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="8932a-131">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="8932a-132">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="8932a-132">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

