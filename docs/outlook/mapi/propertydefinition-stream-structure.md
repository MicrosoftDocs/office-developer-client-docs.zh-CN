---
title: 属性定义流结构
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: ab677a06-6d7d-47e7-99ea-535b0b24389a
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 289227ee171c2325cad0ed321dab4f635a0ca724
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778582"
---
# <a name="propertydefinition-stream-structure"></a><span data-ttu-id="d3921-103">属性定义流结构</span><span class="sxs-lookup"><span data-stu-id="d3921-103">PropertyDefinition stream structure</span></span>

<span data-ttu-id="d3921-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="d3921-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="d3921-105">属性定义流结构是包含在 Microsoft Outlook 项目中，所有用户定义的字段定义和一些内置字段的数据绑定设置[FieldDefinition](fielddefinition-stream-structure.md)流结构的数组。</span><span class="sxs-lookup"><span data-stu-id="d3921-105">A PropertyDefinition stream structure is an array of [FieldDefinition](fielddefinition-stream-structure.md) stream structures that contain definitions for all user-defined fields in a Microsoft Outlook item, and data-binding settings for some built-in fields.</span></span> 
  
<span data-ttu-id="d3921-106">您可以编程方式处理属性定义流结构。</span><span class="sxs-lookup"><span data-stu-id="d3921-106">You can programmatically manipulate the PropertyDefinition stream structure.</span></span> <span data-ttu-id="d3921-107">但是，您可以通过使用 Outlook 窗体设计器来实现类似的结果，并且**属性**对话框，尤其是数据绑定控件框。</span><span class="sxs-lookup"><span data-stu-id="d3921-107">However, you can achieve similar results by using the Outlook Forms Designer and, in particular, the **Properties** dialog box for a data-bound control.</span></span> 
  
<span data-ttu-id="d3921-108">在属性定义流结构中的字段定义可为以下两种格式之一： PropDefV1 和 PropDefV2。</span><span class="sxs-lookup"><span data-stu-id="d3921-108">Field definitions in a PropertyDefinition stream structure can be one of two formats: PropDefV1 and PropDefV2.</span></span> <span data-ttu-id="d3921-109">Outlook 支持 PropDefV1 和 PropDefV2。</span><span class="sxs-lookup"><span data-stu-id="d3921-109">Outlook supports both PropDefV1 and PropDefV2.</span></span> <span data-ttu-id="d3921-110">在单个属性定义流结构中的所有字段定义都必须属于相同的格式。</span><span class="sxs-lookup"><span data-stu-id="d3921-110">All field definitions in a single PropertyDefinition stream structure must be of the same format.</span></span> <span data-ttu-id="d3921-111">有关如何 PropDefV1 和 PropDefV2 不同的详细信息，请参阅[FieldDefinition 流结构](fielddefinition-stream-structure.md)。</span><span class="sxs-lookup"><span data-stu-id="d3921-111">For more information about how PropDefV1 and PropDefV2 differ, see [FieldDefinition Stream Structure](fielddefinition-stream-structure.md).</span></span>
  
<span data-ttu-id="d3921-112">此流中的数据元素存储在-little-endian 字节的顺序，紧跟彼此下面指定的顺序。</span><span class="sxs-lookup"><span data-stu-id="d3921-112">Data elements in this stream are stored in little-endian byte order, immediately following each other in the order specified below.</span></span>
  
- <span data-ttu-id="d3921-113">版本： WORD （2 个字节） 属性定义中的字段定义的格式 stream 结构。</span><span class="sxs-lookup"><span data-stu-id="d3921-113">Version: WORD (2 bytes), the format of the field definitions in the PropertyDefinition stream structure.</span></span> <span data-ttu-id="d3921-114">下表显示可能的值。</span><span class="sxs-lookup"><span data-stu-id="d3921-114">The following table shows the possible values.</span></span>
    
    |<span data-ttu-id="d3921-115">**值**</span><span class="sxs-lookup"><span data-stu-id="d3921-115">**Value**</span></span>|<span data-ttu-id="d3921-116">**说明**</span><span class="sxs-lookup"><span data-stu-id="d3921-116">**Description**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="d3921-117">0x0102</span><span class="sxs-lookup"><span data-stu-id="d3921-117">0x0102</span></span>  <br/> |<span data-ttu-id="d3921-118">格式为 PropDefV1。</span><span class="sxs-lookup"><span data-stu-id="d3921-118">Format is PropDefV1.</span></span>  <br/> |
    |<span data-ttu-id="d3921-119">0x0103</span><span class="sxs-lookup"><span data-stu-id="d3921-119">0x0103</span></span>  <br/> |<span data-ttu-id="d3921-120">格式为 PropDefV2。</span><span class="sxs-lookup"><span data-stu-id="d3921-120">Format is PropDefV2.</span></span>  <br/> |
   
- <span data-ttu-id="d3921-121">FieldDefinitionCount: DWORD （4 个字节），此流中的字段定义的数目。</span><span class="sxs-lookup"><span data-stu-id="d3921-121">FieldDefinitionCount: DWORD (4 bytes), the number of field definitions in this stream.</span></span> <span data-ttu-id="d3921-122">这是 FieldDefinitions data 元素中的数组元素的计数。</span><span class="sxs-lookup"><span data-stu-id="d3921-122">This is the count of array elements in the FieldDefinitions data element.</span></span>
    
- <span data-ttu-id="d3921-123">FieldDefinitions: FieldDefinition 流结构的数组。</span><span class="sxs-lookup"><span data-stu-id="d3921-123">FieldDefinitions: An array of FieldDefinition stream structures.</span></span> <span data-ttu-id="d3921-124">此数组的计数等于 FieldDefinitionCount 数据元素。</span><span class="sxs-lookup"><span data-stu-id="d3921-124">The count of this array is equal to the FieldDefinitionCount data element.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="d3921-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d3921-125">See also</span></span>

- [<span data-ttu-id="d3921-126">Outlook 项和字段</span><span class="sxs-lookup"><span data-stu-id="d3921-126">Outlook Items and Fields</span></span>](outlook-items-and-fields.md)
- [<span data-ttu-id="d3921-127">为新的用户定义字段添加定义</span><span class="sxs-lookup"><span data-stu-id="d3921-127">Add a Definition for a New User-Defined Field</span></span>](how-to-add-a-definition-for-a-new-user-defined-field.md)
- [<span data-ttu-id="d3921-128">PropertyDefinition 流示例</span><span class="sxs-lookup"><span data-stu-id="d3921-128">PropertyDefinition Stream Sample</span></span>](propertydefinition-stream-sample.md)
- [<span data-ttu-id="d3921-129">流结构</span><span class="sxs-lookup"><span data-stu-id="d3921-129">Stream Structures</span></span>](stream-structures.md)

