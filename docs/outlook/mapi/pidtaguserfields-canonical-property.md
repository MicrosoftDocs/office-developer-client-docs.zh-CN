---
title: PidTagUserFields 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: db3a6947-f640-43e8-a2df-71e96560fd81
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 5abfd9c98c5a83ca45792f094d0c9573b8affb85
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778522"
---
# <a name="pidtaguserfields-canonical-property"></a><span data-ttu-id="031ce-103">PidTagUserFields 规范属性</span><span class="sxs-lookup"><span data-stu-id="031ce-103">PidTagUserFields Canonical Property</span></span>

  
  
<span data-ttu-id="031ce-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="031ce-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="031ce-105">包含名称、 数据类型和用户定义的字段的其他信息。</span><span class="sxs-lookup"><span data-stu-id="031ce-105">Contains the name, data type, and other information about a user-defined field.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="031ce-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="031ce-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="031ce-107">PR_USERFIELDS</span><span class="sxs-lookup"><span data-stu-id="031ce-107">PR_USERFIELDS</span></span>  <br/> |
|<span data-ttu-id="031ce-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="031ce-108">Identifier:</span></span>  <br/> |<span data-ttu-id="031ce-109">0x36E3</span><span class="sxs-lookup"><span data-stu-id="031ce-109">0x36E3</span></span>  <br/> |
|<span data-ttu-id="031ce-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="031ce-110">Data type:</span></span>  <br/> |<span data-ttu-id="031ce-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="031ce-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="031ce-112">区域：</span><span class="sxs-lookup"><span data-stu-id="031ce-112">Area:</span></span>  <br/> |<span data-ttu-id="031ce-113">MAPI 文件夹</span><span class="sxs-lookup"><span data-stu-id="031ce-113">MAPI folder</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="031ce-114">备注</span><span class="sxs-lookup"><span data-stu-id="031ce-114">Remarks</span></span>

<span data-ttu-id="031ce-115">对于每个项，Outlook 相应**IMessage**对象的[PidLidPropertyDefinitionStream](pidlidpropertydefinitionstream-canonical-property.md)属性中存储所有用户定义的字段的定义。</span><span class="sxs-lookup"><span data-stu-id="031ce-115">For each item, Outlook stores the definitions of all user-defined fields in the [PidLidPropertyDefinitionStream](pidlidpropertydefinitionstream-canonical-property.md) property of the corresponding **IMessage** object.</span></span> <span data-ttu-id="031ce-116">**PidLidPropertyDefinitionStream**属性将包含二进制流称为[属性定义](propertydefinition-stream-structure.md)，其中包含的字段定义。</span><span class="sxs-lookup"><span data-stu-id="031ce-116">The **PidLidPropertyDefinitionStream** property contains a binary stream known as [PropertyDefinition](propertydefinition-stream-structure.md), which contains the field definitions.</span></span> <span data-ttu-id="031ce-117">有关字段定义流结构的详细信息，请参阅[流结构](stream-structures.md)。</span><span class="sxs-lookup"><span data-stu-id="031ce-117">For more information about stream structures for field definitions, see [Stream Structures](stream-structures.md).</span></span>
  
<span data-ttu-id="031ce-118">对于每个文件夹中，Outlook 将在该文件夹中的邮件类 IPC.MS 关联的邮件的**PidTagUserFields**属性存储所有用户定义的字段的定义。REN。USERFIELDS-每个文件夹假定包含不多个此类及其关联的内容表中的邮件。</span><span class="sxs-lookup"><span data-stu-id="031ce-118">For each folder, Outlook stores the definitions of all user-defined fields in that folder in the **PidTagUserFields** property of an associated message of the message class IPC.MS.REN.USERFIELDS - each folder presumed to contain no more than one message of this class in its associated contents table.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="031ce-119">一组的文件夹中的用户定义的字段不一定是匹配每个其项目中的用户定义的字段的集。</span><span class="sxs-lookup"><span data-stu-id="031ce-119">The set of user-defined fields in a folder may not necessarily match the sets of user-defined fields in each of its items.</span></span> 
  
<span data-ttu-id="031ce-120">中的不同位置的 Outlook UI，例如文件夹的字段选择器中显示的文件夹中的用户定义的字段集。</span><span class="sxs-lookup"><span data-stu-id="031ce-120">The set of user-defined fields in a folder is displayed in various places in the Outlook UI, such as the folder's Field Chooser.</span></span> <span data-ttu-id="031ce-121">消息的**PidTagUserFields**属性包含二进制数据流， **FolderUserFields**，其中包含的文件夹字段定义。</span><span class="sxs-lookup"><span data-stu-id="031ce-121">The message's **PidTagUserFields** property contains a binary stream, **FolderUserFields**, which contains the folder field definitions.</span></span> <span data-ttu-id="031ce-122">有关流结构文件夹字段定义的详细信息，请参阅[文件夹字段流结构](folder-fields-stream-structures.md)和[FolderUserFields 流示例](folderuserfields-stream-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="031ce-122">For more information about stream structures for folder field definitions, see [Folder Fields Stream Structures](folder-fields-stream-structures.md) and the [FolderUserFields Stream Sample](folderuserfields-stream-sample.md).</span></span>
  
## <a name="section-heading"></a><span data-ttu-id="031ce-123">节标题</span><span class="sxs-lookup"><span data-stu-id="031ce-123">Section Heading</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="031ce-124">协议规范</span><span class="sxs-lookup"><span data-stu-id="031ce-124">Protocol specifications</span></span>

<span data-ttu-id="031ce-125">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="031ce-125">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="031ce-126">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="031ce-126">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="031ce-127">头文件</span><span class="sxs-lookup"><span data-stu-id="031ce-127">Header files</span></span>

<span data-ttu-id="031ce-128">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="031ce-128">Mapidefs.h</span></span>
  
> <span data-ttu-id="031ce-129">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="031ce-129">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="031ce-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="031ce-130">See also</span></span>



[<span data-ttu-id="031ce-131">Outlook 项和计算字段</span><span class="sxs-lookup"><span data-stu-id="031ce-131">Outlook Items and Fields</span></span>](outlook-items-and-fields.md)
  
[<span data-ttu-id="031ce-132">添加用户定义的新字段的定义</span><span class="sxs-lookup"><span data-stu-id="031ce-132">Add a Definition for a New User-Defined Field</span></span>](how-to-add-a-definition-for-a-new-user-defined-field.md)
  
[<span data-ttu-id="031ce-133">属性定义流示例</span><span class="sxs-lookup"><span data-stu-id="031ce-133">PropertyDefinition Stream Sample</span></span>](propertydefinition-stream-sample.md)
  
[<span data-ttu-id="031ce-134">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="031ce-134">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="031ce-135">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="031ce-135">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="031ce-136">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="031ce-136">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="031ce-137">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="031ce-137">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

