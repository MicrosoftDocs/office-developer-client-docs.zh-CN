---
title: PidLidContacts 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidContacts
api_type:
- COM
ms.assetid: 709e701f-b24e-4cd5-8c55-3f9e67f67a4a
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 2a097b8e8071c08b82a05f3c8e0b021db8ec5107
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22585393"
---
# <a name="pidlidcontacts-canonical-property"></a><span data-ttu-id="3d7fb-103">PidLidContacts 规范属性</span><span class="sxs-lookup"><span data-stu-id="3d7fb-103">PidLidContacts Canonical Property</span></span>

  
  
<span data-ttu-id="3d7fb-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="3d7fb-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="3d7fb-105">包含与项关联的联系人的姓名。</span><span class="sxs-lookup"><span data-stu-id="3d7fb-105">Contains the names of contacts associated with the item.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="3d7fb-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="3d7fb-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="3d7fb-107">dispidContacts</span><span class="sxs-lookup"><span data-stu-id="3d7fb-107">dispidContacts</span></span>  <br/> |
|<span data-ttu-id="3d7fb-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="3d7fb-108">Property set:</span></span>  <br/> |<span data-ttu-id="3d7fb-109">PSETID_Common</span><span class="sxs-lookup"><span data-stu-id="3d7fb-109">PSETID_Common</span></span>  <br/> |
|<span data-ttu-id="3d7fb-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="3d7fb-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="3d7fb-111">0x0000853A</span><span class="sxs-lookup"><span data-stu-id="3d7fb-111">0x0000853A</span></span>  <br/> |
|<span data-ttu-id="3d7fb-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="3d7fb-112">Data type:</span></span>  <br/> |<span data-ttu-id="3d7fb-113">PT_MV_UNICODE</span><span class="sxs-lookup"><span data-stu-id="3d7fb-113">PT_MV_UNICODE</span></span>  <br/> |
|<span data-ttu-id="3d7fb-114">区域：</span><span class="sxs-lookup"><span data-stu-id="3d7fb-114">Area:</span></span>  <br/> |<span data-ttu-id="3d7fb-115">常规消息</span><span class="sxs-lookup"><span data-stu-id="3d7fb-115">General messaging</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="3d7fb-116">注解</span><span class="sxs-lookup"><span data-stu-id="3d7fb-116">Remarks</span></span>

<span data-ttu-id="3d7fb-117">此属性包含每个通讯簿**EntryID** **dispidContactLinkEntry** ([PidLidContactLinkEntry](pidlidcontactlinkentry-canonical-property.md)) 属性的值中引用的**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="3d7fb-117">This property contains the **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) property of each Address Book **EntryID** that is referenced in the value of **dispidContactLinkEntry** ([PidLidContactLinkEntry](pidlidcontactlinkentry-canonical-property.md)) property.</span></span> <span data-ttu-id="3d7fb-118">它可能包括**dispidContactLinkEntry**中被引用的名称。</span><span class="sxs-lookup"><span data-stu-id="3d7fb-118">It may include names not referenced in **dispidContactLinkEntry**.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="3d7fb-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="3d7fb-119">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="3d7fb-120">协议规范</span><span class="sxs-lookup"><span data-stu-id="3d7fb-120">Protocol specifications</span></span>

<span data-ttu-id="3d7fb-121">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="3d7fb-121">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="3d7fb-122">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="3d7fb-122">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="3d7fb-123">[[MS OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="3d7fb-123">[[MS-OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="3d7fb-124">指定的属性和约会、 会议请求和响应消息的操作。</span><span class="sxs-lookup"><span data-stu-id="3d7fb-124">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
<span data-ttu-id="3d7fb-125">[[MS OXOJRNL]](http://msdn.microsoft.com/library/2aa04fd2-0f36-4ce4-9178-c0fc70aa8d43%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="3d7fb-125">[[MS-OXOJRNL]](http://msdn.microsoft.com/library/2aa04fd2-0f36-4ce4-9178-c0fc70aa8d43%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="3d7fb-126">指定的属性和操作所允许的日志。</span><span class="sxs-lookup"><span data-stu-id="3d7fb-126">Specifies the properties and operations that are permissible for journals.</span></span>
    
<span data-ttu-id="3d7fb-127">[[MS OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="3d7fb-127">[[MS-OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="3d7fb-128">处理邮件和附件的对象。</span><span class="sxs-lookup"><span data-stu-id="3d7fb-128">Handles message and attachment objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="3d7fb-129">头文件</span><span class="sxs-lookup"><span data-stu-id="3d7fb-129">Header files</span></span>

<span data-ttu-id="3d7fb-130">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="3d7fb-130">Mapidefs.h</span></span>
  
> <span data-ttu-id="3d7fb-131">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="3d7fb-131">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="3d7fb-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3d7fb-132">See also</span></span>



[<span data-ttu-id="3d7fb-133">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="3d7fb-133">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="3d7fb-134">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="3d7fb-134">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="3d7fb-135">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="3d7fb-135">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="3d7fb-136">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="3d7fb-136">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

