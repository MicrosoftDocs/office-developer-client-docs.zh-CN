---
title: PackedUnicodeString 流结构
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: e4cb1613-7e81-432a-ae3a-7fedb05dac65
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: fc20c259f30ded2f96f3bf314e74207bebcac980
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32348473"
---
# <a name="packedunicodestring-stream-structure"></a><span data-ttu-id="34273-103">PackedUnicodeString 流结构</span><span class="sxs-lookup"><span data-stu-id="34273-103">PackedUnicodeString Stream Structure</span></span>

  
  
<span data-ttu-id="34273-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="34273-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="34273-105">PackedUnicodeString 流结构包含字符串的 Unicode (UTF-16) 表示形式。</span><span class="sxs-lookup"><span data-stu-id="34273-105">The PackedUnicodeString stream structure contains a Unicode (UTF-16) representation of a string.</span></span> <span data-ttu-id="34273-106">此字符串不是由 null 字符终止的。</span><span class="sxs-lookup"><span data-stu-id="34273-106">This string is not terminated by a null character.</span></span> <span data-ttu-id="34273-107">此流中的数据元素存储在小端字节序的字节顺序中, 紧跟在下面列出的顺序后续。</span><span class="sxs-lookup"><span data-stu-id="34273-107">Data elements in this stream are stored in little-endian byte order, immediately following each other in the order listed below.</span></span> <span data-ttu-id="34273-108">现有的实际数据元素取决于 UTF-16 表示形式的字符串的长度。</span><span class="sxs-lookup"><span data-stu-id="34273-108">The actual data elements that exist depend on the length of the string in UTF-16 representation.</span></span>
  
- <span data-ttu-id="34273-109">对于其 UTF-16 表示形式包含小于 255 WCHARs 的字符串, 数据元素如下所示:</span><span class="sxs-lookup"><span data-stu-id="34273-109">For a string whose UTF-16 representation contains less than 255 WCHARs, the data elements are as follows:</span></span>
    
  - <span data-ttu-id="34273-110">长度: 字节 (1 个字节), 字符串的 utf-16 表示形式的长度 (以 WCHARs 为单位)。</span><span class="sxs-lookup"><span data-stu-id="34273-110">Length: BYTE (1 byte), the length, in number of WCHARs, of the UTF-16 representation of the string.</span></span>
    
  - <span data-ttu-id="34273-111">字符: WCHAR 数组。</span><span class="sxs-lookup"><span data-stu-id="34273-111">Characters: An array of WCHAR.</span></span> <span data-ttu-id="34273-112">此数组的计数等于 Length 数据元素。</span><span class="sxs-lookup"><span data-stu-id="34273-112">The count of this array is equal to the Length data element.</span></span> <span data-ttu-id="34273-113">数组中的数据是字符串的 UTF-16 表示形式。</span><span class="sxs-lookup"><span data-stu-id="34273-113">The data in the array is the UTF-16 representation of the string.</span></span>
    
- <span data-ttu-id="34273-114">对于其 UTF-16 表示形式包含255到 65535 WCHARs 的字符串, 数据元素如下所示:</span><span class="sxs-lookup"><span data-stu-id="34273-114">For a string whose UTF-16 representation contains 255 to 65535 WCHARs, the data elements are as follows:</span></span>
    
  - <span data-ttu-id="34273-115">Prefix: BYTE (1 个字节), 值为 255 (0xff)。</span><span class="sxs-lookup"><span data-stu-id="34273-115">Prefix: BYTE (1 byte), the value of 255 (0xff).</span></span>
    
  - <span data-ttu-id="34273-116">length: WORD (2 个字节), 字符串的 utf-16 表示形式的长度 (以 WCHARs 为单位)。</span><span class="sxs-lookup"><span data-stu-id="34273-116">Length: WORD (2 bytes), the length, in number of WCHARs, of the UTF-16 representation of the string.</span></span>
    
  - <span data-ttu-id="34273-117">字符: WCHAR 数组。</span><span class="sxs-lookup"><span data-stu-id="34273-117">Characters: An array of WCHAR.</span></span> <span data-ttu-id="34273-118">此数组的计数等于 Length 数据元素。</span><span class="sxs-lookup"><span data-stu-id="34273-118">The count of this array is equal to the Length data element.</span></span> <span data-ttu-id="34273-119">数组中的数据是字符串的 UTF-16 表示形式。</span><span class="sxs-lookup"><span data-stu-id="34273-119">The data in the array is the UTF-16 representation of the string.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="34273-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="34273-120">See also</span></span>



[<span data-ttu-id="34273-121">Outlook 项目和字段</span><span class="sxs-lookup"><span data-stu-id="34273-121">Outlook Items and Fields</span></span>](outlook-items-and-fields.md)
  
[<span data-ttu-id="34273-122">流结构</span><span class="sxs-lookup"><span data-stu-id="34273-122">Stream Structures</span></span>](stream-structures.md)
  
[<span data-ttu-id="34273-123">FieldDefinition 流结构</span><span class="sxs-lookup"><span data-stu-id="34273-123">FieldDefinition Stream Structure</span></span>](fielddefinition-stream-structure.md)

