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
# <a name="pidtagextendedfolderflags-canonical-property"></a><span data-ttu-id="4893f-103">PidTagExtendedFolderFlags 规范属性</span><span class="sxs-lookup"><span data-stu-id="4893f-103">PidTagExtendedFolderFlags Canonical Property</span></span>
 
<span data-ttu-id="4893f-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="4893f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="4893f-105">包含有关文件夹的扩展标志。</span><span class="sxs-lookup"><span data-stu-id="4893f-105">Contains extended flags about a folder.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="4893f-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="4893f-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="4893f-107">PR_EXTENDED_FOLDER_FLAGS</span><span class="sxs-lookup"><span data-stu-id="4893f-107">PR_EXTENDED_FOLDER_FLAGS</span></span>  <br/> |
|<span data-ttu-id="4893f-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="4893f-108">Identifier:</span></span>  <br/> |<span data-ttu-id="4893f-109">0x36DA</span><span class="sxs-lookup"><span data-stu-id="4893f-109">0x36DA</span></span>  <br/> |
|<span data-ttu-id="4893f-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="4893f-110">Data type:</span></span>  <br/> |<span data-ttu-id="4893f-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="4893f-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="4893f-112">区域：</span><span class="sxs-lookup"><span data-stu-id="4893f-112">Area:</span></span>  <br/> |<span data-ttu-id="4893f-113">MAPI 容器</span><span class="sxs-lookup"><span data-stu-id="4893f-113">MAPI container</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="4893f-114">注解</span><span class="sxs-lookup"><span data-stu-id="4893f-114">Remarks</span></span>

<span data-ttu-id="4893f-115">此属性是包含文件夹的编码子属性的二进制流。</span><span class="sxs-lookup"><span data-stu-id="4893f-115">This property is a binary stream that contains encoded sub-properties for the folder.</span></span> <span data-ttu-id="4893f-116">它被格式化为一系列可变长度的子项目。</span><span class="sxs-lookup"><span data-stu-id="4893f-116">It is formatted as a series of variable length sub items.</span></span> <span data-ttu-id="4893f-117">子项目的前8位是 ID 字段, 用于指示子项目表示的标志种类。</span><span class="sxs-lookup"><span data-stu-id="4893f-117">The first 8 bits of the sub item is an ID field, which indicates what kind of flag the sub item represents.</span></span> <span data-ttu-id="4893f-118">第二个8位是接下来的数据的字节数。</span><span class="sxs-lookup"><span data-stu-id="4893f-118">The second 8 bits is the number of bytes of data that follow.</span></span>
  
<span data-ttu-id="4893f-119">可能的 ID 值包括:</span><span class="sxs-lookup"><span data-stu-id="4893f-119">Possible ID values include:</span></span>
  
- <span data-ttu-id="4893f-120">Invalid</span><span class="sxs-lookup"><span data-stu-id="4893f-120">Invalid</span></span>
    
   <span data-ttu-id="4893f-121">不使用此值</span><span class="sxs-lookup"><span data-stu-id="4893f-121">Do not use this value</span></span>
    
- <span data-ttu-id="4893f-122">ExtendedFlags</span><span class="sxs-lookup"><span data-stu-id="4893f-122">ExtendedFlags</span></span>
    
   <span data-ttu-id="4893f-123">数据为四个字节的值, 格式为:</span><span class="sxs-lookup"><span data-stu-id="4893f-123">The data is a four byte value formatted as:</span></span>
    
   |<span data-ttu-id="4893f-124">**位数**</span><span class="sxs-lookup"><span data-stu-id="4893f-124">**Bits**</span></span>|<span data-ttu-id="4893f-125">**Description**</span><span class="sxs-lookup"><span data-stu-id="4893f-125">**Description**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="4893f-126">0-1</span><span class="sxs-lookup"><span data-stu-id="4893f-126">0-1</span></span>  <br/> |<span data-ttu-id="4893f-127">保留。</span><span class="sxs-lookup"><span data-stu-id="4893f-127">Reserved.</span></span>  <br/> |
   |<span data-ttu-id="4893f-128">双面</span><span class="sxs-lookup"><span data-stu-id="4893f-128">2</span></span>  <br/> |<span data-ttu-id="4893f-129">如果应用程序应显示策略说明, 则设置为0。</span><span class="sxs-lookup"><span data-stu-id="4893f-129">Set to 0 if the application should show a policy description.</span></span>  <br/> |
   |<span data-ttu-id="4893f-130">3-5</span><span class="sxs-lookup"><span data-stu-id="4893f-130">3-5</span></span>  <br/> |<span data-ttu-id="4893f-131">保留。</span><span class="sxs-lookup"><span data-stu-id="4893f-131">Reserved.</span></span>  <br/> |
   |<span data-ttu-id="4893f-132">6-7</span><span class="sxs-lookup"><span data-stu-id="4893f-132">6-7</span></span>  <br/> |<span data-ttu-id="4893f-133">控制文件夹中邮件数的显示。</span><span class="sxs-lookup"><span data-stu-id="4893f-133">Controls the display of the number of messages in the folder.</span></span>  <br/> <span data-ttu-id="4893f-134">0-使用默认设置</span><span class="sxs-lookup"><span data-stu-id="4893f-134">0 - Use the default setting</span></span>  <br/> <span data-ttu-id="4893f-135">1-使用未读邮件的数量</span><span class="sxs-lookup"><span data-stu-id="4893f-135">1 - Use the number of unread messages</span></span>  <br/> <span data-ttu-id="4893f-136">3-使用总邮件数</span><span class="sxs-lookup"><span data-stu-id="4893f-136">3 - Use the total number of messages</span></span>  <br/> |
   |<span data-ttu-id="4893f-137">8-31</span><span class="sxs-lookup"><span data-stu-id="4893f-137">8-31</span></span>  <br/> |<span data-ttu-id="4893f-138">保留。</span><span class="sxs-lookup"><span data-stu-id="4893f-138">Reserved.</span></span>  <br/> |
   
<span data-ttu-id="4893f-139">可以忽略保留的项目, 但必须保留现有值。</span><span class="sxs-lookup"><span data-stu-id="4893f-139">Reserved items can be ignored, but existing values must be preserved.</span></span>
    
- <span data-ttu-id="4893f-140">SearchFolderID</span><span class="sxs-lookup"><span data-stu-id="4893f-140">SearchFolderID</span></span>
    
   <span data-ttu-id="4893f-141">数据字段是一个16字节的字段。</span><span class="sxs-lookup"><span data-stu-id="4893f-141">The data field is a 16-byte field.</span></span> <span data-ttu-id="4893f-142">当应用程序创建持久搜索文件夹时, 它必须将文件夹中的此字段设置为与搜索文件夹消息中的**PR_WB_SF_TAG** ([PidTagSearchFolderId)](pidtagsearchfolderid-canonical-property.md)) 二进制属性相同的值。</span><span class="sxs-lookup"><span data-stu-id="4893f-142">When the application creates a persistent search folder, it must set this field on the folder to the same value as the **PR_WB_SF_TAG** ([PidTagSearchFolderId)](pidtagsearchfolderid-canonical-property.md)) binary property on the Search Folder Message.</span></span>
    
- <span data-ttu-id="4893f-143">ToDoFolderVersion</span><span class="sxs-lookup"><span data-stu-id="4893f-143">ToDoFolderVersion</span></span>
    
   <span data-ttu-id="4893f-144">数据字段是一个4字节的字段。</span><span class="sxs-lookup"><span data-stu-id="4893f-144">The data field is a 4-byte field.</span></span> <span data-ttu-id="4893f-145">当应用程序创建待办事项搜索文件夹时, 它必须将文件夹上此字段的值设置为小端字节的整数值 "0x000c0000":</span><span class="sxs-lookup"><span data-stu-id="4893f-145">When the application creates the to-do search folder, it must set the value of this field on the folder to the little-endian integer value of" 0x000c0000":</span></span>
    
## <a name="related-resources"></a><span data-ttu-id="4893f-146">相关资源</span><span class="sxs-lookup"><span data-stu-id="4893f-146">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="4893f-147">协议规范</span><span class="sxs-lookup"><span data-stu-id="4893f-147">Protocol specifications</span></span>

<span data-ttu-id="4893f-148">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="4893f-148">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="4893f-149">提供对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="4893f-149">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="4893f-150">[[毫秒-OXOCFG]](https://msdn.microsoft.com/library/7d466dd5-c156-4da9-9a01-75c78e7e1a67%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="4893f-150">[[MS-OXOCFG]](https://msdn.microsoft.com/library/7d466dd5-c156-4da9-9a01-75c78e7e1a67%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="4893f-151">指定客户端和服务器配置数据的位置和属性, 如共享类别列表和工作时间。</span><span class="sxs-lookup"><span data-stu-id="4893f-151">Specifies the location and properties of client and server configuration data, such as shared category lists and working hours.</span></span>
    
<span data-ttu-id="4893f-152">[[毫秒-OXOSRCH]](https://msdn.microsoft.com/library/c72e49b8-78c7-4483-ad65-e46e9133673b%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="4893f-152">[[MS-OXOSRCH]](https://msdn.microsoft.com/library/c72e49b8-78c7-4483-ad65-e46e9133673b%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="4893f-153">指定用于操作搜索文件夹列表配置的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="4893f-153">Specifies the properties and operations for manipulating a search folder list configuration.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="4893f-154">头文件</span><span class="sxs-lookup"><span data-stu-id="4893f-154">Header files</span></span>

<span data-ttu-id="4893f-155">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="4893f-155">Mapidefs.h</span></span>
  
> <span data-ttu-id="4893f-156">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="4893f-156">Provides data type definitions.</span></span>
    
<span data-ttu-id="4893f-157">Mapitags</span><span class="sxs-lookup"><span data-stu-id="4893f-157">Mapitags.h</span></span>
  
> <span data-ttu-id="4893f-158">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="4893f-158">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="4893f-159">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4893f-159">See also</span></span>

- [<span data-ttu-id="4893f-160">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="4893f-160">MAPI Properties</span></span>](mapi-properties.md)
- [<span data-ttu-id="4893f-161">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="4893f-161">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
- [<span data-ttu-id="4893f-162">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="4893f-162">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
- [<span data-ttu-id="4893f-163">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="4893f-163">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

