---
title: 为用户定义的新字段添加定义
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 183d3b86-4506-44da-bbfc-d6242ad89e57
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 2879299d152d8fea7690162ae55a22f337f5fd59
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33428163"
---
# <a name="add-a-definition-for-a-new-user-defined-field"></a><span data-ttu-id="8720f-103">为用户定义的新字段添加定义</span><span class="sxs-lookup"><span data-stu-id="8720f-103">Add a definition for a new user-defined field</span></span>
 
<span data-ttu-id="8720f-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="8720f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="8720f-105">将用户定义的字段添加到 Microsoft Outlook项时，会向相应的[PropertyDefinition](propertydefinition-stream-structure.md)流结构添加字段定义。</span><span class="sxs-lookup"><span data-stu-id="8720f-105">When you add a user-defined field to a Microsoft Outlook item, you add a field definition to the corresponding [PropertyDefinition](propertydefinition-stream-structure.md) stream structure.</span></span> <span data-ttu-id="8720f-106">使用以下过程向 PropertyDefinition 流结构添加新字段定义。</span><span class="sxs-lookup"><span data-stu-id="8720f-106">Use the following procedure to add a new field definition to a PropertyDefinition stream structure.</span></span> 
  
### <a name="to-add-a-definition-for-a-new-user-defined-field"></a><span data-ttu-id="8720f-107">为新的用户定义字段添加定义</span><span class="sxs-lookup"><span data-stu-id="8720f-107">To add a definition for a new user-defined field</span></span>

1. <span data-ttu-id="8720f-108">将 PropertyDefinition 流结构的现有字段定义复制到新的字段定义数组。</span><span class="sxs-lookup"><span data-stu-id="8720f-108">Copy the existing field definitions of the PropertyDefinition stream structure to a new field definitions array.</span></span> 
    
2. <span data-ttu-id="8720f-109">如果任何现有字段定义采用 PropDefV1 格式，请将其转换为 PropDefV2 格式。</span><span class="sxs-lookup"><span data-stu-id="8720f-109">If any existing field definitions are in the PropDefV1 format, convert them to the PropDefV2 format.</span></span> <span data-ttu-id="8720f-110">有关字段定义格式的信息，请参阅[PropertyDefinition Stream Structure](propertydefinition-stream-structure.md)和[FieldDefinition Stream Structure。](fielddefinition-stream-structure.md)</span><span class="sxs-lookup"><span data-stu-id="8720f-110">For more information about field definition formats, see [PropertyDefinition Stream Structure](propertydefinition-stream-structure.md) and [FieldDefinition Stream Structure](fielddefinition-stream-structure.md).</span></span>
    
3. <span data-ttu-id="8720f-111">创建 PropDefV2 格式的新用户定义字段的定义，并将其添加到数组中。</span><span class="sxs-lookup"><span data-stu-id="8720f-111">Create a definition of the new user-defined field in the PropDefV2 format and add it to the array.</span></span>
    
4. <span data-ttu-id="8720f-112">将 PropertyDefinition 流结构的 Version 元素设置为 0x0103（如果 Version 元素尚未设置为该值）。</span><span class="sxs-lookup"><span data-stu-id="8720f-112">Set the Version element of the PropertyDefinition stream structure as 0x0103, if the Version element has not been set to that value.</span></span>
    
5. <span data-ttu-id="8720f-113">将 FieldDefinitionCount 元素增加 1。</span><span class="sxs-lookup"><span data-stu-id="8720f-113">Increment the FieldDefinitionCount element by 1.</span></span>
    
6. <span data-ttu-id="8720f-114">将数组存储为 FieldDefinitions 元素的值。</span><span class="sxs-lookup"><span data-stu-id="8720f-114">Store the array as the value of the FieldDefinitions element.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="8720f-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8720f-115">See also</span></span>

- [<span data-ttu-id="8720f-116">PropertyDefinition 流结构</span><span class="sxs-lookup"><span data-stu-id="8720f-116">PropertyDefinition Stream Structure</span></span>](propertydefinition-stream-structure.md)

