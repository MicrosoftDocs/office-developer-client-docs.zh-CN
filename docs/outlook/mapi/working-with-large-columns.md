---
title: 处理大型列
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 452acccf-22fd-4450-b50f-eaa2b2c94515
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 9ca3c5e7a0d1b4a6ac09dcfcc7db10ec76ecb224
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33420421"
---
# <a name="working-with-large-columns"></a><span data-ttu-id="0c15a-103">处理大型列</span><span class="sxs-lookup"><span data-stu-id="0c15a-103">Working with Large Columns</span></span>

  
  
<span data-ttu-id="0c15a-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="0c15a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="0c15a-105">带有字符串或二进制属性数据的列可能会很大, 可能很多包含数千个字节。</span><span class="sxs-lookup"><span data-stu-id="0c15a-105">Columns with string or binary property data can be large, possibly many thousands of bytes long.</span></span> <span data-ttu-id="0c15a-106">由于在视图中包含包含数百个字节的一个或多个列通常是不切实际的, 因此 MAPI 使表实施者能够将此值截断, 最常见的是255字节, 而频率不到510字节。</span><span class="sxs-lookup"><span data-stu-id="0c15a-106">Because including one or more columns with hundreds of bytes in a view is often impractical, MAPI enables table implementers to truncate the value, most often to 255 bytes and less often to 510 bytes.</span></span> <span data-ttu-id="0c15a-107">只要有可能, 表实施者就应将属性的完整值包括在表的列中。</span><span class="sxs-lookup"><span data-stu-id="0c15a-107">Whenever possible, table implementers should include the full value of a property in a table column.</span></span> <span data-ttu-id="0c15a-108">建议的替代方法是仅包含前255个字节。</span><span class="sxs-lookup"><span data-stu-id="0c15a-108">The recommended alternative is to include only the first 255 bytes.</span></span>
  
<span data-ttu-id="0c15a-109">客户端无法提前知道其使用的表是否截断了大型列。</span><span class="sxs-lookup"><span data-stu-id="0c15a-109">Clients cannot know in advance whether a table they are using truncates large columns.</span></span> <span data-ttu-id="0c15a-110">如果列的长度为255或510字节, 则用户应假定列表示截断的属性。</span><span class="sxs-lookup"><span data-stu-id="0c15a-110">They should assume that a column represents a truncated property if the length of the column is either 255 or 510 bytes.</span></span> <span data-ttu-id="0c15a-111">如果需要, 客户端可以通过调用对象的[IMAPIProp:: GetProps](imapiprop-getprops.md)方法直接从对象中检索截断的列的完整值。</span><span class="sxs-lookup"><span data-stu-id="0c15a-111">If necessary, clients can directly retrieve the full value of a truncated column from the object by calling the object's [IMAPIProp::GetProps](imapiprop-getprops.md) method.</span></span> 
  
<span data-ttu-id="0c15a-112">使用大型属性构建限制的客户端应注意, 对于表实施者来说, 这些限制是如何运行的。</span><span class="sxs-lookup"><span data-stu-id="0c15a-112">Clients building restrictions with large properties should be aware that it is up to the table implementer as to how these restrictions operate.</span></span> <span data-ttu-id="0c15a-113">某些表实施者允许使用被截断的列生成的限制基于截断的大小, 而另一些则将其作为整个值。</span><span class="sxs-lookup"><span data-stu-id="0c15a-113">Some table implementers allow restrictions that are built with a truncated column to be based on the truncated size while others base it on the entire value.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="0c15a-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0c15a-114">See also</span></span>



[<span data-ttu-id="0c15a-115">MAPI 表</span><span class="sxs-lookup"><span data-stu-id="0c15a-115">MAPI Tables</span></span>](mapi-tables.md)

