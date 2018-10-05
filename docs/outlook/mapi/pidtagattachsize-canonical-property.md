---
title: PidTagAttachSize 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagAttachSize
api_type:
- HeaderDef
ms.assetid: 768b3215-dd9f-4aa0-b52c-178ca81a7b07
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: f3e4f19ab43a3da7c4840d762d5131813c83d996
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25399744"
---
# <a name="pidtagattachsize-canonical-property"></a><span data-ttu-id="3b1a5-103">PidTagAttachSize 规范属性</span><span class="sxs-lookup"><span data-stu-id="3b1a5-103">PidTagAttachSize Canonical Property</span></span>

  
  
<span data-ttu-id="3b1a5-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="3b1a5-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="3b1a5-105">包含附件上的所有属性的大小的总和，以字节为单位。</span><span class="sxs-lookup"><span data-stu-id="3b1a5-105">Contains the sum, in bytes, of the sizes of all properties on an attachment.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="3b1a5-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="3b1a5-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="3b1a5-107">PR_ATTACH_SIZE</span><span class="sxs-lookup"><span data-stu-id="3b1a5-107">PR_ATTACH_SIZE</span></span>  <br/> |
|<span data-ttu-id="3b1a5-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="3b1a5-108">Identifier:</span></span>  <br/> |<span data-ttu-id="3b1a5-109">0x0E20</span><span class="sxs-lookup"><span data-stu-id="3b1a5-109">0x0E20</span></span>  <br/> |
|<span data-ttu-id="3b1a5-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="3b1a5-110">Data type:</span></span>  <br/> |<span data-ttu-id="3b1a5-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="3b1a5-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="3b1a5-112">区域：</span><span class="sxs-lookup"><span data-stu-id="3b1a5-112">Area:</span></span>  <br/> |<span data-ttu-id="3b1a5-113">邮件附件</span><span class="sxs-lookup"><span data-stu-id="3b1a5-113">Message attachment</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="3b1a5-114">说明</span><span class="sxs-lookup"><span data-stu-id="3b1a5-114">Remarks</span></span>

<span data-ttu-id="3b1a5-115">建议附件子对象公开**PR_ATTACH_SIZE**属性。</span><span class="sxs-lookup"><span data-stu-id="3b1a5-115">It is recommended that attachment subobjects expose the **PR_ATTACH_SIZE** property.</span></span> <span data-ttu-id="3b1a5-116">包含在**PR_ATTACH_SIZE**总和包括**PR_ATTACH_DATA_BIN** ([PidTagAttachDataBinary](pidtagattachdatabinary-canonical-property.md)) 或**PR_ATTACH_DATA_OBJ** ([PidTagAttachDataObject](pidtagattachdataobject-canonical-property.md)) 属性的大小。</span><span class="sxs-lookup"><span data-stu-id="3b1a5-116">The sum contained in **PR_ATTACH_SIZE** includes the size of the **PR_ATTACH_DATA_BIN** ([PidTagAttachDataBinary](pidtagattachdatabinary-canonical-property.md)) or **PR_ATTACH_DATA_OBJ** ([PidTagAttachDataObject](pidtagattachdataobject-canonical-property.md)) property.</span></span> <span data-ttu-id="3b1a5-117">因此， **PR_ATTACH_SIZE**大于通常表达附件的内容。</span><span class="sxs-lookup"><span data-stu-id="3b1a5-117">Accordingly, **PR_ATTACH_SIZE** is usually larger than the contents of the attachment alone.</span></span> 
  
<span data-ttu-id="3b1a5-118">可以使用此属性，以检查的附件之前执行调制解调器远程传输大致大小并保存到磁盘上的附件时显示进度指示器。</span><span class="sxs-lookup"><span data-stu-id="3b1a5-118">This property can be used to check the approximate size of the attachment before performing a remote transfer by modem and to display progress indicators when saving the attachment to disk.</span></span> <span data-ttu-id="3b1a5-119">它是附加的 OLE 对象特别有用。</span><span class="sxs-lookup"><span data-stu-id="3b1a5-119">It is particularly useful with attached OLE objects.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="3b1a5-120">相关资源</span><span class="sxs-lookup"><span data-stu-id="3b1a5-120">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="3b1a5-121">协议规范</span><span class="sxs-lookup"><span data-stu-id="3b1a5-121">Protocol specifications</span></span>

<span data-ttu-id="3b1a5-122">[[MS OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="3b1a5-122">[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="3b1a5-123">处理邮件和附件的对象。</span><span class="sxs-lookup"><span data-stu-id="3b1a5-123">Handles message and attachment objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="3b1a5-124">头文件</span><span class="sxs-lookup"><span data-stu-id="3b1a5-124">Header files</span></span>

<span data-ttu-id="3b1a5-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="3b1a5-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="3b1a5-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="3b1a5-126">Provides data type definitions.</span></span>
    
<span data-ttu-id="3b1a5-127">mapitags.h</span><span class="sxs-lookup"><span data-stu-id="3b1a5-127">mapitags.h</span></span>
  
> <span data-ttu-id="3b1a5-128">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="3b1a5-128">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="3b1a5-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3b1a5-129">See also</span></span>



[<span data-ttu-id="3b1a5-130">PidTagMessageSize 规范属性</span><span class="sxs-lookup"><span data-stu-id="3b1a5-130">PidTagMessageSize Canonical Property</span></span>](pidtagmessagesize-canonical-property.md)


[<span data-ttu-id="3b1a5-131">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="3b1a5-131">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="3b1a5-132">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="3b1a5-132">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="3b1a5-133">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="3b1a5-133">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="3b1a5-134">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="3b1a5-134">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

