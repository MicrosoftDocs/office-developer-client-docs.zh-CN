---
title: SkipBlock 流结构
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 2499587b-2a0e-4987-9bf7-591bef41b894
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 5a3367a15374234658fd9d10f3c2a5f3a191c80e
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33435542"
---
# <a name="skipblock-stream-structure"></a><span data-ttu-id="73473-103">SkipBlock 流结构</span><span class="sxs-lookup"><span data-stu-id="73473-103">SkipBlock Stream Structure</span></span>

  
  
<span data-ttu-id="73473-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="73473-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="73473-105">SkipBlock 流结构是一个以整数开头的数据块，该整数指定块的剩余部分的长度。</span><span class="sxs-lookup"><span data-stu-id="73473-105">A SkipBlock stream structure is a block of data that starts with an integer that specifies the length of the remaining part of the block.</span></span> <span data-ttu-id="73473-106">如果字段定义采用 PropDefV2 格式，则此流结构存在于 [FieldDefinition](fielddefinition-stream-structure.md) 流中。</span><span class="sxs-lookup"><span data-stu-id="73473-106">This stream structure exists in a [FieldDefinition](fielddefinition-stream-structure.md) stream if the field definition is in PropDefV2 format.</span></span> 
  
<span data-ttu-id="73473-107">SkipBlock 流结构的用途取决于其在 FieldDefinition 流的 SkipBlocks 数据元素中的一系列类似结构中的相对位置。</span><span class="sxs-lookup"><span data-stu-id="73473-107">The purpose of a SkipBlock stream structure depends on its relative location in a series of like structures in the SkipBlocks data element of a FieldDefinition stream.</span></span> <span data-ttu-id="73473-108">SkipBlocks 系列应至少包含一个终止系列的 SkipBlock 结构，并且 Size 数据元素等于 0。</span><span class="sxs-lookup"><span data-stu-id="73473-108">The SkipBlocks series should contain at least one SkipBlock structure that terminates the series and has the Size data element equal to 0.</span></span> <span data-ttu-id="73473-109">如果第一个结构不是终止结构 (即 Size 数据元素大于 0) ，则 Outlook 假定第一个结构在 Unicode (UTF-16) 中指定字段名称。</span><span class="sxs-lookup"><span data-stu-id="73473-109">If the first structure is not the terminating structure (that is, the Size data element is greater than 0), Outlook assumes the first structure specifies the field name in Unicode (UTF-16).</span></span>
  
<span data-ttu-id="73473-110">此流中的数据元素以小尾序字节顺序存储，并按下面指定的顺序彼此紧接。</span><span class="sxs-lookup"><span data-stu-id="73473-110">Data elements in this stream are stored in little-endian byte order, immediately following each other in the order specified below.</span></span>
  
- <span data-ttu-id="73473-111">大小：DWORD (4 字节) ，内容数据元素的大小（以字节数为单位）。</span><span class="sxs-lookup"><span data-stu-id="73473-111">Size: DWORD (4 bytes), the size, in number of bytes, of the Content data element.</span></span>
    
- <span data-ttu-id="73473-112">内容：BYTE 数组。</span><span class="sxs-lookup"><span data-stu-id="73473-112">Content: An array of BYTE.</span></span> <span data-ttu-id="73473-113">此数组的计数等于 Size 数据元素。</span><span class="sxs-lookup"><span data-stu-id="73473-113">The count of this array is equal to the Size data element.</span></span> <span data-ttu-id="73473-114">Content 数据元素的含义取决于 SkipBlock 结构在系列中的位置以及 Outlook。</span><span class="sxs-lookup"><span data-stu-id="73473-114">The meaning of the Content data element depends on the location of the SkipBlock structure in the series and the version of Outlook.</span></span> <span data-ttu-id="73473-115">如果第一个 SkipBlock 结构不是终止结构，Outlook将第一个 SkipBlock 结构视为在 Unicode 中指定字段名称的[FirstSkipBlockContent](firstskipblockcontent-stream-structure.md)流结构。</span><span class="sxs-lookup"><span data-stu-id="73473-115">If the first SkipBlock structure is not the terminating structure, Outlook considers the first SkipBlock structure as the [FirstSkipBlockContent](firstskipblockcontent-stream-structure.md) stream structure that specifies the field name in Unicode.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="73473-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="73473-116">See also</span></span>



[<span data-ttu-id="73473-117">Outlook项目和字段</span><span class="sxs-lookup"><span data-stu-id="73473-117">Outlook Items and Fields</span></span>](outlook-items-and-fields.md)
  
[<span data-ttu-id="73473-118">流结构</span><span class="sxs-lookup"><span data-stu-id="73473-118">Stream Structures</span></span>](stream-structures.md)
  
[<span data-ttu-id="73473-119">FieldDefinition 流结构</span><span class="sxs-lookup"><span data-stu-id="73473-119">FieldDefinition Stream Structure</span></span>](fielddefinition-stream-structure.md)
  
[<span data-ttu-id="73473-120">FirstSkipBlockContent 流结构</span><span class="sxs-lookup"><span data-stu-id="73473-120">FirstSkipBlockContent Stream Structure</span></span>](firstskipblockcontent-stream-structure.md)

