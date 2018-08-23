---
title: PackedUnicodeString 流结构
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: e4cb1613-7e81-432a-ae3a-7fedb05dac65
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 00791ab47cc3c6bd435d6f581e5ada53ae59d73b
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22569195"
---
# <a name="packedunicodestring-stream-structure"></a><span data-ttu-id="8f104-103">PackedUnicodeString 流结构</span><span class="sxs-lookup"><span data-stu-id="8f104-103">PackedUnicodeString Stream Structure</span></span>

  
  
<span data-ttu-id="8f104-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="8f104-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="8f104-105">PackedUnicodeString 流结构包含 Unicode (utf-16) 字符串表示形式。</span><span class="sxs-lookup"><span data-stu-id="8f104-105">The PackedUnicodeString stream structure contains a Unicode (UTF-16) representation of a string.</span></span> <span data-ttu-id="8f104-106">未通过空字符终止此字符串。</span><span class="sxs-lookup"><span data-stu-id="8f104-106">This string is not terminated by a null character.</span></span> <span data-ttu-id="8f104-107">此流中的数据元素存储在-little-endian 字节的顺序，紧跟彼此下面列出的顺序。</span><span class="sxs-lookup"><span data-stu-id="8f104-107">Data elements in this stream are stored in little-endian byte order, immediately following each other in the order listed below.</span></span> <span data-ttu-id="8f104-108">存在的实际数据元素取决于中 utf-16 表示形式的字符串的长度。</span><span class="sxs-lookup"><span data-stu-id="8f104-108">The actual data elements that exist depend on the length of the string in UTF-16 representation.</span></span>
  
- <span data-ttu-id="8f104-109">一个字符串，其 utf-16 表示包含少于 255 个 WCHARs，数据要素如下所示：</span><span class="sxs-lookup"><span data-stu-id="8f104-109">For a string whose UTF-16 representation contains less than 255 WCHARs, the data elements are as follows:</span></span>
    
  - <span data-ttu-id="8f104-110">时长： 字节 （1 个字节），utf-16 字符串表示形式的长度，以 WCHARs，数。</span><span class="sxs-lookup"><span data-stu-id="8f104-110">Length: BYTE (1 byte), the length, in number of WCHARs, of the UTF-16 representation of the string.</span></span>
    
  - <span data-ttu-id="8f104-111">字符数： WCHAR 数组。</span><span class="sxs-lookup"><span data-stu-id="8f104-111">Characters: An array of WCHAR.</span></span> <span data-ttu-id="8f104-112">此数组的计数等于长度数据元素。</span><span class="sxs-lookup"><span data-stu-id="8f104-112">The count of this array is equal to the Length data element.</span></span> <span data-ttu-id="8f104-113">数组中的数据是 utf-16 字符串表示形式。</span><span class="sxs-lookup"><span data-stu-id="8f104-113">The data in the array is the UTF-16 representation of the string.</span></span>
    
- <span data-ttu-id="8f104-114">一个字符串，其 utf-16 表示包含 255 到 65535 WCHARs，数据要素如下所示：</span><span class="sxs-lookup"><span data-stu-id="8f104-114">For a string whose UTF-16 representation contains 255 to 65535 WCHARs, the data elements are as follows:</span></span>
    
  - <span data-ttu-id="8f104-115">前缀： 字节 （1 个字节），255 之间的值 (0xff)。</span><span class="sxs-lookup"><span data-stu-id="8f104-115">Prefix: BYTE (1 byte), the value of 255 (0xff).</span></span>
    
  - <span data-ttu-id="8f104-116">时长： 单词 （2 个字节），utf-16 字符串表示形式的长度，以 WCHARs，数。</span><span class="sxs-lookup"><span data-stu-id="8f104-116">Length: WORD (2 bytes), the length, in number of WCHARs, of the UTF-16 representation of the string.</span></span>
    
  - <span data-ttu-id="8f104-117">字符数： WCHAR 数组。</span><span class="sxs-lookup"><span data-stu-id="8f104-117">Characters: An array of WCHAR.</span></span> <span data-ttu-id="8f104-118">此数组的计数等于长度数据元素。</span><span class="sxs-lookup"><span data-stu-id="8f104-118">The count of this array is equal to the Length data element.</span></span> <span data-ttu-id="8f104-119">数组中的数据是 utf-16 字符串表示形式。</span><span class="sxs-lookup"><span data-stu-id="8f104-119">The data in the array is the UTF-16 representation of the string.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="8f104-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8f104-120">See also</span></span>



[<span data-ttu-id="8f104-121">Outlook 项和字段</span><span class="sxs-lookup"><span data-stu-id="8f104-121">Outlook Items and Fields</span></span>](outlook-items-and-fields.md)
  
[<span data-ttu-id="8f104-122">流结构</span><span class="sxs-lookup"><span data-stu-id="8f104-122">Stream Structures</span></span>](stream-structures.md)
  
[<span data-ttu-id="8f104-123">FieldDefinition 流结构</span><span class="sxs-lookup"><span data-stu-id="8f104-123">FieldDefinition Stream Structure</span></span>](fielddefinition-stream-structure.md)

