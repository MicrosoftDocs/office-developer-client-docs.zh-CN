---
title: PropertyDefinition 流结构
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: ab677a06-6d7d-47e7-99ea-535b0b24389a
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 479339762867aa778bc8bc8baa1f21f6bc34b441
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32328481"
---
# <a name="propertydefinition-stream-structure"></a><span data-ttu-id="977fb-103">PropertyDefinition 流结构</span><span class="sxs-lookup"><span data-stu-id="977fb-103">PropertyDefinition stream structure</span></span>

<span data-ttu-id="977fb-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="977fb-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="977fb-105">PropertyDefinition 流结构是[FieldDefinition](fielddefinition-stream-structure.md)流结构的数组, 其中包含 Microsoft Outlook 项目中所有用户定义的字段的定义, 以及某些内置字段的数据绑定设置。</span><span class="sxs-lookup"><span data-stu-id="977fb-105">A PropertyDefinition stream structure is an array of [FieldDefinition](fielddefinition-stream-structure.md) stream structures that contain definitions for all user-defined fields in a Microsoft Outlook item, and data-binding settings for some built-in fields.</span></span> 
  
<span data-ttu-id="977fb-106">您可以以编程方式操作 PropertyDefinition 流结构。</span><span class="sxs-lookup"><span data-stu-id="977fb-106">You can programmatically manipulate the PropertyDefinition stream structure.</span></span> <span data-ttu-id="977fb-107">但是, 您可以使用 Outlook 窗体设计器来获得类似的结果, 并在数据绑定控件的 "**属性**" 对话框中进行查找。</span><span class="sxs-lookup"><span data-stu-id="977fb-107">However, you can achieve similar results by using the Outlook Forms Designer and, in particular, the **Properties** dialog box for a data-bound control.</span></span> 
  
<span data-ttu-id="977fb-108">PropertyDefinition 流结构中的字段定义可以是以下两种格式之一: PropDefV1 和 PropDefV2。</span><span class="sxs-lookup"><span data-stu-id="977fb-108">Field definitions in a PropertyDefinition stream structure can be one of two formats: PropDefV1 and PropDefV2.</span></span> <span data-ttu-id="977fb-109">Outlook 同时支持 PropDefV1 和 PropDefV2。</span><span class="sxs-lookup"><span data-stu-id="977fb-109">Outlook supports both PropDefV1 and PropDefV2.</span></span> <span data-ttu-id="977fb-110">一个 PropertyDefinition 流结构中的所有字段定义的格式必须相同。</span><span class="sxs-lookup"><span data-stu-id="977fb-110">All field definitions in a single PropertyDefinition stream structure must be of the same format.</span></span> <span data-ttu-id="977fb-111">有关 PropDefV1 和 PropDefV2 的不同之处的详细信息, 请参阅[FieldDefinition Stream Structure](fielddefinition-stream-structure.md)。</span><span class="sxs-lookup"><span data-stu-id="977fb-111">For more information about how PropDefV1 and PropDefV2 differ, see [FieldDefinition Stream Structure](fielddefinition-stream-structure.md).</span></span>
  
<span data-ttu-id="977fb-112">此流中的数据元素存储在小端字节序的字节顺序中, 紧跟在下面指定的顺序依次后续。</span><span class="sxs-lookup"><span data-stu-id="977fb-112">Data elements in this stream are stored in little-endian byte order, immediately following each other in the order specified below.</span></span>
  
- <span data-ttu-id="977fb-113">版本: WORD (2 个字节), PropertyDefinition 流结构中的字段定义的格式。</span><span class="sxs-lookup"><span data-stu-id="977fb-113">Version: WORD (2 bytes), the format of the field definitions in the PropertyDefinition stream structure.</span></span> <span data-ttu-id="977fb-114">下表显示可能的值。</span><span class="sxs-lookup"><span data-stu-id="977fb-114">The following table shows the possible values.</span></span>
    
    |<span data-ttu-id="977fb-115">**Value**</span><span class="sxs-lookup"><span data-stu-id="977fb-115">**Value**</span></span>|<span data-ttu-id="977fb-116">**说明**</span><span class="sxs-lookup"><span data-stu-id="977fb-116">**Description**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="977fb-117">0x0102</span><span class="sxs-lookup"><span data-stu-id="977fb-117">0x0102</span></span>  <br/> |<span data-ttu-id="977fb-118">格式为 PropDefV1。</span><span class="sxs-lookup"><span data-stu-id="977fb-118">Format is PropDefV1.</span></span>  <br/> |
    |<span data-ttu-id="977fb-119">0x0103</span><span class="sxs-lookup"><span data-stu-id="977fb-119">0x0103</span></span>  <br/> |<span data-ttu-id="977fb-120">格式为 PropDefV2。</span><span class="sxs-lookup"><span data-stu-id="977fb-120">Format is PropDefV2.</span></span>  <br/> |
   
- <span data-ttu-id="977fb-121">FieldDefinitionCount: DWORD (4 个字节), 此流中的字段定义数。</span><span class="sxs-lookup"><span data-stu-id="977fb-121">FieldDefinitionCount: DWORD (4 bytes), the number of field definitions in this stream.</span></span> <span data-ttu-id="977fb-122">这是 FieldDefinitions 数据元素中数组元素的计数。</span><span class="sxs-lookup"><span data-stu-id="977fb-122">This is the count of array elements in the FieldDefinitions data element.</span></span>
    
- <span data-ttu-id="977fb-123">FieldDefinitions: FieldDefinition 流结构的数组。</span><span class="sxs-lookup"><span data-stu-id="977fb-123">FieldDefinitions: An array of FieldDefinition stream structures.</span></span> <span data-ttu-id="977fb-124">此数组的计数等于 FieldDefinitionCount 数据元素。</span><span class="sxs-lookup"><span data-stu-id="977fb-124">The count of this array is equal to the FieldDefinitionCount data element.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="977fb-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="977fb-125">See also</span></span>

- [<span data-ttu-id="977fb-126">Outlook 项目和字段</span><span class="sxs-lookup"><span data-stu-id="977fb-126">Outlook Items and Fields</span></span>](outlook-items-and-fields.md)
- [<span data-ttu-id="977fb-127">为新的用户定义的字段添加定义</span><span class="sxs-lookup"><span data-stu-id="977fb-127">Add a Definition for a New User-Defined Field</span></span>](how-to-add-a-definition-for-a-new-user-defined-field.md)
- [<span data-ttu-id="977fb-128">PropertyDefinition 流示例</span><span class="sxs-lookup"><span data-stu-id="977fb-128">PropertyDefinition Stream Sample</span></span>](propertydefinition-stream-sample.md)
- [<span data-ttu-id="977fb-129">流结构</span><span class="sxs-lookup"><span data-stu-id="977fb-129">Stream Structures</span></span>](stream-structures.md)

