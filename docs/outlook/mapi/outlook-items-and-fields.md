---
title: Outlook 项和字段
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 605fab0f-c045-4d2b-a2da-447a111f66a9
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: caa231842c5fd51deb80144f12fdf53e51ccc980
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22582873"
---
# <a name="outlook-items-and-fields"></a><span data-ttu-id="daa5a-103">Outlook 项和字段</span><span class="sxs-lookup"><span data-stu-id="daa5a-103">Outlook Items and Fields</span></span>

  
  
<span data-ttu-id="daa5a-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="daa5a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="daa5a-105">Microsoft Outlook 提供了专用于他们的功能 （例如邮件项目、 约会、 联系人、 任务和 notes） 的项目类型。</span><span class="sxs-lookup"><span data-stu-id="daa5a-105">Microsoft Outlook provides item types that are specialized for their functionality (for example, mail items, appointments, contacts, tasks, and notes).</span></span> <span data-ttu-id="daa5a-106">Outlook 提供了每种类型的项目，通常称作内置字段的标准字段。</span><span class="sxs-lookup"><span data-stu-id="daa5a-106">Outlook provides standard fields for each type of item, commonly referred to as built-in fields.</span></span> <span data-ttu-id="daa5a-107">Outlook 还允许用户创建自定义字段，通常称作用户定义的字段。</span><span class="sxs-lookup"><span data-stu-id="daa5a-107">Outlook also allows users to create custom fields, commonly referred to as user-defined fields.</span></span> <span data-ttu-id="daa5a-108">每个字段相关联的数据类型和值。</span><span class="sxs-lookup"><span data-stu-id="daa5a-108">Each field is associated with a data type and a value.</span></span> <span data-ttu-id="daa5a-109">数据类型的示例是**货币**、**日期/时间**、**持续时间**、**整数**、**关键字**和**文本**。</span><span class="sxs-lookup"><span data-stu-id="daa5a-109">Examples of data types are **Currency**, **Date/Time**, **Duration**, **Integer**, **Keywords**, and **Text**.</span></span> <span data-ttu-id="daa5a-110">用户可以通过在 Outlook 中使用窗体设计器中定义自定义字段。</span><span class="sxs-lookup"><span data-stu-id="daa5a-110">Users can define custom fields by using the Forms Designer in Outlook.</span></span>
  
<span data-ttu-id="daa5a-111">可编程性级别由[IMessage](imessageimapiprop.md)对象表示每个项目。</span><span class="sxs-lookup"><span data-stu-id="daa5a-111">At the programmability level, each item is represented by an [IMessage](imessageimapiprop.md) object.</span></span> <span data-ttu-id="daa5a-112">用户定义的每个字段相关联的字段定义和值。</span><span class="sxs-lookup"><span data-stu-id="daa5a-112">Each user-defined field is associated with a field definition and a value.</span></span> 
  
### <a name="field-definition"></a><span data-ttu-id="daa5a-113">字段定义</span><span class="sxs-lookup"><span data-stu-id="daa5a-113">Field Definition</span></span>

<span data-ttu-id="daa5a-114">字段定义包括名称、 数据类型和字段的其他信息。</span><span class="sxs-lookup"><span data-stu-id="daa5a-114">A field definition includes the name, data type, and other information about the field.</span></span> <span data-ttu-id="daa5a-115">对于每个项，Outlook 相应**IMessage**对象的[PidLidPropertyDefinitionStream](pidlidpropertydefinitionstream-canonical-property.md)属性中存储所有用户定义的字段的定义。</span><span class="sxs-lookup"><span data-stu-id="daa5a-115">For each item, Outlook stores the definitions of all user-defined fields in the [PidLidPropertyDefinitionStream](pidlidpropertydefinitionstream-canonical-property.md) property of the corresponding **IMessage** object.</span></span> <span data-ttu-id="daa5a-116">**PidLidPropertyDefinitionStream**属性将包含二进制流称为[属性定义](propertydefinition-stream-structure.md)包含的字段定义。</span><span class="sxs-lookup"><span data-stu-id="daa5a-116">The **PidLidPropertyDefinitionStream** property contains a binary stream known as [PropertyDefinition](propertydefinition-stream-structure.md) that contains the field definitions.</span></span> <span data-ttu-id="daa5a-117">有关字段定义流结构的详细信息，请参阅[流结构](stream-structures.md)。</span><span class="sxs-lookup"><span data-stu-id="daa5a-117">For more information about stream structures for field definitions, see [Stream Structures](stream-structures.md).</span></span>
  
### <a name="field-value"></a><span data-ttu-id="daa5a-118">域值</span><span class="sxs-lookup"><span data-stu-id="daa5a-118">Field Value</span></span>

<span data-ttu-id="daa5a-119">项目的每个用户定义的字段有一个相应的命名属性中存储的值。</span><span class="sxs-lookup"><span data-stu-id="daa5a-119">Each user-defined field of an item has a value that is stored in a corresponding named property.</span></span> <span data-ttu-id="daa5a-120">命名属性位于 PS_PUBLIC_STRINGS 属性集，并具有与属性名称 Unicode 字符串。</span><span class="sxs-lookup"><span data-stu-id="daa5a-120">That named property is in the PS_PUBLIC_STRINGS property set, and has a Unicode character string as the property name.</span></span> <span data-ttu-id="daa5a-121">属性的数据类型对应于字段类型。</span><span class="sxs-lookup"><span data-stu-id="daa5a-121">The data type of the property corresponds to the type of the field.</span></span> <span data-ttu-id="daa5a-122">如果该属性不存在**IMessage**对象中，Outlook 将假定属性的合理的默认值。</span><span class="sxs-lookup"><span data-stu-id="daa5a-122">If the property is not present in the **IMessage** object, Outlook assumes a reasonable default value for the property.</span></span> <span data-ttu-id="daa5a-123">例如，string 类型，Outlook 假定为空字符串如果属性不存在。</span><span class="sxs-lookup"><span data-stu-id="daa5a-123">For example, for a string type, Outlook assumes an empty string if the property is not present.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="daa5a-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="daa5a-124">See also</span></span>



[<span data-ttu-id="daa5a-125">为新的用户定义字段添加定义</span><span class="sxs-lookup"><span data-stu-id="daa5a-125">Add a Definition for a New User-Defined Field</span></span>](how-to-add-a-definition-for-a-new-user-defined-field.md)
  
[<span data-ttu-id="daa5a-126">PropertyDefinition 流示例</span><span class="sxs-lookup"><span data-stu-id="daa5a-126">PropertyDefinition Stream Sample</span></span>](propertydefinition-stream-sample.md)
  
[<span data-ttu-id="daa5a-127">流结构</span><span class="sxs-lookup"><span data-stu-id="daa5a-127">Stream Structures</span></span>](stream-structures.md)
  
[<span data-ttu-id="daa5a-128">PropertyDefinition 流结构</span><span class="sxs-lookup"><span data-stu-id="daa5a-128">PropertyDefinition Stream Structure</span></span>](propertydefinition-stream-structure.md)
  
[<span data-ttu-id="daa5a-129">FieldDefinition 流结构</span><span class="sxs-lookup"><span data-stu-id="daa5a-129">FieldDefinition Stream Structure</span></span>](fielddefinition-stream-structure.md)
  
[<span data-ttu-id="daa5a-130">SkipBlock 流结构</span><span class="sxs-lookup"><span data-stu-id="daa5a-130">SkipBlock Stream Structure</span></span>](skipblock-stream-structure.md)
  
[<span data-ttu-id="daa5a-131">FirstSkipBlockContent 流结构</span><span class="sxs-lookup"><span data-stu-id="daa5a-131">FirstSkipBlockContent Stream Structure</span></span>](firstskipblockcontent-stream-structure.md)
  
[<span data-ttu-id="daa5a-132">PackedAnsiString 流结构</span><span class="sxs-lookup"><span data-stu-id="daa5a-132">PackedAnsiString Stream Structure</span></span>](packedansistring-stream-structure.md)
  
[<span data-ttu-id="daa5a-133">PackedUnicodeString 流结构</span><span class="sxs-lookup"><span data-stu-id="daa5a-133">PackedUnicodeString Stream Structure</span></span>](packedunicodestring-stream-structure.md)

