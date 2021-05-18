---
title: PidLidContactLinkName 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidContactLinkName
api_type:
- COM
ms.assetid: 7b9be1cd-e81e-42f3-b391-036afa2ae1b4
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 3236c848a4aef83f3a675994c834ef27a5b7bb53
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32319738"
---
# <a name="pidlidcontactlinkname-canonical-property"></a><span data-ttu-id="4312d-103">PidLidContactLinkName 规范属性</span><span class="sxs-lookup"><span data-stu-id="4312d-103">PidLidContactLinkName Canonical Property</span></span>

  
  
<span data-ttu-id="4312d-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="4312d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="4312d-105">包含 **PidLidContacts** 属性 ([dispidContacts](pidlidcontacts-canonical-property.md)) 元素。</span><span class="sxs-lookup"><span data-stu-id="4312d-105">Contains the elements of the **dispidContacts** ([PidLidContacts](pidlidcontacts-canonical-property.md)) property.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="4312d-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="4312d-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="4312d-107">dispidContactLinkName</span><span class="sxs-lookup"><span data-stu-id="4312d-107">dispidContactLinkName</span></span>  <br/> |
|<span data-ttu-id="4312d-108">属性集：</span><span class="sxs-lookup"><span data-stu-id="4312d-108">Property set:</span></span>  <br/> |<span data-ttu-id="4312d-109">PSETID_Common</span><span class="sxs-lookup"><span data-stu-id="4312d-109">PSETID_Common</span></span>  <br/> |
|<span data-ttu-id="4312d-110">LONG ID (的一) ：</span><span class="sxs-lookup"><span data-stu-id="4312d-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="4312d-111">0x00008586</span><span class="sxs-lookup"><span data-stu-id="4312d-111">0x00008586</span></span>  <br/> |
|<span data-ttu-id="4312d-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="4312d-112">Data type:</span></span>  <br/> |<span data-ttu-id="4312d-113">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="4312d-113">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="4312d-114">区域：</span><span class="sxs-lookup"><span data-stu-id="4312d-114">Area:</span></span>  <br/> |<span data-ttu-id="4312d-115">联系人</span><span class="sxs-lookup"><span data-stu-id="4312d-115">Contact</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="4312d-116">备注</span><span class="sxs-lookup"><span data-stu-id="4312d-116">Remarks</span></span>

<span data-ttu-id="4312d-117">**dispidContactLinkName** 属性中的元素用分号和空格分隔 (";") 。</span><span class="sxs-lookup"><span data-stu-id="4312d-117">The elements in the **dispidContactLinkName** property are separated by a semicolon and a space ("; ").</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="4312d-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="4312d-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="4312d-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="4312d-119">Protocol specifications</span></span>

<span data-ttu-id="4312d-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="4312d-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="4312d-121">提供属性集定义和对相关协议规范Exchange Server引用。</span><span class="sxs-lookup"><span data-stu-id="4312d-121">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="4312d-122">[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="4312d-122">[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="4312d-123">处理邮件和附件对象。</span><span class="sxs-lookup"><span data-stu-id="4312d-123">Handles message and attachment objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="4312d-124">头文件</span><span class="sxs-lookup"><span data-stu-id="4312d-124">Header files</span></span>

<span data-ttu-id="4312d-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="4312d-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="4312d-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="4312d-126">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="4312d-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4312d-127">See also</span></span>



[<span data-ttu-id="4312d-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="4312d-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="4312d-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="4312d-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="4312d-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="4312d-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="4312d-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="4312d-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

