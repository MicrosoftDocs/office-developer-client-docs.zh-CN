---
title: PidLidNoteWidth 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidNoteWidth
api_type:
- COM
ms.assetid: 20788f40-a7a4-44f7-8e43-efd3a34e6b10
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: e217a7f8ced3438908974cfaf11c0454d9856976
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32326185"
---
# <a name="pidlidnotewidth-canonical-property"></a><span data-ttu-id="dffd0-103">PidLidNoteWidth 规范属性</span><span class="sxs-lookup"><span data-stu-id="dffd0-103">PidLidNoteWidth Canonical Property</span></span>

  
  
<span data-ttu-id="dffd0-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="dffd0-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="dffd0-105">指定可见邮件窗口的宽度 (以像素为单位)。</span><span class="sxs-lookup"><span data-stu-id="dffd0-105">Specifies the width of the visible message window in pixels.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="dffd0-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="dffd0-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="dffd0-107">dispidNoteWidth</span><span class="sxs-lookup"><span data-stu-id="dffd0-107">dispidNoteWidth</span></span>  <br/> |
|<span data-ttu-id="dffd0-108">属性集:</span><span class="sxs-lookup"><span data-stu-id="dffd0-108">Property set:</span></span>  <br/> |<span data-ttu-id="dffd0-109">PSETID_Note</span><span class="sxs-lookup"><span data-stu-id="dffd0-109">PSETID_Note</span></span>  <br/> |
|<span data-ttu-id="dffd0-110">长 ID (盖子):</span><span class="sxs-lookup"><span data-stu-id="dffd0-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="dffd0-111">0x00008B02</span><span class="sxs-lookup"><span data-stu-id="dffd0-111">0x00008B02</span></span>  <br/> |
|<span data-ttu-id="dffd0-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="dffd0-112">Data type:</span></span>  <br/> |<span data-ttu-id="dffd0-113">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="dffd0-113">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="dffd0-114">区域：</span><span class="sxs-lookup"><span data-stu-id="dffd0-114">Area:</span></span>  <br/> |<span data-ttu-id="dffd0-115">粘滞便笺</span><span class="sxs-lookup"><span data-stu-id="dffd0-115">Sticky Note</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="dffd0-116">注解</span><span class="sxs-lookup"><span data-stu-id="dffd0-116">Remarks</span></span>

<span data-ttu-id="dffd0-117">此值必须大于零。</span><span class="sxs-lookup"><span data-stu-id="dffd0-117">This value must be greater than zero.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="dffd0-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="dffd0-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="dffd0-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="dffd0-119">Protocol specifications</span></span>

<span data-ttu-id="dffd0-120">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="dffd0-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="dffd0-121">提供属性集定义和对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="dffd0-121">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="dffd0-122">[[毫秒-OXONOTE]](https://msdn.microsoft.com/library/6bf4ed7e-316c-4a3c-be27-5ec93e7ab39f%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="dffd0-122">[[MS-OXONOTE]](https://msdn.microsoft.com/library/6bf4ed7e-316c-4a3c-be27-5ec93e7ab39f%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="dffd0-123">指定在备注中允许的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="dffd0-123">Specifies the properties and operations that are permissible on notes.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="dffd0-124">头文件</span><span class="sxs-lookup"><span data-stu-id="dffd0-124">Header files</span></span>

<span data-ttu-id="dffd0-125">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="dffd0-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="dffd0-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="dffd0-126">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="dffd0-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dffd0-127">See also</span></span>



[<span data-ttu-id="dffd0-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="dffd0-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="dffd0-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="dffd0-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="dffd0-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="dffd0-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="dffd0-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="dffd0-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

