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
ms.openlocfilehash: fe14f6ca101e6a546f99989ecc87b0c516ee5df4
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32316350"
---
# <a name="pidtagextendedfolderflags-canonical-property"></a><span data-ttu-id="ecb25-103">PidTagExtendedFolderFlags 规范属性</span><span class="sxs-lookup"><span data-stu-id="ecb25-103">PidTagExtendedFolderFlags Canonical Property</span></span>
 
<span data-ttu-id="ecb25-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ecb25-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ecb25-105">包含有关文件夹的扩展标志。</span><span class="sxs-lookup"><span data-stu-id="ecb25-105">Contains extended flags about a folder.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="ecb25-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="ecb25-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="ecb25-107">PR_EXTENDED_FOLDER_FLAGS</span><span class="sxs-lookup"><span data-stu-id="ecb25-107">PR_EXTENDED_FOLDER_FLAGS</span></span>  <br/> |
|<span data-ttu-id="ecb25-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="ecb25-108">Identifier:</span></span>  <br/> |<span data-ttu-id="ecb25-109">0x36DA</span><span class="sxs-lookup"><span data-stu-id="ecb25-109">0x36DA</span></span>  <br/> |
|<span data-ttu-id="ecb25-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="ecb25-110">Data type:</span></span>  <br/> |<span data-ttu-id="ecb25-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="ecb25-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="ecb25-112">区域：</span><span class="sxs-lookup"><span data-stu-id="ecb25-112">Area:</span></span>  <br/> |<span data-ttu-id="ecb25-113">MAPI 容器</span><span class="sxs-lookup"><span data-stu-id="ecb25-113">MAPI container</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="ecb25-114">备注</span><span class="sxs-lookup"><span data-stu-id="ecb25-114">Remarks</span></span>

<span data-ttu-id="ecb25-115">此属性是包含文件夹的编码子属性的二进制流。</span><span class="sxs-lookup"><span data-stu-id="ecb25-115">This property is a binary stream that contains encoded sub-properties for the folder.</span></span> <span data-ttu-id="ecb25-116">它的格式设置为一系列可变长度子项。</span><span class="sxs-lookup"><span data-stu-id="ecb25-116">It is formatted as a series of variable length sub items.</span></span> <span data-ttu-id="ecb25-117">子项的前 8 位是一个 ID 字段，它指示子项表示的标志类型。</span><span class="sxs-lookup"><span data-stu-id="ecb25-117">The first 8 bits of the sub item is an ID field, which indicates what kind of flag the sub item represents.</span></span> <span data-ttu-id="ecb25-118">第二个 8 位是后续数据字节数。</span><span class="sxs-lookup"><span data-stu-id="ecb25-118">The second 8 bits is the number of bytes of data that follow.</span></span>
  
<span data-ttu-id="ecb25-119">可能的 ID 值包括：</span><span class="sxs-lookup"><span data-stu-id="ecb25-119">Possible ID values include:</span></span>
  
- <span data-ttu-id="ecb25-120">Invalid</span><span class="sxs-lookup"><span data-stu-id="ecb25-120">Invalid</span></span>
    
   <span data-ttu-id="ecb25-121">请勿使用此值</span><span class="sxs-lookup"><span data-stu-id="ecb25-121">Do not use this value</span></span>
    
- <span data-ttu-id="ecb25-122">ExtendedFlags</span><span class="sxs-lookup"><span data-stu-id="ecb25-122">ExtendedFlags</span></span>
    
   <span data-ttu-id="ecb25-123">数据是四字节值，格式为：</span><span class="sxs-lookup"><span data-stu-id="ecb25-123">The data is a four byte value formatted as:</span></span>
    
   |<span data-ttu-id="ecb25-124">**位数**</span><span class="sxs-lookup"><span data-stu-id="ecb25-124">**Bits**</span></span>|<span data-ttu-id="ecb25-125">**说明**</span><span class="sxs-lookup"><span data-stu-id="ecb25-125">**Description**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="ecb25-126">0-1</span><span class="sxs-lookup"><span data-stu-id="ecb25-126">0-1</span></span>  <br/> |<span data-ttu-id="ecb25-127">保留。</span><span class="sxs-lookup"><span data-stu-id="ecb25-127">Reserved.</span></span>  <br/> |
   |<span data-ttu-id="ecb25-128">2</span><span class="sxs-lookup"><span data-stu-id="ecb25-128">2</span></span>  <br/> |<span data-ttu-id="ecb25-129">如果应用程序应显示策略说明，设置为 0。</span><span class="sxs-lookup"><span data-stu-id="ecb25-129">Set to 0 if the application should show a policy description.</span></span>  <br/> |
   |<span data-ttu-id="ecb25-130">3-5</span><span class="sxs-lookup"><span data-stu-id="ecb25-130">3-5</span></span>  <br/> |<span data-ttu-id="ecb25-131">保留。</span><span class="sxs-lookup"><span data-stu-id="ecb25-131">Reserved.</span></span>  <br/> |
   |<span data-ttu-id="ecb25-132">6-7</span><span class="sxs-lookup"><span data-stu-id="ecb25-132">6-7</span></span>  <br/> |<span data-ttu-id="ecb25-133">控制文件夹中邮件数量的显示。</span><span class="sxs-lookup"><span data-stu-id="ecb25-133">Controls the display of the number of messages in the folder.</span></span>  <br/> <span data-ttu-id="ecb25-134">0 - 使用默认设置</span><span class="sxs-lookup"><span data-stu-id="ecb25-134">0 - Use the default setting</span></span>  <br/> <span data-ttu-id="ecb25-135">1 - 使用未读邮件的数量</span><span class="sxs-lookup"><span data-stu-id="ecb25-135">1 - Use the number of unread messages</span></span>  <br/> <span data-ttu-id="ecb25-136">3 - 使用邮件总数</span><span class="sxs-lookup"><span data-stu-id="ecb25-136">3 - Use the total number of messages</span></span>  <br/> |
   |<span data-ttu-id="ecb25-137">8-31</span><span class="sxs-lookup"><span data-stu-id="ecb25-137">8-31</span></span>  <br/> |<span data-ttu-id="ecb25-138">保留。</span><span class="sxs-lookup"><span data-stu-id="ecb25-138">Reserved.</span></span>  <br/> |
   
<span data-ttu-id="ecb25-139">可以忽略保留项，但必须保留现有值。</span><span class="sxs-lookup"><span data-stu-id="ecb25-139">Reserved items can be ignored, but existing values must be preserved.</span></span>
    
- <span data-ttu-id="ecb25-140">SearchFolderID</span><span class="sxs-lookup"><span data-stu-id="ecb25-140">SearchFolderID</span></span>
    
   <span data-ttu-id="ecb25-141">数据字段是一个 16 字节字段。</span><span class="sxs-lookup"><span data-stu-id="ecb25-141">The data field is a 16-byte field.</span></span> <span data-ttu-id="ecb25-142">当应用程序创建永久搜索文件夹时，它必须将文件夹上的此字段设置为与搜索文件夹邮件的 **PR_WB_SF_TAG** ([PidTagSearchFolderId)](pidtagsearchfolderid-canonical-property.md)) 二进制属性相同的值。</span><span class="sxs-lookup"><span data-stu-id="ecb25-142">When the application creates a persistent search folder, it must set this field on the folder to the same value as the **PR_WB_SF_TAG** ([PidTagSearchFolderId)](pidtagsearchfolderid-canonical-property.md)) binary property on the Search Folder Message.</span></span>
    
- <span data-ttu-id="ecb25-143">ToDoFolderVersion</span><span class="sxs-lookup"><span data-stu-id="ecb25-143">ToDoFolderVersion</span></span>
    
   <span data-ttu-id="ecb25-144">数据字段是一个 4 字节字段。</span><span class="sxs-lookup"><span data-stu-id="ecb25-144">The data field is a 4-byte field.</span></span> <span data-ttu-id="ecb25-145">当应用程序创建"to-do"搜索文件夹时，它必须将文件夹上的此字段的值设置为"0x000c0000"的 little-endian 整数值：</span><span class="sxs-lookup"><span data-stu-id="ecb25-145">When the application creates the to-do search folder, it must set the value of this field on the folder to the little-endian integer value of" 0x000c0000":</span></span>
    
## <a name="related-resources"></a><span data-ttu-id="ecb25-146">相关资源</span><span class="sxs-lookup"><span data-stu-id="ecb25-146">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="ecb25-147">协议规范</span><span class="sxs-lookup"><span data-stu-id="ecb25-147">Protocol specifications</span></span>

<span data-ttu-id="ecb25-148">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="ecb25-148">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="ecb25-149">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="ecb25-149">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="ecb25-150">[[MS-OXOCFG]](https://msdn.microsoft.com/library/7d466dd5-c156-4da9-9a01-75c78e7e1a67%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="ecb25-150">[[MS-OXOCFG]](https://msdn.microsoft.com/library/7d466dd5-c156-4da9-9a01-75c78e7e1a67%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="ecb25-151">指定客户端和服务器配置数据的位置和属性，例如共享类别列表和工作时间。</span><span class="sxs-lookup"><span data-stu-id="ecb25-151">Specifies the location and properties of client and server configuration data, such as shared category lists and working hours.</span></span>
    
<span data-ttu-id="ecb25-152">[[MS-OXOSRCH]](https://msdn.microsoft.com/library/c72e49b8-78c7-4483-ad65-e46e9133673b%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="ecb25-152">[[MS-OXOSRCH]](https://msdn.microsoft.com/library/c72e49b8-78c7-4483-ad65-e46e9133673b%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="ecb25-153">指定用于操作搜索文件夹列表配置的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="ecb25-153">Specifies the properties and operations for manipulating a search folder list configuration.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="ecb25-154">头文件</span><span class="sxs-lookup"><span data-stu-id="ecb25-154">Header files</span></span>

<span data-ttu-id="ecb25-155">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="ecb25-155">Mapidefs.h</span></span>
  
> <span data-ttu-id="ecb25-156">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="ecb25-156">Provides data type definitions.</span></span>
    
<span data-ttu-id="ecb25-157">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="ecb25-157">Mapitags.h</span></span>
  
> <span data-ttu-id="ecb25-158">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="ecb25-158">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="ecb25-159">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ecb25-159">See also</span></span>

- [<span data-ttu-id="ecb25-160">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="ecb25-160">MAPI Properties</span></span>](mapi-properties.md)
- [<span data-ttu-id="ecb25-161">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="ecb25-161">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
- [<span data-ttu-id="ecb25-162">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="ecb25-162">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
- [<span data-ttu-id="ecb25-163">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="ecb25-163">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

