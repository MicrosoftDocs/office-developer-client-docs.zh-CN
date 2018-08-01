---
title: 处理大型列
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 452acccf-22fd-4450-b50f-eaa2b2c94515
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: a191a8551d425d7e8b3b9a281936a4a0e2dfd587
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779089"
---
# <a name="working-with-large-columns"></a><span data-ttu-id="d940c-103">处理大型列</span><span class="sxs-lookup"><span data-stu-id="d940c-103">Working with Large Columns</span></span>

  
  
<span data-ttu-id="d940c-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="d940c-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="d940c-105">列中的包含字符串或二进制属性数据可能很大，可能数千个字节长。</span><span class="sxs-lookup"><span data-stu-id="d940c-105">Columns with string or binary property data can be large, possibly many thousands of bytes long.</span></span> <span data-ttu-id="d940c-106">视图中包括一个或多个列与数百个字节通常是不切实际的因为 MAPI 使表实施者截断的值，最常到 255 个字节和 510 字节越来越少。</span><span class="sxs-lookup"><span data-stu-id="d940c-106">Because including one or more columns with hundreds of bytes in a view is often impractical, MAPI enables table implementers to truncate the value, most often to 255 bytes and less often to 510 bytes.</span></span> <span data-ttu-id="d940c-107">只要有可能，表实施应包括的表格列中的属性的完整值。</span><span class="sxs-lookup"><span data-stu-id="d940c-107">Whenever possible, table implementers should include the full value of a property in a table column.</span></span> <span data-ttu-id="d940c-108">建议使用的替代是包含前 255 个字节。</span><span class="sxs-lookup"><span data-stu-id="d940c-108">The recommended alternative is to include only the first 255 bytes.</span></span>
  
<span data-ttu-id="d940c-109">客户端无法事先知道，他们使用的表是否截断大型列。</span><span class="sxs-lookup"><span data-stu-id="d940c-109">Clients cannot know in advance whether a table they are using truncates large columns.</span></span> <span data-ttu-id="d940c-110">他们应假定列表示截断的属性，如果列的长度为 255 个或 510 字节。</span><span class="sxs-lookup"><span data-stu-id="d940c-110">They should assume that a column represents a truncated property if the length of the column is either 255 or 510 bytes.</span></span> <span data-ttu-id="d940c-111">如有必要，客户端可以直接截断列的完整值从对象中检索通过调用该对象的[IMAPIProp::GetProps](imapiprop-getprops.md)方法。</span><span class="sxs-lookup"><span data-stu-id="d940c-111">If necessary, clients can directly retrieve the full value of a truncated column from the object by calling the object's [IMAPIProp::GetProps](imapiprop-getprops.md) method.</span></span> 
  
<span data-ttu-id="d940c-112">构建具有大型属性限制的客户端应注意，最多为表实施来如何这些限制对操作。</span><span class="sxs-lookup"><span data-stu-id="d940c-112">Clients building restrictions with large properties should be aware that it is up to the table implementer as to how these restrictions operate.</span></span> <span data-ttu-id="d940c-113">某些表实施允许使用截断列时其他人基于整个值基于截断大小生成的限制。</span><span class="sxs-lookup"><span data-stu-id="d940c-113">Some table implementers allow restrictions that are built with a truncated column to be based on the truncated size while others base it on the entire value.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="d940c-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d940c-114">See also</span></span>



[<span data-ttu-id="d940c-115">MAPI 表</span><span class="sxs-lookup"><span data-stu-id="d940c-115">MAPI Tables</span></span>](mapi-tables.md)

