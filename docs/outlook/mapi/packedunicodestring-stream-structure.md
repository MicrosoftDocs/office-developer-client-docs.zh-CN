---
title: PackedUnicodeString 流结构
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: e4cb1613-7e81-432a-ae3a-7fedb05dac65
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: fc20c259f30ded2f96f3bf314e74207bebcac980
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33422612"
---
# <a name="packedunicodestring-stream-structure"></a><span data-ttu-id="248d6-103">PackedUnicodeString 流结构</span><span class="sxs-lookup"><span data-stu-id="248d6-103">PackedUnicodeString Stream Structure</span></span>

  
  
<span data-ttu-id="248d6-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="248d6-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="248d6-105">PackedUnicodeString 流结构包含 Unicode (UTF-16) 字符串的表示形式。</span><span class="sxs-lookup"><span data-stu-id="248d6-105">The PackedUnicodeString stream structure contains a Unicode (UTF-16) representation of a string.</span></span> <span data-ttu-id="248d6-106">此字符串不以空字符结尾。</span><span class="sxs-lookup"><span data-stu-id="248d6-106">This string is not terminated by a null character.</span></span> <span data-ttu-id="248d6-107">此流中的数据元素按小尾字节顺序存储，并按下面列出的顺序彼此紧接。</span><span class="sxs-lookup"><span data-stu-id="248d6-107">Data elements in this stream are stored in little-endian byte order, immediately following each other in the order listed below.</span></span> <span data-ttu-id="248d6-108">实际存在的数据元素取决于 UTF-16 表示形式中的字符串长度。</span><span class="sxs-lookup"><span data-stu-id="248d6-108">The actual data elements that exist depend on the length of the string in UTF-16 representation.</span></span>
  
- <span data-ttu-id="248d6-109">对于 UTF-16 表示形式包含小于 255 个 WCHAR 的字符串，数据元素如下所示：</span><span class="sxs-lookup"><span data-stu-id="248d6-109">For a string whose UTF-16 representation contains less than 255 WCHARs, the data elements are as follows:</span></span>
    
  - <span data-ttu-id="248d6-110">长度：BYTE (1 字节) ，字符串的 UTF-16 表示形式的长度（以 WCHAR 数表示）。</span><span class="sxs-lookup"><span data-stu-id="248d6-110">Length: BYTE (1 byte), the length, in number of WCHARs, of the UTF-16 representation of the string.</span></span>
    
  - <span data-ttu-id="248d6-111">字符：WCHAR 的数组。</span><span class="sxs-lookup"><span data-stu-id="248d6-111">Characters: An array of WCHAR.</span></span> <span data-ttu-id="248d6-112">此数组的计数等于 Length 数据元素。</span><span class="sxs-lookup"><span data-stu-id="248d6-112">The count of this array is equal to the Length data element.</span></span> <span data-ttu-id="248d6-113">数组中的数据是字符串的 UTF-16 表示形式。</span><span class="sxs-lookup"><span data-stu-id="248d6-113">The data in the array is the UTF-16 representation of the string.</span></span>
    
- <span data-ttu-id="248d6-114">对于 UTF-16 表示形式包含 255 到 65535 WCHAR 的字符串，数据元素如下所示：</span><span class="sxs-lookup"><span data-stu-id="248d6-114">For a string whose UTF-16 representation contains 255 to 65535 WCHARs, the data elements are as follows:</span></span>
    
  - <span data-ttu-id="248d6-115">前缀：BYTE (1 字节) ，值 255 (0xff) 。</span><span class="sxs-lookup"><span data-stu-id="248d6-115">Prefix: BYTE (1 byte), the value of 255 (0xff).</span></span>
    
  - <span data-ttu-id="248d6-116">长度：WORD (2 字节) ，即字符串的 UTF-16 表示形式的长度（以 WCHAR 数表示）。</span><span class="sxs-lookup"><span data-stu-id="248d6-116">Length: WORD (2 bytes), the length, in number of WCHARs, of the UTF-16 representation of the string.</span></span>
    
  - <span data-ttu-id="248d6-117">字符：WCHAR 的数组。</span><span class="sxs-lookup"><span data-stu-id="248d6-117">Characters: An array of WCHAR.</span></span> <span data-ttu-id="248d6-118">此数组的计数等于 Length 数据元素。</span><span class="sxs-lookup"><span data-stu-id="248d6-118">The count of this array is equal to the Length data element.</span></span> <span data-ttu-id="248d6-119">数组中的数据是字符串的 UTF-16 表示形式。</span><span class="sxs-lookup"><span data-stu-id="248d6-119">The data in the array is the UTF-16 representation of the string.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="248d6-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="248d6-120">See also</span></span>



[<span data-ttu-id="248d6-121">Outlook项目和字段</span><span class="sxs-lookup"><span data-stu-id="248d6-121">Outlook Items and Fields</span></span>](outlook-items-and-fields.md)
  
[<span data-ttu-id="248d6-122">流结构</span><span class="sxs-lookup"><span data-stu-id="248d6-122">Stream Structures</span></span>](stream-structures.md)
  
[<span data-ttu-id="248d6-123">FieldDefinition 流结构</span><span class="sxs-lookup"><span data-stu-id="248d6-123">FieldDefinition Stream Structure</span></span>](fielddefinition-stream-structure.md)

