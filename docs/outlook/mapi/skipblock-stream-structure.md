---
title: SkipBlock 流结构
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 2499587b-2a0e-4987-9bf7-591bef41b894
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 5a3367a15374234658fd9d10f3c2a5f3a191c80e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32282668"
---
# <a name="skipblock-stream-structure"></a><span data-ttu-id="eeb78-103">SkipBlock 流结构</span><span class="sxs-lookup"><span data-stu-id="eeb78-103">SkipBlock Stream Structure</span></span>

  
  
<span data-ttu-id="eeb78-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="eeb78-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="eeb78-105">SkipBlock 流结构是一种以整数开头的数据块, 用于指定块的剩余部分的长度。</span><span class="sxs-lookup"><span data-stu-id="eeb78-105">A SkipBlock stream structure is a block of data that starts with an integer that specifies the length of the remaining part of the block.</span></span> <span data-ttu-id="eeb78-106">如果字段定义为 PropDefV2 格式, 则[FieldDefinition](fielddefinition-stream-structure.md)流中存在此流结构。</span><span class="sxs-lookup"><span data-stu-id="eeb78-106">This stream structure exists in a [FieldDefinition](fielddefinition-stream-structure.md) stream if the field definition is in PropDefV2 format.</span></span> 
  
<span data-ttu-id="eeb78-107">SkipBlock 流结构的用途取决于其在 FieldDefinition 流的 SkipBlocks 数据元素中的一系列类似结构中的相对位置。</span><span class="sxs-lookup"><span data-stu-id="eeb78-107">The purpose of a SkipBlock stream structure depends on its relative location in a series of like structures in the SkipBlocks data element of a FieldDefinition stream.</span></span> <span data-ttu-id="eeb78-108">SkipBlocks 系列应包含至少一个 SkipBlock 结构, 该结构将终止系列并使 Size 数据元素等于0。</span><span class="sxs-lookup"><span data-stu-id="eeb78-108">The SkipBlocks series should contain at least one SkipBlock structure that terminates the series and has the Size data element equal to 0.</span></span> <span data-ttu-id="eeb78-109">如果第一个结构不是终止结构 (即, Size 数据元素大于 0), Outlook 将假定第一个结构以 Unicode (UTF-16) 指定字段名称。</span><span class="sxs-lookup"><span data-stu-id="eeb78-109">If the first structure is not the terminating structure (that is, the Size data element is greater than 0), Outlook assumes the first structure specifies the field name in Unicode (UTF-16).</span></span>
  
<span data-ttu-id="eeb78-110">此流中的数据元素存储在小端字节序的字节顺序中, 紧跟在下面指定的顺序依次后续。</span><span class="sxs-lookup"><span data-stu-id="eeb78-110">Data elements in this stream are stored in little-endian byte order, immediately following each other in the order specified below.</span></span>
  
- <span data-ttu-id="eeb78-111">大小: DWORD (4 个字节), 内容数据元素的大小 (以字节数表示)。</span><span class="sxs-lookup"><span data-stu-id="eeb78-111">Size: DWORD (4 bytes), the size, in number of bytes, of the Content data element.</span></span>
    
- <span data-ttu-id="eeb78-112">内容: 字节数组。</span><span class="sxs-lookup"><span data-stu-id="eeb78-112">Content: An array of BYTE.</span></span> <span data-ttu-id="eeb78-113">此数组的计数等于大小数据元素。</span><span class="sxs-lookup"><span data-stu-id="eeb78-113">The count of this array is equal to the Size data element.</span></span> <span data-ttu-id="eeb78-114">内容数据元素的意义取决于 SkipBlock 结构在系列中的位置和 Outlook 的版本。</span><span class="sxs-lookup"><span data-stu-id="eeb78-114">The meaning of the Content data element depends on the location of the SkipBlock structure in the series and the version of Outlook.</span></span> <span data-ttu-id="eeb78-115">如果第一个 SkipBlock 结构不是终止结构, Outlook 会将第一个 SkipBlock 结构视为用 Unicode 指定字段名称的[FirstSkipBlockContent](firstskipblockcontent-stream-structure.md)流结构。</span><span class="sxs-lookup"><span data-stu-id="eeb78-115">If the first SkipBlock structure is not the terminating structure, Outlook considers the first SkipBlock structure as the [FirstSkipBlockContent](firstskipblockcontent-stream-structure.md) stream structure that specifies the field name in Unicode.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="eeb78-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="eeb78-116">See also</span></span>



[<span data-ttu-id="eeb78-117">Outlook 项目和字段</span><span class="sxs-lookup"><span data-stu-id="eeb78-117">Outlook Items and Fields</span></span>](outlook-items-and-fields.md)
  
[<span data-ttu-id="eeb78-118">流结构</span><span class="sxs-lookup"><span data-stu-id="eeb78-118">Stream Structures</span></span>](stream-structures.md)
  
[<span data-ttu-id="eeb78-119">FieldDefinition 流结构</span><span class="sxs-lookup"><span data-stu-id="eeb78-119">FieldDefinition Stream Structure</span></span>](fielddefinition-stream-structure.md)
  
[<span data-ttu-id="eeb78-120">FirstSkipBlockContent 流结构</span><span class="sxs-lookup"><span data-stu-id="eeb78-120">FirstSkipBlockContent Stream Structure</span></span>](firstskipblockcontent-stream-structure.md)

