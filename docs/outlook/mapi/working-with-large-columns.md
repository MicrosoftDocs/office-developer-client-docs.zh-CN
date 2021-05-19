---
title: 使用大列
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
# <a name="working-with-large-columns"></a><span data-ttu-id="15632-103">使用大列</span><span class="sxs-lookup"><span data-stu-id="15632-103">Working with Large Columns</span></span>

  
  
<span data-ttu-id="15632-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="15632-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="15632-105">具有字符串或二进制属性数据的列可能很大，可能数千字节长。</span><span class="sxs-lookup"><span data-stu-id="15632-105">Columns with string or binary property data can be large, possibly many thousands of bytes long.</span></span> <span data-ttu-id="15632-106">由于在视图中包含一个或多个包含数百个字节的列通常不切实际，因此 MAPI 允许表实现程序截断值，通常截断为 255 字节，而将更不常截断为 510 字节。</span><span class="sxs-lookup"><span data-stu-id="15632-106">Because including one or more columns with hundreds of bytes in a view is often impractical, MAPI enables table implementers to truncate the value, most often to 255 bytes and less often to 510 bytes.</span></span> <span data-ttu-id="15632-107">只要有可能，表实施者应在表列中包括属性的完整值。</span><span class="sxs-lookup"><span data-stu-id="15632-107">Whenever possible, table implementers should include the full value of a property in a table column.</span></span> <span data-ttu-id="15632-108">建议的替代项是仅包含前 255 个字节。</span><span class="sxs-lookup"><span data-stu-id="15632-108">The recommended alternative is to include only the first 255 bytes.</span></span>
  
<span data-ttu-id="15632-109">客户端无法提前知道他们使用的表是否截断了大列。</span><span class="sxs-lookup"><span data-stu-id="15632-109">Clients cannot know in advance whether a table they are using truncates large columns.</span></span> <span data-ttu-id="15632-110">如果列的长度为 255 或 510 字节，则它们应假定列代表截断的属性。</span><span class="sxs-lookup"><span data-stu-id="15632-110">They should assume that a column represents a truncated property if the length of the column is either 255 or 510 bytes.</span></span> <span data-ttu-id="15632-111">如有必要，客户端可以通过调用对象的 [IMAPIProp：：GetProps](imapiprop-getprops.md) 方法直接从对象检索截断列的完整值。</span><span class="sxs-lookup"><span data-stu-id="15632-111">If necessary, clients can directly retrieve the full value of a truncated column from the object by calling the object's [IMAPIProp::GetProps](imapiprop-getprops.md) method.</span></span> 
  
<span data-ttu-id="15632-112">使用大型属性构建限制的客户端应注意，这些限制的运行方式由表实施者决定。</span><span class="sxs-lookup"><span data-stu-id="15632-112">Clients building restrictions with large properties should be aware that it is up to the table implementer as to how these restrictions operate.</span></span> <span data-ttu-id="15632-113">某些表实现程序允许使用截断列构建的限制基于截断的大小，而其他表实现器则基于整个值。</span><span class="sxs-lookup"><span data-stu-id="15632-113">Some table implementers allow restrictions that are built with a truncated column to be based on the truncated size while others base it on the entire value.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="15632-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="15632-114">See also</span></span>



[<span data-ttu-id="15632-115">MAPI 表</span><span class="sxs-lookup"><span data-stu-id="15632-115">MAPI Tables</span></span>](mapi-tables.md)

