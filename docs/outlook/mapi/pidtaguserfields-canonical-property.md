---
title: PidTagUserFields 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: db3a6947-f640-43e8-a2df-71e96560fd81
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 680c9dd9db2743c031de7cda4673d7044ec533e8
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32360737"
---
# <a name="pidtaguserfields-canonical-property"></a><span data-ttu-id="29fe9-103">PidTagUserFields 规范属性</span><span class="sxs-lookup"><span data-stu-id="29fe9-103">PidTagUserFields Canonical Property</span></span>

  
  
<span data-ttu-id="29fe9-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="29fe9-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="29fe9-105">包含有关数据类型字段的名称、名称和其他信息。</span><span class="sxs-lookup"><span data-stu-id="29fe9-105">Contains the name, data type, and other information about a user-defined field.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="29fe9-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="29fe9-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="29fe9-107">PR_USERFIELDS</span><span class="sxs-lookup"><span data-stu-id="29fe9-107">PR_USERFIELDS</span></span>  <br/> |
|<span data-ttu-id="29fe9-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="29fe9-108">Identifier:</span></span>  <br/> |<span data-ttu-id="29fe9-109">0x36E3</span><span class="sxs-lookup"><span data-stu-id="29fe9-109">0x36E3</span></span>  <br/> |
|<span data-ttu-id="29fe9-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="29fe9-110">Data type:</span></span>  <br/> |<span data-ttu-id="29fe9-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="29fe9-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="29fe9-112">区域：</span><span class="sxs-lookup"><span data-stu-id="29fe9-112">Area:</span></span>  <br/> |<span data-ttu-id="29fe9-113">MAPI 文件夹</span><span class="sxs-lookup"><span data-stu-id="29fe9-113">MAPI folder</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="29fe9-114">备注</span><span class="sxs-lookup"><span data-stu-id="29fe9-114">Remarks</span></span>

<span data-ttu-id="29fe9-115">对于每个项，Outlook定义字段的定义存储在相应 **IMessage** 对象的 [PidLidPropertyDefinitionStream](pidlidpropertydefinitionstream-canonical-property.md)属性中。</span><span class="sxs-lookup"><span data-stu-id="29fe9-115">For each item, Outlook stores the definitions of all user-defined fields in the [PidLidPropertyDefinitionStream](pidlidpropertydefinitionstream-canonical-property.md) property of the corresponding **IMessage** object.</span></span> <span data-ttu-id="29fe9-116">**PidLidPropertyDefinitionStream** 属性包含一个称为 [PropertyDefinition](propertydefinition-stream-structure.md)的二进制流，其中包含字段定义。</span><span class="sxs-lookup"><span data-stu-id="29fe9-116">The **PidLidPropertyDefinitionStream** property contains a binary stream known as [PropertyDefinition](propertydefinition-stream-structure.md), which contains the field definitions.</span></span> <span data-ttu-id="29fe9-117">有关字段定义的流结构详细信息，请参阅 [Stream Structures](stream-structures.md)。</span><span class="sxs-lookup"><span data-stu-id="29fe9-117">For more information about stream structures for field definitions, see [Stream Structures](stream-structures.md).</span></span>
  
<span data-ttu-id="29fe9-118">对于每个文件夹，Outlook邮件类关联的邮件的 **PidTagUserFields** 属性中存储该文件夹中所有用户定义字段 IPC.MS。REN。USERFIELDS - 每个文件夹假定在其关联内容表中包含此类的邮件不超过一条。</span><span class="sxs-lookup"><span data-stu-id="29fe9-118">For each folder, Outlook stores the definitions of all user-defined fields in that folder in the **PidTagUserFields** property of an associated message of the message class IPC.MS.REN.USERFIELDS - each folder presumed to contain no more than one message of this class in its associated contents table.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="29fe9-119">文件夹中的用户定义字段集不一定与其中每个项中的用户定义字段集匹配。</span><span class="sxs-lookup"><span data-stu-id="29fe9-119">The set of user-defined fields in a folder may not necessarily match the sets of user-defined fields in each of its items.</span></span> 
  
<span data-ttu-id="29fe9-120">文件夹中的用户定义字段集显示在用户界面中Outlook位置，例如文件夹的字段选择器。</span><span class="sxs-lookup"><span data-stu-id="29fe9-120">The set of user-defined fields in a folder is displayed in various places in the Outlook UI, such as the folder's Field Chooser.</span></span> <span data-ttu-id="29fe9-121">邮件的 **PidTagUserFields** 属性包含二进制流 **FolderUserFields**，其中包含文件夹字段定义。</span><span class="sxs-lookup"><span data-stu-id="29fe9-121">The message's **PidTagUserFields** property contains a binary stream, **FolderUserFields**, which contains the folder field definitions.</span></span> <span data-ttu-id="29fe9-122">有关文件夹字段定义的流结构详细信息，请参阅 Folder Fields [Stream Structures](folder-fields-stream-structures.md) 和 [FolderUserFields Stream Sample](folderuserfields-stream-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="29fe9-122">For more information about stream structures for folder field definitions, see [Folder Fields Stream Structures](folder-fields-stream-structures.md) and the [FolderUserFields Stream Sample](folderuserfields-stream-sample.md).</span></span>
  
## <a name="section-heading"></a><span data-ttu-id="29fe9-123">节标题</span><span class="sxs-lookup"><span data-stu-id="29fe9-123">Section Heading</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="29fe9-124">协议规范</span><span class="sxs-lookup"><span data-stu-id="29fe9-124">Protocol specifications</span></span>

<span data-ttu-id="29fe9-125">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="29fe9-125">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="29fe9-126">提供属性集定义和对相关协议规范Exchange Server引用。</span><span class="sxs-lookup"><span data-stu-id="29fe9-126">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="29fe9-127">头文件</span><span class="sxs-lookup"><span data-stu-id="29fe9-127">Header files</span></span>

<span data-ttu-id="29fe9-128">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="29fe9-128">Mapidefs.h</span></span>
  
> <span data-ttu-id="29fe9-129">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="29fe9-129">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="29fe9-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="29fe9-130">See also</span></span>



[<span data-ttu-id="29fe9-131">Outlook项目和字段</span><span class="sxs-lookup"><span data-stu-id="29fe9-131">Outlook Items and Fields</span></span>](outlook-items-and-fields.md)
  
[<span data-ttu-id="29fe9-132">添加新字段User-Defined定义</span><span class="sxs-lookup"><span data-stu-id="29fe9-132">Add a Definition for a New User-Defined Field</span></span>](how-to-add-a-definition-for-a-new-user-defined-field.md)
  
[<span data-ttu-id="29fe9-133">PropertyDefinition Stream 示例</span><span class="sxs-lookup"><span data-stu-id="29fe9-133">PropertyDefinition Stream Sample</span></span>](propertydefinition-stream-sample.md)
  
[<span data-ttu-id="29fe9-134">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="29fe9-134">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="29fe9-135">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="29fe9-135">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="29fe9-136">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="29fe9-136">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="29fe9-137">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="29fe9-137">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

