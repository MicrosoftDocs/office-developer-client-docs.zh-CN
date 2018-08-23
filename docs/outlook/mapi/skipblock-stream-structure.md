---
title: SkipBlock 流结构
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 2499587b-2a0e-4987-9bf7-591bef41b894
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: b7be498473ef86b11006702f85089f0f95bb2e37
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22580899"
---
# <a name="skipblock-stream-structure"></a><span data-ttu-id="0815d-103">SkipBlock 流结构</span><span class="sxs-lookup"><span data-stu-id="0815d-103">SkipBlock Stream Structure</span></span>

  
  
<span data-ttu-id="0815d-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="0815d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="0815d-105">SkipBlock 流结构是开头一个整数，指定的块的剩余部分的长度的数据块。</span><span class="sxs-lookup"><span data-stu-id="0815d-105">A SkipBlock stream structure is a block of data that starts with an integer that specifies the length of the remaining part of the block.</span></span> <span data-ttu-id="0815d-106">如果字段定义为 PropDefV2 格式，该流结构存在于[FieldDefinition](fielddefinition-stream-structure.md) stream 中。</span><span class="sxs-lookup"><span data-stu-id="0815d-106">This stream structure exists in a [FieldDefinition](fielddefinition-stream-structure.md) stream if the field definition is in PropDefV2 format.</span></span> 
  
<span data-ttu-id="0815d-107">SkipBlock 流结构的目的取决于其在一系列类似的 FieldDefinition 流 SkipBlocks data 元素中的结构中的相对位置。</span><span class="sxs-lookup"><span data-stu-id="0815d-107">The purpose of a SkipBlock stream structure depends on its relative location in a series of like structures in the SkipBlocks data element of a FieldDefinition stream.</span></span> <span data-ttu-id="0815d-108">SkipBlocks 系列应包含至少一个 SkipBlock 结构终止系列且具有等于 0 的大小数据元素。</span><span class="sxs-lookup"><span data-stu-id="0815d-108">The SkipBlocks series should contain at least one SkipBlock structure that terminates the series and has the Size data element equal to 0.</span></span> <span data-ttu-id="0815d-109">如果第一个结构中不是终止结构 （即，大小数据元素是大于 0），Outlook 假定的第一个结构 Unicode (utf-16) 中指定的字段名称。</span><span class="sxs-lookup"><span data-stu-id="0815d-109">If the first structure is not the terminating structure (that is, the Size data element is greater than 0), Outlook assumes the first structure specifies the field name in Unicode (UTF-16).</span></span>
  
<span data-ttu-id="0815d-110">此流中的数据元素存储在-little-endian 字节的顺序，紧跟彼此下面指定的顺序。</span><span class="sxs-lookup"><span data-stu-id="0815d-110">Data elements in this stream are stored in little-endian byte order, immediately following each other in the order specified below.</span></span>
  
- <span data-ttu-id="0815d-111">规模： DWORD （4 个字节） 的大小，以字节为单位的内容数据元素的数量。</span><span class="sxs-lookup"><span data-stu-id="0815d-111">Size: DWORD (4 bytes), the size, in number of bytes, of the Content data element.</span></span>
    
- <span data-ttu-id="0815d-112">内容： BYTE 的数组。</span><span class="sxs-lookup"><span data-stu-id="0815d-112">Content: An array of BYTE.</span></span> <span data-ttu-id="0815d-113">此数组的计数等于大小数据元素。</span><span class="sxs-lookup"><span data-stu-id="0815d-113">The count of this array is equal to the Size data element.</span></span> <span data-ttu-id="0815d-114">内容数据元素的含义取决于 SkipBlock 结构系列中的位置和 Outlook 版本。</span><span class="sxs-lookup"><span data-stu-id="0815d-114">The meaning of the Content data element depends on the location of the SkipBlock structure in the series and the version of Outlook.</span></span> <span data-ttu-id="0815d-115">如果第一个 SkipBlock 结构不终止的结构，Outlook 就会将视为 Unicode 中指定的字段名称的[FirstSkipBlockContent](firstskipblockcontent-stream-structure.md)流结构的第一个 SkipBlock 结构。</span><span class="sxs-lookup"><span data-stu-id="0815d-115">If the first SkipBlock structure is not the terminating structure, Outlook considers the first SkipBlock structure as the [FirstSkipBlockContent](firstskipblockcontent-stream-structure.md) stream structure that specifies the field name in Unicode.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="0815d-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0815d-116">See also</span></span>



[<span data-ttu-id="0815d-117">Outlook 项和字段</span><span class="sxs-lookup"><span data-stu-id="0815d-117">Outlook Items and Fields</span></span>](outlook-items-and-fields.md)
  
[<span data-ttu-id="0815d-118">流结构</span><span class="sxs-lookup"><span data-stu-id="0815d-118">Stream Structures</span></span>](stream-structures.md)
  
[<span data-ttu-id="0815d-119">FieldDefinition 流结构</span><span class="sxs-lookup"><span data-stu-id="0815d-119">FieldDefinition Stream Structure</span></span>](fielddefinition-stream-structure.md)
  
[<span data-ttu-id="0815d-120">FirstSkipBlockContent 流结构</span><span class="sxs-lookup"><span data-stu-id="0815d-120">FirstSkipBlockContent Stream Structure</span></span>](firstskipblockcontent-stream-structure.md)

