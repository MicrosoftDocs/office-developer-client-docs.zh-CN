---
title: PidTagExtendedFolderFlags 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagExtendedFolderFlags
api_type:
- HeaderDef
ms.assetid: e0c04f98-3d66-4ab5-ba05-69f9df539fcf
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 4a4d3c940539c23be8ec212cb85e3dd4f3a04aab
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777614"
---
# <a name="pidtagextendedfolderflags-canonical-property"></a><span data-ttu-id="f679a-103">PidTagExtendedFolderFlags 规范属性</span><span class="sxs-lookup"><span data-stu-id="f679a-103">PidTagExtendedFolderFlags Canonical Property</span></span>
 
<span data-ttu-id="f679a-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="f679a-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="f679a-105">包含有关文件夹扩展的标志。</span><span class="sxs-lookup"><span data-stu-id="f679a-105">Contains extended flags about a folder.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="f679a-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="f679a-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="f679a-107">PR_EXTENDED_FOLDER_FLAGS</span><span class="sxs-lookup"><span data-stu-id="f679a-107">PR_EXTENDED_FOLDER_FLAGS</span></span>  <br/> |
|<span data-ttu-id="f679a-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="f679a-108">Identifier:</span></span>  <br/> |<span data-ttu-id="f679a-109">0x36DA</span><span class="sxs-lookup"><span data-stu-id="f679a-109">0x36DA</span></span>  <br/> |
|<span data-ttu-id="f679a-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="f679a-110">Data type:</span></span>  <br/> |<span data-ttu-id="f679a-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="f679a-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="f679a-112">区域：</span><span class="sxs-lookup"><span data-stu-id="f679a-112">Area:</span></span>  <br/> |<span data-ttu-id="f679a-113">MAPI 容器</span><span class="sxs-lookup"><span data-stu-id="f679a-113">MAPI container</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="f679a-114">说明</span><span class="sxs-lookup"><span data-stu-id="f679a-114">Remarks</span></span>

<span data-ttu-id="f679a-115">此属性是包含文件夹的编码子属性的二进制流。</span><span class="sxs-lookup"><span data-stu-id="f679a-115">This property is a binary stream that contains encoded sub-properties for the folder.</span></span> <span data-ttu-id="f679a-116">它的格式设置为一系列的可变长度子项目。</span><span class="sxs-lookup"><span data-stu-id="f679a-116">It is formatted as a series of variable length sub items.</span></span> <span data-ttu-id="f679a-117">Sub 项目的第 8 位是标志的 ID 字段，这表明哪种类型 sub 该项表示。</span><span class="sxs-lookup"><span data-stu-id="f679a-117">The first 8 bits of the sub item is an ID field, which indicates what kind of flag the sub item represents.</span></span> <span data-ttu-id="f679a-118">第二个 8 位是按照的数据的字节数。</span><span class="sxs-lookup"><span data-stu-id="f679a-118">The second 8 bits is the number of bytes of data that follow.</span></span>
  
<span data-ttu-id="f679a-119">可能的 ID 值包括：</span><span class="sxs-lookup"><span data-stu-id="f679a-119">Possible ID values include:</span></span>
  
- <span data-ttu-id="f679a-120">Invalid</span><span class="sxs-lookup"><span data-stu-id="f679a-120">Invalid</span></span>
    
   <span data-ttu-id="f679a-121">不要使用此值</span><span class="sxs-lookup"><span data-stu-id="f679a-121">Do not use this value</span></span>
    
- <span data-ttu-id="f679a-122">ExtendedFlags</span><span class="sxs-lookup"><span data-stu-id="f679a-122">ExtendedFlags</span></span>
    
   <span data-ttu-id="f679a-123">数据是格式为四个字节的值：</span><span class="sxs-lookup"><span data-stu-id="f679a-123">The data is a four byte value formatted as:</span></span>
    
   |<span data-ttu-id="f679a-124">**Bits**</span><span class="sxs-lookup"><span data-stu-id="f679a-124">**Bits**</span></span>|<span data-ttu-id="f679a-125">**说明**</span><span class="sxs-lookup"><span data-stu-id="f679a-125">**Description**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="f679a-126">0-1</span><span class="sxs-lookup"><span data-stu-id="f679a-126">0-1</span></span>  <br/> |<span data-ttu-id="f679a-127">保留。</span><span class="sxs-lookup"><span data-stu-id="f679a-127">Reserved.</span></span>  <br/> |
   |<span data-ttu-id="f679a-128">2</span><span class="sxs-lookup"><span data-stu-id="f679a-128">2</span></span>  <br/> |<span data-ttu-id="f679a-129">如果应用程序应显示的策略说明，设置为 0。</span><span class="sxs-lookup"><span data-stu-id="f679a-129">Set to 0 if the application should show a policy description.</span></span>  <br/> |
   |<span data-ttu-id="f679a-130">3-5</span><span class="sxs-lookup"><span data-stu-id="f679a-130">3-5</span></span>  <br/> |<span data-ttu-id="f679a-131">保留。</span><span class="sxs-lookup"><span data-stu-id="f679a-131">Reserved.</span></span>  <br/> |
   |<span data-ttu-id="f679a-132">6-7</span><span class="sxs-lookup"><span data-stu-id="f679a-132">6-7</span></span>  <br/> |<span data-ttu-id="f679a-133">控件显示的文件夹中的消息数。</span><span class="sxs-lookup"><span data-stu-id="f679a-133">Controls the display of the number of messages in the folder.</span></span>  <br/> <span data-ttu-id="f679a-134">0-使用默认设置</span><span class="sxs-lookup"><span data-stu-id="f679a-134">0 - Use the default setting</span></span>  <br/> <span data-ttu-id="f679a-135">1-使用未读邮件数</span><span class="sxs-lookup"><span data-stu-id="f679a-135">1 - Use the number of unread messages</span></span>  <br/> <span data-ttu-id="f679a-136">3-使用消息的总数</span><span class="sxs-lookup"><span data-stu-id="f679a-136">3 - Use the total number of messages</span></span>  <br/> |
   |<span data-ttu-id="f679a-137">8-31</span><span class="sxs-lookup"><span data-stu-id="f679a-137">8-31</span></span>  <br/> |<span data-ttu-id="f679a-138">保留。</span><span class="sxs-lookup"><span data-stu-id="f679a-138">Reserved.</span></span>  <br/> |
   
<span data-ttu-id="f679a-139">可以忽略保留的项目，但必须保留现有的值。</span><span class="sxs-lookup"><span data-stu-id="f679a-139">Reserved items can be ignored, but existing values must be preserved.</span></span>
    
- <span data-ttu-id="f679a-140">SearchFolderID</span><span class="sxs-lookup"><span data-stu-id="f679a-140">SearchFolderID</span></span>
    
   <span data-ttu-id="f679a-141">数据字段是 16 字节字段。</span><span class="sxs-lookup"><span data-stu-id="f679a-141">The data field is a 16-byte field.</span></span> <span data-ttu-id="f679a-142">当应用程序创建永久搜索文件夹时，必须相同的值为**PR_WB_SF_TAG**文件夹上设置此字段 ([PidTagSearchFolderId)](pidtagsearchfolderid-canonical-property.md)) 上搜索文件夹消息二进制属性。</span><span class="sxs-lookup"><span data-stu-id="f679a-142">When the application creates a persistent search folder, it must set this field on the folder to the same value as the **PR_WB_SF_TAG** ([PidTagSearchFolderId)](pidtagsearchfolderid-canonical-property.md)) binary property on the Search Folder Message.</span></span>
    
- <span data-ttu-id="f679a-143">ToDoFolderVersion</span><span class="sxs-lookup"><span data-stu-id="f679a-143">ToDoFolderVersion</span></span>
    
   <span data-ttu-id="f679a-144">数据字段是 4 字节字段。</span><span class="sxs-lookup"><span data-stu-id="f679a-144">The data field is a 4-byte field.</span></span> <span data-ttu-id="f679a-145">当应用程序创建待办事项搜索文件夹时，必须为-little-endian 整数值的"0x000c0000"的文件夹设置此字段的值：</span><span class="sxs-lookup"><span data-stu-id="f679a-145">When the application creates the to-do search folder, it must set the value of this field on the folder to the little-endian integer value of" 0x000c0000":</span></span>
    
## <a name="related-resources"></a><span data-ttu-id="f679a-146">相关资源</span><span class="sxs-lookup"><span data-stu-id="f679a-146">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="f679a-147">协议规范</span><span class="sxs-lookup"><span data-stu-id="f679a-147">Protocol specifications</span></span>

<span data-ttu-id="f679a-148">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="f679a-148">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="f679a-149">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="f679a-149">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="f679a-150">[[MS OXOCFG]](http://msdn.microsoft.com/library/7d466dd5-c156-4da9-9a01-75c78e7e1a67%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="f679a-150">[[MS-OXOCFG]](http://msdn.microsoft.com/library/7d466dd5-c156-4da9-9a01-75c78e7e1a67%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="f679a-151">指定的位置和客户端和服务器配置数据，如共享的类别列表和工作时间的属性。</span><span class="sxs-lookup"><span data-stu-id="f679a-151">Specifies the location and properties of client and server configuration data, such as shared category lists and working hours.</span></span>
    
<span data-ttu-id="f679a-152">[[MS OXOSRCH]](http://msdn.microsoft.com/library/c72e49b8-78c7-4483-ad65-e46e9133673b%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="f679a-152">[[MS-OXOSRCH]](http://msdn.microsoft.com/library/c72e49b8-78c7-4483-ad65-e46e9133673b%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="f679a-153">指定的属性和操作的搜索文件夹列表配置的操作。</span><span class="sxs-lookup"><span data-stu-id="f679a-153">Specifies the properties and operations for manipulating a search folder list configuration.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="f679a-154">头文件</span><span class="sxs-lookup"><span data-stu-id="f679a-154">Header files</span></span>

<span data-ttu-id="f679a-155">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="f679a-155">Mapidefs.h</span></span>
  
> <span data-ttu-id="f679a-156">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="f679a-156">Provides data type definitions.</span></span>
    
<span data-ttu-id="f679a-157">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="f679a-157">Mapitags.h</span></span>
  
> <span data-ttu-id="f679a-158">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="f679a-158">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="f679a-159">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f679a-159">See also</span></span>

- [<span data-ttu-id="f679a-160">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="f679a-160">MAPI Properties</span></span>](mapi-properties.md)
- [<span data-ttu-id="f679a-161">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="f679a-161">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
- [<span data-ttu-id="f679a-162">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="f679a-162">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
- [<span data-ttu-id="f679a-163">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="f679a-163">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

