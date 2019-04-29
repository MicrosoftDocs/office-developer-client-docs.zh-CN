---
title: PackedAnsiString 流结构
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: ada86f04-e81b-4f97-b9c1-1c8ec5e1a5dd
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 3e48e57deba5c274982eeb515d27f203ec5ac7fc
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33404503"
---
# <a name="packedansistring-stream-structure"></a><span data-ttu-id="f79a4-103">PackedAnsiString 流结构</span><span class="sxs-lookup"><span data-stu-id="f79a4-103">PackedAnsiString Stream Structure</span></span>

  
  
<span data-ttu-id="f79a4-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f79a4-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f79a4-105">PackedAnsiString 流结构包含字符串的 ansi 表示形式, 它基于运行 Microsoft Outlook 的计算机的 ansi 代码页。</span><span class="sxs-lookup"><span data-stu-id="f79a4-105">The PackedAnsiString stream structure contains an ANSI representation of a string, based on the ANSI code page of the computer on which Microsoft Outlook is running.</span></span> <span data-ttu-id="f79a4-106">此字符串不是由 null 字符终止的。</span><span class="sxs-lookup"><span data-stu-id="f79a4-106">This string is not terminated by a null character.</span></span> <span data-ttu-id="f79a4-107">此流中的数据元素存储在小端字节序的字节顺序中, 紧跟在下面列出的顺序后续。</span><span class="sxs-lookup"><span data-stu-id="f79a4-107">Data elements in this stream are stored in little-endian byte order, immediately following each other in the order listed below.</span></span> <span data-ttu-id="f79a4-108">现有的实际数据元素取决于 ANSI 表示形式的字符串的长度。</span><span class="sxs-lookup"><span data-stu-id="f79a4-108">The actual data elements that exist depend on the length of the string in ANSI representation.</span></span>
  
- <span data-ttu-id="f79a4-109">对于 ANSI 表示形式包含小于255个字节的字符串, 数据元素如下所示:</span><span class="sxs-lookup"><span data-stu-id="f79a4-109">For a string whose ANSI representation contains less than 255 bytes, the data elements are as follows:</span></span>
    
  - <span data-ttu-id="f79a4-110">length: BYTE (1 个字节), 字符串的 ANSI 表示形式的长度 (以字节为单位)。</span><span class="sxs-lookup"><span data-stu-id="f79a4-110">Length: BYTE (1 byte), the length, in number of bytes, of the ANSI representation of the string.</span></span>
    
  - <span data-ttu-id="f79a4-111">字符: 字符数组。</span><span class="sxs-lookup"><span data-stu-id="f79a4-111">Characters: An array of CHAR.</span></span> <span data-ttu-id="f79a4-112">此数组的计数等于 Length 数据元素。</span><span class="sxs-lookup"><span data-stu-id="f79a4-112">The count of this array is equal to the Length data element.</span></span> <span data-ttu-id="f79a4-113">数组中的数据是字符串的 ANSI 表示形式。</span><span class="sxs-lookup"><span data-stu-id="f79a4-113">The data in the array is the ANSI representation of the string.</span></span>
    
- <span data-ttu-id="f79a4-114">对于 ANSI 表示形式包含255到65535字节的字符串, 数据元素如下所示:</span><span class="sxs-lookup"><span data-stu-id="f79a4-114">For a string whose ANSI representation contains 255 to 65535 bytes, the data elements are as follows:</span></span>
    
  - <span data-ttu-id="f79a4-115">Prefix: BYTE (1 个字节), 值为 255 (0xff)。</span><span class="sxs-lookup"><span data-stu-id="f79a4-115">Prefix: BYTE (1 byte), the value of 255 (0xff).</span></span>
    
  - <span data-ttu-id="f79a4-116">length: WORD (2 个字节), 字符串的 ANSI 表示形式的长度 (以字节为单位)。</span><span class="sxs-lookup"><span data-stu-id="f79a4-116">Length: WORD (2 bytes), the length, in number of bytes, of the ANSI representation of the string.</span></span>
    
  - <span data-ttu-id="f79a4-117">字符: 字符数组。</span><span class="sxs-lookup"><span data-stu-id="f79a4-117">Characters: An array of CHAR.</span></span> <span data-ttu-id="f79a4-118">此数组的计数等于 Length 数据元素。</span><span class="sxs-lookup"><span data-stu-id="f79a4-118">The count of this array is equal to the Length data element.</span></span> <span data-ttu-id="f79a4-119">数组中的数据是字符串的 ANSI 表示形式。</span><span class="sxs-lookup"><span data-stu-id="f79a4-119">The data in the array is the ANSI representation of the string.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="f79a4-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f79a4-120">See also</span></span>



[<span data-ttu-id="f79a4-121">Outlook 项目和字段</span><span class="sxs-lookup"><span data-stu-id="f79a4-121">Outlook Items and Fields</span></span>](outlook-items-and-fields.md)
  
[<span data-ttu-id="f79a4-122">流结构</span><span class="sxs-lookup"><span data-stu-id="f79a4-122">Stream Structures</span></span>](stream-structures.md)
  
[<span data-ttu-id="f79a4-123">FieldDefinition 流结构</span><span class="sxs-lookup"><span data-stu-id="f79a4-123">FieldDefinition Stream Structure</span></span>](fielddefinition-stream-structure.md)

