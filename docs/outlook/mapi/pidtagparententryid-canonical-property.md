---
title: PidTagParentEntryId 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagParentEntryId
api_type:
- COM
ms.assetid: 55e08ace-493c-4246-8ebf-c304f4abc56a
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 65f5e6c5da88267ec2e63d0acf3ef6f8e10c893b
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32348228"
---
# <a name="pidtagparententryid-canonical-property"></a><span data-ttu-id="6c450-103">PidTagParentEntryId 规范属性</span><span class="sxs-lookup"><span data-stu-id="6c450-103">PidTagParentEntryId Canonical Property</span></span>

  
  
<span data-ttu-id="6c450-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="6c450-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="6c450-105">包含包含文件夹或邮件的文件夹的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="6c450-105">Contains the entry identifier of the folder that contains a folder or message.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="6c450-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="6c450-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="6c450-107">PR_PARENT_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="6c450-107">PR_PARENT_ENTRYID</span></span>  <br/> |
|<span data-ttu-id="6c450-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="6c450-108">Identifier:</span></span>  <br/> |<span data-ttu-id="6c450-109">0x0E09</span><span class="sxs-lookup"><span data-stu-id="6c450-109">0x0E09</span></span>  <br/> |
|<span data-ttu-id="6c450-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="6c450-110">Data type:</span></span>  <br/> |<span data-ttu-id="6c450-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="6c450-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="6c450-112">区域：</span><span class="sxs-lookup"><span data-stu-id="6c450-112">Area:</span></span>  <br/> |<span data-ttu-id="6c450-113">ID 属性</span><span class="sxs-lookup"><span data-stu-id="6c450-113">ID properties</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="6c450-114">注解</span><span class="sxs-lookup"><span data-stu-id="6c450-114">Remarks</span></span>

<span data-ttu-id="6c450-115">此属性由邮件存储区为所有文件夹和邮件计算。</span><span class="sxs-lookup"><span data-stu-id="6c450-115">This property is computed by message stores for all folders and messages.</span></span>
  
<span data-ttu-id="6c450-116">对于邮件存储根文件夹, 此属性包含该文件夹自己的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="6c450-116">For a message store root folder, this property contains the folder's own entry identifier.</span></span>
  
 <span data-ttu-id="6c450-117">**PR_PARENT_DISPLAY**([PidTagParentDisplay](pidtagparentdisplay-canonical-property.md)), 并且此属性不相互关联。</span><span class="sxs-lookup"><span data-stu-id="6c450-117">**PR_PARENT_DISPLAY** ([PidTagParentDisplay](pidtagparentdisplay-canonical-property.md)) and this property are not related to each other.</span></span> <span data-ttu-id="6c450-118">它们属于完全不同的上下文。</span><span class="sxs-lookup"><span data-stu-id="6c450-118">They belong to entirely different contexts.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="6c450-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="6c450-119">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="6c450-120">协议规范</span><span class="sxs-lookup"><span data-stu-id="6c450-120">Protocol specifications</span></span>

<span data-ttu-id="6c450-121">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="6c450-121">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="6c450-122">提供对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="6c450-122">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="6c450-123">[[毫秒-OXCDATA]](https://msdn.microsoft.com/library/ 1afa0cd9-b1a0-4520-b623-bf15030af5d8%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="6c450-123">[[MS-OXCDATA]](https://msdn.microsoft.com/library/ 1afa0cd9-b1a0-4520-b623-bf15030af5d8%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="6c450-124">定义在远程操作中使用的基本数据结构。</span><span class="sxs-lookup"><span data-stu-id="6c450-124">Defines the basic data structures that are used in remote operations.</span></span>
    
<span data-ttu-id="6c450-125">[[毫秒-OXCFOLD]](https://msdn.microsoft.com/library/c0f31b95-c07f-486c-98d9-535ed9705fbf%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="6c450-125">[[MS-OXCFOLD]](https://msdn.microsoft.com/library/c0f31b95-c07f-486c-98d9-535ed9705fbf%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="6c450-126">处理文件夹操作。</span><span class="sxs-lookup"><span data-stu-id="6c450-126">Handles folder operations.</span></span>
    
<span data-ttu-id="6c450-127">[[毫秒-OXCICAL]](https://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="6c450-127">[[MS-OXCICAL]](https://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="6c450-128">在 IETF RFC2445、RFC2446 和 RFC2447 以及约会和会议对象之间进行转换。</span><span class="sxs-lookup"><span data-stu-id="6c450-128">Converts between IETF RFC2445, RFC2446, and RFC2447, and appointment and meeting objects.</span></span>
    
<span data-ttu-id="6c450-129">[[毫秒-OXCSPAM]](https://msdn.microsoft.com/library/522f8587-4aed-4cd6-831b-40bd87862189%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="6c450-129">[[MS-OXCSPAM]](https://msdn.microsoft.com/library/522f8587-4aed-4cd6-831b-40bd87862189%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="6c450-130">启用对允许/阻止列表的处理以及确定垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="6c450-130">Enables the handling of allow/block lists and the determination of junk email messages.</span></span>
    
<span data-ttu-id="6c450-131">[[毫秒-OXOSFLD]](https://msdn.microsoft.com/library/a60e9c16-2ba8-424b-b60c-385a8a2837cb%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="6c450-131">[[MS-OXOSFLD]](https://msdn.microsoft.com/library/a60e9c16-2ba8-424b-b60c-385a8a2837cb%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="6c450-132">指定用于创建和定位邮箱中的特殊文件夹的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="6c450-132">Specifies the properties and operations for creating and locating the special folders in a mailbox.</span></span>
    
<span data-ttu-id="6c450-133">[[毫秒-OXPFOAB]](https://msdn.microsoft.com/library/258a07a7-34a7-4373-87c1-cddf51447d00%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="6c450-133">[[MS-OXPFOAB]](https://msdn.microsoft.com/library/258a07a7-34a7-4373-87c1-cddf51447d00%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="6c450-134">指定将脱机通讯簿 (OAB) 数据从服务器传递到客户端的方法。</span><span class="sxs-lookup"><span data-stu-id="6c450-134">Specifies the method of delivering offline address book (OAB) data from server to client.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="6c450-135">头文件</span><span class="sxs-lookup"><span data-stu-id="6c450-135">Header files</span></span>

<span data-ttu-id="6c450-136">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="6c450-136">Mapidefs.h</span></span>
  
> <span data-ttu-id="6c450-137">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="6c450-137">Provides data type definitions.</span></span>
    
<span data-ttu-id="6c450-138">Mapitags</span><span class="sxs-lookup"><span data-stu-id="6c450-138">Mapitags.h</span></span>
  
> <span data-ttu-id="6c450-139">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="6c450-139">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="6c450-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6c450-140">See also</span></span>



[<span data-ttu-id="6c450-141">PidTagFolderType 规范属性</span><span class="sxs-lookup"><span data-stu-id="6c450-141">PidTagFolderType Canonical Property</span></span>](pidtagfoldertype-canonical-property.md)


[<span data-ttu-id="6c450-142">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="6c450-142">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="6c450-143">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="6c450-143">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="6c450-144">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="6c450-144">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="6c450-145">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="6c450-145">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

