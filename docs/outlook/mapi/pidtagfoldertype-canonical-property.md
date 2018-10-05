---
title: PidTagFolderType 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagFolderType
api_type:
- HeaderDef
ms.assetid: 2ab4681e-0013-4ba0-ba26-50517bbf3f5b
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7cca884eae2111a94d87cc24a6d30542148ab845
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25394872"
---
# <a name="pidtagfoldertype-canonical-property"></a><span data-ttu-id="e8d8b-103">PidTagFolderType 规范属性</span><span class="sxs-lookup"><span data-stu-id="e8d8b-103">PidTagFolderType Canonical Property</span></span>

  
  
<span data-ttu-id="e8d8b-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e8d8b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="e8d8b-105">包含一个常量，指示文件夹类型。</span><span class="sxs-lookup"><span data-stu-id="e8d8b-105">Contains a constant that indicates the folder type.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="e8d8b-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="e8d8b-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="e8d8b-107">PR_FOLDER_TYPE</span><span class="sxs-lookup"><span data-stu-id="e8d8b-107">PR_FOLDER_TYPE</span></span>  <br/> |
|<span data-ttu-id="e8d8b-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="e8d8b-108">Identifier:</span></span>  <br/> |<span data-ttu-id="e8d8b-109">0x3601</span><span class="sxs-lookup"><span data-stu-id="e8d8b-109">0x3601</span></span>  <br/> |
|<span data-ttu-id="e8d8b-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="e8d8b-110">Data type:</span></span>  <br/> |<span data-ttu-id="e8d8b-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="e8d8b-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="e8d8b-112">区域：</span><span class="sxs-lookup"><span data-stu-id="e8d8b-112">Area:</span></span>  <br/> |<span data-ttu-id="e8d8b-113">MAPI 容器</span><span class="sxs-lookup"><span data-stu-id="e8d8b-113">MAPI container</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="e8d8b-114">说明</span><span class="sxs-lookup"><span data-stu-id="e8d8b-114">Remarks</span></span>

<span data-ttu-id="e8d8b-115">此属性可以具有完全下列值之一：</span><span class="sxs-lookup"><span data-stu-id="e8d8b-115">This property can have exactly one of the following values:</span></span>
  
<span data-ttu-id="e8d8b-116">FOLDER_GENERIC</span><span class="sxs-lookup"><span data-stu-id="e8d8b-116">FOLDER_GENERIC</span></span> 
  
> <span data-ttu-id="e8d8b-117">包含邮件和其他文件夹的通用文件夹。</span><span class="sxs-lookup"><span data-stu-id="e8d8b-117">A generic folder that contains messages and other folders.</span></span>
    
<span data-ttu-id="e8d8b-118">FOLDER_ROOT</span><span class="sxs-lookup"><span data-stu-id="e8d8b-118">FOLDER_ROOT</span></span> 
  
> <span data-ttu-id="e8d8b-119">文件夹层次结构表，即，具有没有父文件夹的文件夹的根文件夹。</span><span class="sxs-lookup"><span data-stu-id="e8d8b-119">The root folder of the folder hierarchy table, that is, a folder that has no parent folder.</span></span>
    
<span data-ttu-id="e8d8b-120">FOLDER_SEARCH</span><span class="sxs-lookup"><span data-stu-id="e8d8b-120">FOLDER_SEARCH</span></span> 
  
> <span data-ttu-id="e8d8b-121">包含的链接符合搜索条件的邮件的窗体中的搜索结果的文件夹。</span><span class="sxs-lookup"><span data-stu-id="e8d8b-121">A folder that contains the results of a search, in the form of links to messages that meet search criteria.</span></span>
    
<span data-ttu-id="e8d8b-122">消息存储根不应与该存储区中的人际邮件 (IPM) 子树的根混淆。</span><span class="sxs-lookup"><span data-stu-id="e8d8b-122">The root of a message store should not be confused with the root of the interpersonal message (IPM) subtree in that store.</span></span> <span data-ttu-id="e8d8b-123">通过调用[IMsgStore::OpenEntry](imsgstore-openentry.md)方法具有 null 条目标识符获取存储区的根文件夹，没有父级。</span><span class="sxs-lookup"><span data-stu-id="e8d8b-123">The store's root folder, which has no parent, is obtained by calling the [IMsgStore::OpenEntry](imsgstore-openentry.md) method with a null entry identifier.</span></span> <span data-ttu-id="e8d8b-124">IPM 子树的根文件夹，具有父，通过使用**OpenEntry**呼叫**PR_IPM_SUBTREE_ENTRYID** ([PidTagIpmSubtreeEntryId](pidtagipmsubtreeentryid-canonical-property.md)) 属性的值。</span><span class="sxs-lookup"><span data-stu-id="e8d8b-124">The IPM subtree's root folder, which does have a parent, is obtained by using the value of the **PR_IPM_SUBTREE_ENTRYID** ([PidTagIpmSubtreeEntryId](pidtagipmsubtreeentryid-canonical-property.md)) property for the **OpenEntry** call.</span></span> 
  
<span data-ttu-id="e8d8b-125">MAPI 允许每个邮件存储的只有一个根文件夹。</span><span class="sxs-lookup"><span data-stu-id="e8d8b-125">MAPI allows only one root folder per message store.</span></span> <span data-ttu-id="e8d8b-126">此文件夹包含邮件和其他文件夹。</span><span class="sxs-lookup"><span data-stu-id="e8d8b-126">This folder contains messages and other folders.</span></span> <span data-ttu-id="e8d8b-127">根文件夹的**PR_PARENT_ENTRYID** ([PidTagParentEntryId](pidtagparententryid-canonical-property.md)) 属性包含的文件夹的项标识符。</span><span class="sxs-lookup"><span data-stu-id="e8d8b-127">The root folder's **PR_PARENT_ENTRYID** ([PidTagParentEntryId](pidtagparententryid-canonical-property.md)) property contains the folder's own entry identifier.</span></span>
  
<span data-ttu-id="e8d8b-128">搜索结果文件夹中的信息主要存储在其内容表，该表包含相同的典型的目录表格列以及标识在其中找到每封邮件的文件夹的两个额外的列： **PR_PARENT_DISPLAY** ([PidTagParentDisplay](pidtagparentdisplay-canonical-property.md)) （显示名称，所需） 和此属性 （条目标识符，可选）。</span><span class="sxs-lookup"><span data-stu-id="e8d8b-128">The information in a search-results folder is mainly stored in its contents table, which contains the same columns as a typical contents table, as well as two extra columns identifying the folder in which each message was found: **PR_PARENT_DISPLAY** ([PidTagParentDisplay](pidtagparentdisplay-canonical-property.md)) (display name, required) and this property (entry identifier, optional).</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="e8d8b-129">相关资源</span><span class="sxs-lookup"><span data-stu-id="e8d8b-129">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="e8d8b-130">协议规范</span><span class="sxs-lookup"><span data-stu-id="e8d8b-130">Protocol specifications</span></span>

<span data-ttu-id="e8d8b-131">[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="e8d8b-131">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="e8d8b-132">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="e8d8b-132">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="e8d8b-133">[[MS OXCFOLD]](https://msdn.microsoft.com/library/c0f31b95-c07f-486c-98d9-535ed9705fbf%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="e8d8b-133">[[MS-OXCFOLD]](https://msdn.microsoft.com/library/c0f31b95-c07f-486c-98d9-535ed9705fbf%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="e8d8b-134">处理文件夹的操作。</span><span class="sxs-lookup"><span data-stu-id="e8d8b-134">Handles folder operations.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="e8d8b-135">头文件</span><span class="sxs-lookup"><span data-stu-id="e8d8b-135">Header files</span></span>

<span data-ttu-id="e8d8b-136">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="e8d8b-136">Mapidefs.h</span></span>
  
> <span data-ttu-id="e8d8b-137">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="e8d8b-137">Provides data type definitions.</span></span>
    
<span data-ttu-id="e8d8b-138">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="e8d8b-138">Mapitags.h</span></span>
  
> <span data-ttu-id="e8d8b-139">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="e8d8b-139">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="e8d8b-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e8d8b-140">See also</span></span>



[<span data-ttu-id="e8d8b-141">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="e8d8b-141">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="e8d8b-142">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="e8d8b-142">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="e8d8b-143">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="e8d8b-143">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="e8d8b-144">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="e8d8b-144">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

