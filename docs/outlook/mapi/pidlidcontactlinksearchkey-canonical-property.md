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
ms.openlocfilehash: ea815631f63b5585a3f2705cfbd2639b8c655e6e
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25387494"
---
# <a name="pidlidcontactlinksearchkey-canonical-property"></a><span data-ttu-id="f312c-103">PidLidContactLinkSearchKey 规范属性</span><span class="sxs-lookup"><span data-stu-id="f312c-103">PidLidContactLinkSearchKey Canonical Property</span></span>

<span data-ttu-id="f312c-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f312c-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f312c-105">包含此消息对象链接到的联系人的**SearchKeys**的列表。</span><span class="sxs-lookup"><span data-stu-id="f312c-105">Contains the list of **SearchKeys** for the contact linked to by this message object.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="f312c-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="f312c-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="f312c-107">dispidContactLinkSearchKey</span><span class="sxs-lookup"><span data-stu-id="f312c-107">dispidContactLinkSearchKey</span></span>  <br/> |
|<span data-ttu-id="f312c-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="f312c-108">Property set:</span></span>  <br/> |<span data-ttu-id="f312c-109">PSETID_Common</span><span class="sxs-lookup"><span data-stu-id="f312c-109">PSETID_Common</span></span>  <br/> |
|<span data-ttu-id="f312c-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="f312c-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="f312c-111">0x00008584</span><span class="sxs-lookup"><span data-stu-id="f312c-111">0x00008584</span></span>  <br/> |
|<span data-ttu-id="f312c-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="f312c-112">Data type:</span></span>  <br/> |<span data-ttu-id="f312c-113">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="f312c-113">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="f312c-114">区域：</span><span class="sxs-lookup"><span data-stu-id="f312c-114">Area:</span></span>  <br/> |<span data-ttu-id="f312c-115">联系人</span><span class="sxs-lookup"><span data-stu-id="f312c-115">Contact</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="f312c-116">说明</span><span class="sxs-lookup"><span data-stu-id="f312c-116">Remarks</span></span>

|<span data-ttu-id="f312c-117">**以字节为单位的长度**</span><span class="sxs-lookup"><span data-stu-id="f312c-117">**Length in bytes**</span></span>|<span data-ttu-id="f312c-118">**说明**</span><span class="sxs-lookup"><span data-stu-id="f312c-118">**Description**</span></span>|<span data-ttu-id="f312c-119">**备注**</span><span class="sxs-lookup"><span data-stu-id="f312c-119">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f312c-120">2</span><span class="sxs-lookup"><span data-stu-id="f312c-120">2</span></span>  <br/> |<span data-ttu-id="f312c-121">ContactEntryCount</span><span class="sxs-lookup"><span data-stu-id="f312c-121">ContactEntryCount</span></span>  <br/> |<span data-ttu-id="f312c-122">无</span><span class="sxs-lookup"><span data-stu-id="f312c-122">None</span></span>  <br/> |
|<span data-ttu-id="f312c-123">变量</span><span class="sxs-lookup"><span data-stu-id="f312c-123">variable</span></span>  <br/> |<span data-ttu-id="f312c-124">SearchKey 数据</span><span class="sxs-lookup"><span data-stu-id="f312c-124">SearchKey data</span></span>  <br/> |<span data-ttu-id="f312c-125">重复 ContactEntryCount 次</span><span class="sxs-lookup"><span data-stu-id="f312c-125">Repeats ContactEntryCount times</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="f312c-126">相关资源</span><span class="sxs-lookup"><span data-stu-id="f312c-126">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="f312c-127">协议规范</span><span class="sxs-lookup"><span data-stu-id="f312c-127">Protocol specifications</span></span>

<span data-ttu-id="f312c-128">[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="f312c-128">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="f312c-129">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="f312c-129">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="f312c-130">[[MS OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="f312c-130">[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="f312c-131">处理邮件和附件的对象。</span><span class="sxs-lookup"><span data-stu-id="f312c-131">Handles message and attachment objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="f312c-132">头文件</span><span class="sxs-lookup"><span data-stu-id="f312c-132">Header files</span></span>

<span data-ttu-id="f312c-133">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="f312c-133">Mapidefs.h</span></span>
  
> <span data-ttu-id="f312c-134">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="f312c-134">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="f312c-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f312c-135">See also</span></span>

- [<span data-ttu-id="f312c-136">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="f312c-136">MAPI Properties</span></span>](mapi-properties.md) 
- [<span data-ttu-id="f312c-137">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="f312c-137">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
- [<span data-ttu-id="f312c-138">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="f312c-138">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
- [<span data-ttu-id="f312c-139">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="f312c-139">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

