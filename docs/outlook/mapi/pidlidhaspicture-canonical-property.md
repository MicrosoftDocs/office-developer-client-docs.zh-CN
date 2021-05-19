---
title: PidLidHasPicture 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidHasPicture
api_type:
- COM
ms.assetid: c3bea11c-3197-4060-8672-f1b4bf352112
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 3aef2fc1038751c9ad6fb97cf347c2dcab114fda
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32357748"
---
# <a name="pidlidhaspicture-canonical-property"></a><span data-ttu-id="e13eb-103">PidLidHasPicture 规范属性</span><span class="sxs-lookup"><span data-stu-id="e13eb-103">PidLidHasPicture Canonical Property</span></span>

  
  
<span data-ttu-id="e13eb-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e13eb-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="e13eb-105">指定联系人是否存在照片附件。</span><span class="sxs-lookup"><span data-stu-id="e13eb-105">Specifies whether a photo attachment exists for a contact.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="e13eb-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="e13eb-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="e13eb-107">dispidHasPicture</span><span class="sxs-lookup"><span data-stu-id="e13eb-107">dispidHasPicture</span></span>  <br/> |
|<span data-ttu-id="e13eb-108">属性集：</span><span class="sxs-lookup"><span data-stu-id="e13eb-108">Property set:</span></span>  <br/> |<span data-ttu-id="e13eb-109">PSETID_Address</span><span class="sxs-lookup"><span data-stu-id="e13eb-109">PSETID_Address</span></span>  <br/> |
|<span data-ttu-id="e13eb-110">LONG ID (的一) ：</span><span class="sxs-lookup"><span data-stu-id="e13eb-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="e13eb-111">0x00008015</span><span class="sxs-lookup"><span data-stu-id="e13eb-111">0x00008015</span></span>  <br/> |
|<span data-ttu-id="e13eb-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="e13eb-112">Data type:</span></span>  <br/> |<span data-ttu-id="e13eb-113">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="e13eb-113">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="e13eb-114">区域：</span><span class="sxs-lookup"><span data-stu-id="e13eb-114">Area:</span></span>  <br/> |<span data-ttu-id="e13eb-115">联系人</span><span class="sxs-lookup"><span data-stu-id="e13eb-115">Contact</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="e13eb-116">备注</span><span class="sxs-lookup"><span data-stu-id="e13eb-116">Remarks</span></span>

<span data-ttu-id="e13eb-117">如果此属性存在且设置为 TRUE，则联系人的附件表包含一个附件，PR_ATTACHMENT_CONTACTPHOTO ( [PidTagAttachmentContactPhoto](pidtagattachmentcontactphoto-canonical-property.md)) 设置为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="e13eb-117">If this property exists and is set to TRUE, the contact's attachment table contains an attachment with the **PR_ATTACHMENT_CONTACTPHOTO** ([PidTagAttachmentContactPhoto](pidtagattachmentcontactphoto-canonical-property.md)) property set to TRUE.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="e13eb-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="e13eb-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="e13eb-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="e13eb-119">Protocol specifications</span></span>

<span data-ttu-id="e13eb-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="e13eb-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="e13eb-121">提供属性集定义和对相关协议规范Exchange Server引用。</span><span class="sxs-lookup"><span data-stu-id="e13eb-121">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="e13eb-122">[[MS-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="e13eb-122">[[MS-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="e13eb-123">指定联系人和个人通讯组列表允许的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="e13eb-123">Specifies the properties and operations that are permissible for contacts and personal distribution lists.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="e13eb-124">头文件</span><span class="sxs-lookup"><span data-stu-id="e13eb-124">Header files</span></span>

<span data-ttu-id="e13eb-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="e13eb-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="e13eb-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="e13eb-126">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="e13eb-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e13eb-127">See also</span></span>



[<span data-ttu-id="e13eb-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="e13eb-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="e13eb-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="e13eb-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="e13eb-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="e13eb-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="e13eb-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="e13eb-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

