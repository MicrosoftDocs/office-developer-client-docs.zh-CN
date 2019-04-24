---
title: PidTagAttachmentContactPhoto 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagAttachmentContactPhoto
api_type:
- HeaderDef
ms.assetid: ea5b77b7-8440-4e54-abd2-c475138c8f63
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 5d61289349306b763d13a9a2111c2cd02ff3937e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32345764"
---
# <a name="pidtagattachmentcontactphoto-canonical-property"></a><span data-ttu-id="dc06d-103">PidTagAttachmentContactPhoto 规范属性</span><span class="sxs-lookup"><span data-stu-id="dc06d-103">PidTagAttachmentContactPhoto Canonical Property</span></span>

  
  
<span data-ttu-id="dc06d-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="dc06d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="dc06d-105">指示是否存在联系人的照片附件。</span><span class="sxs-lookup"><span data-stu-id="dc06d-105">Indicates the existence of a photo attachment for a contact.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="dc06d-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="dc06d-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="dc06d-107">PR_ATTACHMENT_CONTACTPHOTO</span><span class="sxs-lookup"><span data-stu-id="dc06d-107">PR_ATTACHMENT_CONTACTPHOTO</span></span>  <br/> |
|<span data-ttu-id="dc06d-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="dc06d-108">Identifier:</span></span>  <br/> |<span data-ttu-id="dc06d-109">0x7FFF</span><span class="sxs-lookup"><span data-stu-id="dc06d-109">0x7FFF</span></span>  <br/> |
|<span data-ttu-id="dc06d-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="dc06d-110">Data type:</span></span>  <br/> |<span data-ttu-id="dc06d-111">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="dc06d-111">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="dc06d-112">区域：</span><span class="sxs-lookup"><span data-stu-id="dc06d-112">Area:</span></span>  <br/> |<span data-ttu-id="dc06d-113">邮件附件</span><span class="sxs-lookup"><span data-stu-id="dc06d-113">Message attachment</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="dc06d-114">注解</span><span class="sxs-lookup"><span data-stu-id="dc06d-114">Remarks</span></span>

<span data-ttu-id="dc06d-115">此属性的值必须设置为 TRUE, 并且在给定的 Contact 对象上只能有一个附件。</span><span class="sxs-lookup"><span data-stu-id="dc06d-115">This property's value must be set to TRUE, and there should only be one attachment on a given Contact object.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="dc06d-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="dc06d-116">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="dc06d-117">协议规范</span><span class="sxs-lookup"><span data-stu-id="dc06d-117">Protocol specifications</span></span>

<span data-ttu-id="dc06d-118">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="dc06d-118">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="dc06d-119">提供属性集定义和对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="dc06d-119">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="dc06d-120">[[毫秒-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="dc06d-120">[[MS-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="dc06d-121">指定允许用于联系人和个人通讯组列表的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="dc06d-121">Specifies the properties and operations that are permissible for contacts and personal distribution lists.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="dc06d-122">头文件</span><span class="sxs-lookup"><span data-stu-id="dc06d-122">Header files</span></span>

<span data-ttu-id="dc06d-123">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="dc06d-123">Mapidefs.h</span></span>
  
> <span data-ttu-id="dc06d-124">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="dc06d-124">Provides data type definitions.</span></span>
    
<span data-ttu-id="dc06d-125">Mapitags</span><span class="sxs-lookup"><span data-stu-id="dc06d-125">Mapitags.h</span></span>
  
> <span data-ttu-id="dc06d-126">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="dc06d-126">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="dc06d-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dc06d-127">See also</span></span>



[<span data-ttu-id="dc06d-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="dc06d-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="dc06d-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="dc06d-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="dc06d-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="dc06d-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="dc06d-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="dc06d-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

