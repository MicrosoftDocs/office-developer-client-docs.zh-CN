---
title: Outlook项目和字段
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 605fab0f-c045-4d2b-a2da-447a111f66a9
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: b40752d4a5f445368752ad4caf5c919f6e0ce27b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33409116"
---
# <a name="outlook-items-and-fields"></a><span data-ttu-id="5f5bd-103">Outlook项目和字段</span><span class="sxs-lookup"><span data-stu-id="5f5bd-103">Outlook Items and Fields</span></span>

  
  
<span data-ttu-id="5f5bd-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="5f5bd-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="5f5bd-105">Microsoft Outlook 提供了专门用于其功能的项目类型 (例如，邮件项目、约会、联系人、任务和注释) 。</span><span class="sxs-lookup"><span data-stu-id="5f5bd-105">Microsoft Outlook provides item types that are specialized for their functionality (for example, mail items, appointments, contacts, tasks, and notes).</span></span> <span data-ttu-id="5f5bd-106">Outlook为每种项目类型提供标准字段，通常称为内置字段。</span><span class="sxs-lookup"><span data-stu-id="5f5bd-106">Outlook provides standard fields for each type of item, commonly referred to as built-in fields.</span></span> <span data-ttu-id="5f5bd-107">Outlook还允许用户创建自定义字段，通常称为用户定义的字段。</span><span class="sxs-lookup"><span data-stu-id="5f5bd-107">Outlook also allows users to create custom fields, commonly referred to as user-defined fields.</span></span> <span data-ttu-id="5f5bd-108">每个字段都与一个数据类型和一个值关联。</span><span class="sxs-lookup"><span data-stu-id="5f5bd-108">Each field is associated with a data type and a value.</span></span> <span data-ttu-id="5f5bd-109">数据类型的示例包括 Currency、Date/Time、Duration、Integer、Keywords 和 **Text。**     </span><span class="sxs-lookup"><span data-stu-id="5f5bd-109">Examples of data types are **Currency**, **Date/Time**, **Duration**, **Integer**, **Keywords**, and **Text**.</span></span> <span data-ttu-id="5f5bd-110">用户可以通过使用窗体设计器定义自定义Outlook。</span><span class="sxs-lookup"><span data-stu-id="5f5bd-110">Users can define custom fields by using the Forms Designer in Outlook.</span></span>
  
<span data-ttu-id="5f5bd-111">在可编程性级别，每个项目都由 [IMessage 对象](imessageimapiprop.md) 表示。</span><span class="sxs-lookup"><span data-stu-id="5f5bd-111">At the programmability level, each item is represented by an [IMessage](imessageimapiprop.md) object.</span></span> <span data-ttu-id="5f5bd-112">每个用户定义的字段都与字段定义和值相关联。</span><span class="sxs-lookup"><span data-stu-id="5f5bd-112">Each user-defined field is associated with a field definition and a value.</span></span> 
  
### <a name="field-definition"></a><span data-ttu-id="5f5bd-113">字段定义</span><span class="sxs-lookup"><span data-stu-id="5f5bd-113">Field Definition</span></span>

<span data-ttu-id="5f5bd-114">字段定义包括名称、数据类型和其他有关字段的信息。</span><span class="sxs-lookup"><span data-stu-id="5f5bd-114">A field definition includes the name, data type, and other information about the field.</span></span> <span data-ttu-id="5f5bd-115">对于每个项，Outlook定义字段的定义存储在相应 **IMessage** 对象的 [PidLidPropertyDefinitionStream](pidlidpropertydefinitionstream-canonical-property.md)属性中。</span><span class="sxs-lookup"><span data-stu-id="5f5bd-115">For each item, Outlook stores the definitions of all user-defined fields in the [PidLidPropertyDefinitionStream](pidlidpropertydefinitionstream-canonical-property.md) property of the corresponding **IMessage** object.</span></span> <span data-ttu-id="5f5bd-116">**PidLidPropertyDefinitionStream** 属性包含一个称为 [PropertyDefinition](propertydefinition-stream-structure.md)的二进制流，其中包含字段定义。</span><span class="sxs-lookup"><span data-stu-id="5f5bd-116">The **PidLidPropertyDefinitionStream** property contains a binary stream known as [PropertyDefinition](propertydefinition-stream-structure.md) that contains the field definitions.</span></span> <span data-ttu-id="5f5bd-117">有关字段定义的流结构详细信息，请参阅 [Stream Structures](stream-structures.md)。</span><span class="sxs-lookup"><span data-stu-id="5f5bd-117">For more information about stream structures for field definitions, see [Stream Structures](stream-structures.md).</span></span>
  
### <a name="field-value"></a><span data-ttu-id="5f5bd-118">域值</span><span class="sxs-lookup"><span data-stu-id="5f5bd-118">Field Value</span></span>

<span data-ttu-id="5f5bd-119">项目的每个用户定义的字段都有一个值，该值存储在相应的命名属性中。</span><span class="sxs-lookup"><span data-stu-id="5f5bd-119">Each user-defined field of an item has a value that is stored in a corresponding named property.</span></span> <span data-ttu-id="5f5bd-120">该命名属性位于PS_PUBLIC_STRINGS集内，并且具有一个 Unicode 字符串作为属性名称。</span><span class="sxs-lookup"><span data-stu-id="5f5bd-120">That named property is in the PS_PUBLIC_STRINGS property set, and has a Unicode character string as the property name.</span></span> <span data-ttu-id="5f5bd-121">属性数据类型对应于字段的类型。</span><span class="sxs-lookup"><span data-stu-id="5f5bd-121">The data type of the property corresponds to the type of the field.</span></span> <span data-ttu-id="5f5bd-122">如果 **IMessage** 对象中不存在该属性，则Outlook假定属性的默认值合理。</span><span class="sxs-lookup"><span data-stu-id="5f5bd-122">If the property is not present in the **IMessage** object, Outlook assumes a reasonable default value for the property.</span></span> <span data-ttu-id="5f5bd-123">例如，对于字符串类型，Outlook属性不存在时假定为空字符串。</span><span class="sxs-lookup"><span data-stu-id="5f5bd-123">For example, for a string type, Outlook assumes an empty string if the property is not present.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="5f5bd-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5f5bd-124">See also</span></span>



[<span data-ttu-id="5f5bd-125">添加新字段User-Defined定义</span><span class="sxs-lookup"><span data-stu-id="5f5bd-125">Add a Definition for a New User-Defined Field</span></span>](how-to-add-a-definition-for-a-new-user-defined-field.md)
  
[<span data-ttu-id="5f5bd-126">PropertyDefinition Stream 示例</span><span class="sxs-lookup"><span data-stu-id="5f5bd-126">PropertyDefinition Stream Sample</span></span>](propertydefinition-stream-sample.md)
  
[<span data-ttu-id="5f5bd-127">流结构</span><span class="sxs-lookup"><span data-stu-id="5f5bd-127">Stream Structures</span></span>](stream-structures.md)
  
[<span data-ttu-id="5f5bd-128">PropertyDefinition 流结构</span><span class="sxs-lookup"><span data-stu-id="5f5bd-128">PropertyDefinition Stream Structure</span></span>](propertydefinition-stream-structure.md)
  
[<span data-ttu-id="5f5bd-129">FieldDefinition 流结构</span><span class="sxs-lookup"><span data-stu-id="5f5bd-129">FieldDefinition Stream Structure</span></span>](fielddefinition-stream-structure.md)
  
[<span data-ttu-id="5f5bd-130">SkipBlock 流结构</span><span class="sxs-lookup"><span data-stu-id="5f5bd-130">SkipBlock Stream Structure</span></span>](skipblock-stream-structure.md)
  
[<span data-ttu-id="5f5bd-131">FirstSkipBlockContent 流结构</span><span class="sxs-lookup"><span data-stu-id="5f5bd-131">FirstSkipBlockContent Stream Structure</span></span>](firstskipblockcontent-stream-structure.md)
  
[<span data-ttu-id="5f5bd-132">PackedAnsiString 流结构</span><span class="sxs-lookup"><span data-stu-id="5f5bd-132">PackedAnsiString Stream Structure</span></span>](packedansistring-stream-structure.md)
  
[<span data-ttu-id="5f5bd-133">PackedUnicodeString 流结构</span><span class="sxs-lookup"><span data-stu-id="5f5bd-133">PackedUnicodeString Stream Structure</span></span>](packedunicodestring-stream-structure.md)

