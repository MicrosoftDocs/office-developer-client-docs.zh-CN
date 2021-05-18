---
title: PidTagUrlComponentName 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagUrlComponentName
api_type:
- COM
ms.assetid: a21906f9-5408-41ba-a89b-273ab60eeef3
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 26a9d432d98c546aefa8f511ba2c4c9bb26cfd80
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32320424"
---
# <a name="pidtagurlcomponentname-canonical-property"></a><span data-ttu-id="dd106-103">PidTagUrlComponentName 规范属性</span><span class="sxs-lookup"><span data-stu-id="dd106-103">PidTagUrlComponentName Canonical Property</span></span>

  
  
<span data-ttu-id="dd106-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="dd106-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="dd106-105">邮件的 URL 组件名称。</span><span class="sxs-lookup"><span data-stu-id="dd106-105">The URL component name for a message.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="dd106-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="dd106-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="dd106-107">PR_URL_COMP_NAME、PR_URL_COMP_NAME_A、PR_URL_COMP_NAME_W</span><span class="sxs-lookup"><span data-stu-id="dd106-107">PR_URL_COMP_NAME, PR_URL_COMP_NAME_A, PR_URL_COMP_NAME_W</span></span>  <br/> |
|<span data-ttu-id="dd106-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="dd106-108">Identifier:</span></span>  <br/> |<span data-ttu-id="dd106-109">0x10F3</span><span class="sxs-lookup"><span data-stu-id="dd106-109">0x10F3</span></span>  <br/> |
|<span data-ttu-id="dd106-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="dd106-110">Data type:</span></span>  <br/> |<span data-ttu-id="dd106-111">PT_STRING8、PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="dd106-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="dd106-112">区域：</span><span class="sxs-lookup"><span data-stu-id="dd106-112">Area:</span></span>  <br/> |<span data-ttu-id="dd106-113">常规消息</span><span class="sxs-lookup"><span data-stu-id="dd106-113">General messaging</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="dd106-114">备注</span><span class="sxs-lookup"><span data-stu-id="dd106-114">Remarks</span></span>

<span data-ttu-id="dd106-115">这些属性在文件夹中应该是唯一的。</span><span class="sxs-lookup"><span data-stu-id="dd106-115">These properties should be unique within a folder.</span></span> <span data-ttu-id="dd106-116">如果在创建邮件时未设置，则邮件存储应基于各种邮件属性设置这些属性，具体取决于邮件类。</span><span class="sxs-lookup"><span data-stu-id="dd106-116">If not set when the message is created, the message store should set these properties based on various message properties, depending on the message class.</span></span> <span data-ttu-id="dd106-117">例如 **，IPM。注意** 和 **IPM。约会** 邮件应基于 [PidTagSubject](pidtagsubject-canonical-property.md)属性和 IPM PR_SUBJECT (属性) 设置 **此属性。联系人** 邮件应基于 [PidLidFileUnder](pidlidfileunder-canonical-property.md)属性的 **dispidFileUnder** (设置此属性) 属性。</span><span class="sxs-lookup"><span data-stu-id="dd106-117">For example, the **IPM.Note** and **IPM.Appointment** messages should have this property set based on the **PR_SUBJECT** ([PidTagSubject](pidtagsubject-canonical-property.md)) property and the **IPM.Contact** messages should have this property set based on the **dispidFileUnder** ([PidLidFileUnder](pidlidfileunder-canonical-property.md)) property.</span></span> <span data-ttu-id="dd106-118">对于大多数其他邮件类，此属性应基于 PR_DISPLAY_NAME ( [PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="dd106-118">For most other message classes, this property should be based on the **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) property.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="dd106-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="dd106-119">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="dd106-120">协议规范</span><span class="sxs-lookup"><span data-stu-id="dd106-120">Protocol specifications</span></span>

<span data-ttu-id="dd106-121">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="dd106-121">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="dd106-122">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="dd106-122">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="dd106-123">[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="dd106-123">[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="dd106-124">处理邮件和附件对象。</span><span class="sxs-lookup"><span data-stu-id="dd106-124">Handles message and attachment objects.</span></span>
    
<span data-ttu-id="dd106-125">[[MS-OXTNEF]](https://msdn.microsoft.com/library/1f0544d7-30b7-4194-b58f-adc82f3763bb%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="dd106-125">[[MS-OXTNEF]](https://msdn.microsoft.com/library/1f0544d7-30b7-4194-b58f-adc82f3763bb%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="dd106-126">将邮件和附件对象编码和解码为有效的流表示形式。</span><span class="sxs-lookup"><span data-stu-id="dd106-126">Encodes and decodes message and attachment objects to an efficient stream representation.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="dd106-127">头文件</span><span class="sxs-lookup"><span data-stu-id="dd106-127">Header files</span></span>

<span data-ttu-id="dd106-128">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="dd106-128">Mapidefs.h</span></span>
  
> <span data-ttu-id="dd106-129">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="dd106-129">Provides data type definitions.</span></span>
    
<span data-ttu-id="dd106-130">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="dd106-130">Mapitags.h</span></span>
  
> <span data-ttu-id="dd106-131">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="dd106-131">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="dd106-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dd106-132">See also</span></span>



[<span data-ttu-id="dd106-133">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="dd106-133">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="dd106-134">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="dd106-134">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="dd106-135">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="dd106-135">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="dd106-136">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="dd106-136">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

