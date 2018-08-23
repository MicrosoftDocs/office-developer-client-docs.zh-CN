---
title: PidLidContactLinkSearchKey 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidContactLinkSearchKey
api_type:
- COM
ms.assetid: 82d21d38-a6c6-4e12-85b1-8158b2f5cce7
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 11e1bd22da480669f72768e5d75b637e1257b6d1
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22589348"
---
# <a name="pidlidcontactlinksearchkey-canonical-property"></a><span data-ttu-id="b29ad-103">PidLidContactLinkSearchKey 规范属性</span><span class="sxs-lookup"><span data-stu-id="b29ad-103">PidLidContactLinkSearchKey Canonical Property</span></span>

<span data-ttu-id="b29ad-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b29ad-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b29ad-105">包含此消息对象链接到的联系人的**SearchKeys**的列表。</span><span class="sxs-lookup"><span data-stu-id="b29ad-105">Contains the list of **SearchKeys** for the contact linked to by this message object.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="b29ad-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="b29ad-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="b29ad-107">dispidContactLinkSearchKey</span><span class="sxs-lookup"><span data-stu-id="b29ad-107">dispidContactLinkSearchKey</span></span>  <br/> |
|<span data-ttu-id="b29ad-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="b29ad-108">Property set:</span></span>  <br/> |<span data-ttu-id="b29ad-109">PSETID_Common</span><span class="sxs-lookup"><span data-stu-id="b29ad-109">PSETID_Common</span></span>  <br/> |
|<span data-ttu-id="b29ad-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="b29ad-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="b29ad-111">0x00008584</span><span class="sxs-lookup"><span data-stu-id="b29ad-111">0x00008584</span></span>  <br/> |
|<span data-ttu-id="b29ad-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="b29ad-112">Data type:</span></span>  <br/> |<span data-ttu-id="b29ad-113">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="b29ad-113">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="b29ad-114">区域：</span><span class="sxs-lookup"><span data-stu-id="b29ad-114">Area:</span></span>  <br/> |<span data-ttu-id="b29ad-115">联系人</span><span class="sxs-lookup"><span data-stu-id="b29ad-115">Contact</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="b29ad-116">注解</span><span class="sxs-lookup"><span data-stu-id="b29ad-116">Remarks</span></span>

|<span data-ttu-id="b29ad-117">**以字节为单位的长度**</span><span class="sxs-lookup"><span data-stu-id="b29ad-117">**Length in bytes**</span></span>|<span data-ttu-id="b29ad-118">**说明**</span><span class="sxs-lookup"><span data-stu-id="b29ad-118">**Description**</span></span>|<span data-ttu-id="b29ad-119">**备注**</span><span class="sxs-lookup"><span data-stu-id="b29ad-119">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b29ad-120">2</span><span class="sxs-lookup"><span data-stu-id="b29ad-120">2</span></span>  <br/> |<span data-ttu-id="b29ad-121">ContactEntryCount</span><span class="sxs-lookup"><span data-stu-id="b29ad-121">ContactEntryCount</span></span>  <br/> |<span data-ttu-id="b29ad-122">无</span><span class="sxs-lookup"><span data-stu-id="b29ad-122">None</span></span>  <br/> |
|<span data-ttu-id="b29ad-123">变量</span><span class="sxs-lookup"><span data-stu-id="b29ad-123">variable</span></span>  <br/> |<span data-ttu-id="b29ad-124">SearchKey 数据</span><span class="sxs-lookup"><span data-stu-id="b29ad-124">SearchKey data</span></span>  <br/> |<span data-ttu-id="b29ad-125">重复 ContactEntryCount 次</span><span class="sxs-lookup"><span data-stu-id="b29ad-125">Repeats ContactEntryCount times</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="b29ad-126">相关资源</span><span class="sxs-lookup"><span data-stu-id="b29ad-126">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="b29ad-127">协议规范</span><span class="sxs-lookup"><span data-stu-id="b29ad-127">Protocol specifications</span></span>

<span data-ttu-id="b29ad-128">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="b29ad-128">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="b29ad-129">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="b29ad-129">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="b29ad-130">[[MS OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="b29ad-130">[[MS-OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="b29ad-131">处理邮件和附件的对象。</span><span class="sxs-lookup"><span data-stu-id="b29ad-131">Handles message and attachment objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="b29ad-132">头文件</span><span class="sxs-lookup"><span data-stu-id="b29ad-132">Header files</span></span>

<span data-ttu-id="b29ad-133">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="b29ad-133">Mapidefs.h</span></span>
  
> <span data-ttu-id="b29ad-134">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="b29ad-134">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="b29ad-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b29ad-135">See also</span></span>

- [<span data-ttu-id="b29ad-136">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="b29ad-136">MAPI Properties</span></span>](mapi-properties.md) 
- [<span data-ttu-id="b29ad-137">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="b29ad-137">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
- [<span data-ttu-id="b29ad-138">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="b29ad-138">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
- [<span data-ttu-id="b29ad-139">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="b29ad-139">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

