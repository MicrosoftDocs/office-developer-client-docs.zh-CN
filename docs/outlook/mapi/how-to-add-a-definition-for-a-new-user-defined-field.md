---
title: 添加新用户定义的字段的定义
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 183d3b86-4506-44da-bbfc-d6242ad89e57
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 26c329323eebff6cfdf4f4be4dffe9a62f8745e6
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775080"
---
# <a name="add-a-definition-for-a-new-user-defined-field"></a><span data-ttu-id="31b2f-103">添加新用户定义的字段的定义</span><span class="sxs-lookup"><span data-stu-id="31b2f-103">Add a definition for a new user-defined field</span></span>
 
<span data-ttu-id="31b2f-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="31b2f-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="31b2f-105">当您向 Microsoft Outlook 项目中添加用户定义的字段时，您将字段定义添加到相应[属性定义](propertydefinition-stream-structure.md)流结构。</span><span class="sxs-lookup"><span data-stu-id="31b2f-105">When you add a user-defined field to a Microsoft Outlook item, you add a field definition to the corresponding [PropertyDefinition](propertydefinition-stream-structure.md) stream structure.</span></span> <span data-ttu-id="31b2f-106">使用以下过程将一个新的字段定义添加到属性定义流结构。</span><span class="sxs-lookup"><span data-stu-id="31b2f-106">Use the following procedure to add a new field definition to a PropertyDefinition stream structure.</span></span> 
  
### <a name="to-add-a-definition-for-a-new-user-defined-field"></a><span data-ttu-id="31b2f-107">若要添加新用户定义的字段的定义</span><span class="sxs-lookup"><span data-stu-id="31b2f-107">To add a definition for a new user-defined field</span></span>

1. <span data-ttu-id="31b2f-108">将现有的字段定义的属性定义流结构复制到新的字段定义数组。</span><span class="sxs-lookup"><span data-stu-id="31b2f-108">Copy the existing field definitions of the PropertyDefinition stream structure to a new field definitions array.</span></span> 
    
2. <span data-ttu-id="31b2f-109">如果任何现有的字段定义 PropDefV1 格式，则将其转换为 PropDefV2 格式。</span><span class="sxs-lookup"><span data-stu-id="31b2f-109">If any existing field definitions are in the PropDefV1 format, convert them to the PropDefV2 format.</span></span> <span data-ttu-id="31b2f-110">有关字段定义格式的详细信息，请参阅[属性定义流结构](propertydefinition-stream-structure.md)和[FieldDefinition 流结构](fielddefinition-stream-structure.md)。</span><span class="sxs-lookup"><span data-stu-id="31b2f-110">For more information about field definition formats, see [PropertyDefinition Stream Structure](propertydefinition-stream-structure.md) and [FieldDefinition Stream Structure](fielddefinition-stream-structure.md).</span></span>
    
3. <span data-ttu-id="31b2f-111">创建新用户定义的字段的定义 PropDefV2 格式并将其添加到数组。</span><span class="sxs-lookup"><span data-stu-id="31b2f-111">Create a definition of the new user-defined field in the PropDefV2 format and add it to the array.</span></span>
    
4. <span data-ttu-id="31b2f-112">如果尚未设置的 Version 元素的值，请将属性定义流结构的 Version 元素设置为 0x0103。</span><span class="sxs-lookup"><span data-stu-id="31b2f-112">Set the Version element of the PropertyDefinition stream structure as 0x0103, if the Version element has not been set to that value.</span></span>
    
5. <span data-ttu-id="31b2f-113">递增 1 FieldDefinitionCount 元素。</span><span class="sxs-lookup"><span data-stu-id="31b2f-113">Increment the FieldDefinitionCount element by 1.</span></span>
    
6. <span data-ttu-id="31b2f-114">存储为 FieldDefinitions 元素的值的数组。</span><span class="sxs-lookup"><span data-stu-id="31b2f-114">Store the array as the value of the FieldDefinitions element.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="31b2f-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="31b2f-115">See also</span></span>

- [<span data-ttu-id="31b2f-116">PropertyDefinition 流结构</span><span class="sxs-lookup"><span data-stu-id="31b2f-116">PropertyDefinition Stream Structure</span></span>](propertydefinition-stream-structure.md)

