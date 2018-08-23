---
title: 通过筛选器设置表位置
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 0d66124b-a018-4db4-b55b-a0e5ed467e14
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 6c4db9c67fc712143657fe66b86ea33ef2b9c272
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22565590"
---
# <a name="setting-a-table-position-with-a-filter"></a><span data-ttu-id="6446e-103">通过筛选器设置表位置</span><span class="sxs-lookup"><span data-stu-id="6446e-103">Setting a Table Position with a Filter</span></span>

  
  
<span data-ttu-id="6446e-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="6446e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="6446e-105">表用户可以将光标移到一组的筛选条件相匹配的行。</span><span class="sxs-lookup"><span data-stu-id="6446e-105">Table users can move the cursor to a row that matches a set of filter criteria.</span></span> <span data-ttu-id="6446e-106">筛选器可以根据各种如列属性的值、 位掩码或子对象的准则。</span><span class="sxs-lookup"><span data-stu-id="6446e-106">Filters can be based on a variety of guidelines such as column property values, bitmasks, or subobjects.</span></span> <span data-ttu-id="6446e-107">使用[SRestriction](srestriction.md)结构的 MAPI 中指定了筛选器。</span><span class="sxs-lookup"><span data-stu-id="6446e-107">Filters are specified in MAPI using an [SRestriction](srestriction.md) structure.</span></span> 
  
 <span data-ttu-id="6446e-108">**来定位限制中建立的条件的第一行的表格**</span><span class="sxs-lookup"><span data-stu-id="6446e-108">**To position a table to the first row that matches the criteria established in a restriction**</span></span>
  
- <span data-ttu-id="6446e-109">调用[IMAPITable::FindRow](imapitable-findrow.md)方法。</span><span class="sxs-lookup"><span data-stu-id="6446e-109">Call the [IMAPITable::FindRow](imapitable-findrow.md) method.</span></span> <span data-ttu-id="6446e-110">开头为特定的书签所表示的行， **FindRow**搜索任一向前或向后方向来查找与限制中指定的条件匹配的行。</span><span class="sxs-lookup"><span data-stu-id="6446e-110">Starting with the row represented by a particular bookmark, **FindRow** searches in either a forward or backward direction to locate a row that matches the criteria specified in the restriction.</span></span> <span data-ttu-id="6446e-111">**FindRow**可用于实现基于字符的字符串，而不是小数滚动条。</span><span class="sxs-lookup"><span data-stu-id="6446e-111">**FindRow** can be useful for implementing a scroll bar that is based on character strings, instead of fractional values.</span></span> <span data-ttu-id="6446e-112">例如，客户端可以调用**FindRow** MAPI 的实现时搜索通过集成的通讯簿启用用户，通过输入一个或多个字符，找到指定字符开头的名字。</span><span class="sxs-lookup"><span data-stu-id="6446e-112">For example, a client can call MAPI's implementation of **FindRow** when searching through the integrated address book to enable a user, by entering one or more characters, to locate the first name that begins with the specified characters.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="6446e-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6446e-113">See also</span></span>



[<span data-ttu-id="6446e-114">MAPI 表</span><span class="sxs-lookup"><span data-stu-id="6446e-114">MAPI Tables</span></span>](mapi-tables.md)

