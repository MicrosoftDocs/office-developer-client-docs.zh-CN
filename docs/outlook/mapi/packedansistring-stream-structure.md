---
title: PackedAnsiString 流结构
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: ada86f04-e81b-4f97-b9c1-1c8ec5e1a5dd
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 5494558db65e19891848264c170ba85a55c5df71
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776576"
---
# <a name="packedansistring-stream-structure"></a><span data-ttu-id="8862c-103">PackedAnsiString 流结构</span><span class="sxs-lookup"><span data-stu-id="8862c-103">PackedAnsiString Stream Structure</span></span>

  
  
<span data-ttu-id="8862c-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="8862c-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="8862c-105">PackedAnsiString 流结构包含 ANSI 字符串表示形式，根据在其上运行 Microsoft Outlook 的计算机的 ANSI 代码页。</span><span class="sxs-lookup"><span data-stu-id="8862c-105">The PackedAnsiString stream structure contains an ANSI representation of a string, based on the ANSI code page of the computer on which Microsoft Outlook is running.</span></span> <span data-ttu-id="8862c-106">未通过空字符终止此字符串。</span><span class="sxs-lookup"><span data-stu-id="8862c-106">This string is not terminated by a null character.</span></span> <span data-ttu-id="8862c-107">此流中的数据元素存储在-little-endian 字节的顺序，紧跟彼此下面列出的顺序。</span><span class="sxs-lookup"><span data-stu-id="8862c-107">Data elements in this stream are stored in little-endian byte order, immediately following each other in the order listed below.</span></span> <span data-ttu-id="8862c-108">存在的实际数据元素取决于 ANSI 表示中字符串的长度。</span><span class="sxs-lookup"><span data-stu-id="8862c-108">The actual data elements that exist depend on the length of the string in ANSI representation.</span></span>
  
- <span data-ttu-id="8862c-109">一个字符串，其 ANSI 表示包含不超过 255 个字节，数据要素如下所示：</span><span class="sxs-lookup"><span data-stu-id="8862c-109">For a string whose ANSI representation contains less than 255 bytes, the data elements are as follows:</span></span>
    
  - <span data-ttu-id="8862c-110">时长： 字节 （1 个字节），ANSI 字符串表示形式的长度，以字节为单位数。</span><span class="sxs-lookup"><span data-stu-id="8862c-110">Length: BYTE (1 byte), the length, in number of bytes, of the ANSI representation of the string.</span></span>
    
  - <span data-ttu-id="8862c-111">字符数： CHAR 的数组。</span><span class="sxs-lookup"><span data-stu-id="8862c-111">Characters: An array of CHAR.</span></span> <span data-ttu-id="8862c-112">此数组的计数等于长度数据元素。</span><span class="sxs-lookup"><span data-stu-id="8862c-112">The count of this array is equal to the Length data element.</span></span> <span data-ttu-id="8862c-113">数组中的数据是 ANSI 字符串表示形式。</span><span class="sxs-lookup"><span data-stu-id="8862c-113">The data in the array is the ANSI representation of the string.</span></span>
    
- <span data-ttu-id="8862c-114">一个字符串，其 ANSI 表示包含 255 到 65535 字节，数据要素如下所示：</span><span class="sxs-lookup"><span data-stu-id="8862c-114">For a string whose ANSI representation contains 255 to 65535 bytes, the data elements are as follows:</span></span>
    
  - <span data-ttu-id="8862c-115">前缀： 字节 （1 个字节），255 之间的值 (0xff)。</span><span class="sxs-lookup"><span data-stu-id="8862c-115">Prefix: BYTE (1 byte), the value of 255 (0xff).</span></span>
    
  - <span data-ttu-id="8862c-116">时长： 单词 （2 个字节），ANSI 字符串表示形式的长度，以字节为单位数。</span><span class="sxs-lookup"><span data-stu-id="8862c-116">Length: WORD (2 bytes), the length, in number of bytes, of the ANSI representation of the string.</span></span>
    
  - <span data-ttu-id="8862c-117">字符数： CHAR 的数组。</span><span class="sxs-lookup"><span data-stu-id="8862c-117">Characters: An array of CHAR.</span></span> <span data-ttu-id="8862c-118">此数组的计数等于长度数据元素。</span><span class="sxs-lookup"><span data-stu-id="8862c-118">The count of this array is equal to the Length data element.</span></span> <span data-ttu-id="8862c-119">数组中的数据是 ANSI 字符串表示形式。</span><span class="sxs-lookup"><span data-stu-id="8862c-119">The data in the array is the ANSI representation of the string.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="8862c-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8862c-120">See also</span></span>



[<span data-ttu-id="8862c-121">Outlook 项和计算字段</span><span class="sxs-lookup"><span data-stu-id="8862c-121">Outlook Items and Fields</span></span>](outlook-items-and-fields.md)
  
[<span data-ttu-id="8862c-122">流结构</span><span class="sxs-lookup"><span data-stu-id="8862c-122">Stream Structures</span></span>](stream-structures.md)
  
[<span data-ttu-id="8862c-123">FieldDefinition 流结构</span><span class="sxs-lookup"><span data-stu-id="8862c-123">FieldDefinition Stream Structure</span></span>](fielddefinition-stream-structure.md)
