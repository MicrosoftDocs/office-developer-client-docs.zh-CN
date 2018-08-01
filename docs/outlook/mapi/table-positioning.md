---
title: 表定位
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: a0cbbc93-8074-4e86-b660-ee7bab910587
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: cec0b3584c6c19abb5f7421f1db0b06c877bb9ac
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778954"
---
# <a name="table-positioning"></a><span data-ttu-id="25717-103">表定位</span><span class="sxs-lookup"><span data-stu-id="25717-103">Table Positioning</span></span>

  
  
<span data-ttu-id="25717-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="25717-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="25717-105">始终由游标表示表格中的当前位置。</span><span class="sxs-lookup"><span data-stu-id="25717-105">The current position within a table is always indicated by a cursor.</span></span> <span data-ttu-id="25717-106">没有为表; 每个视图的一个游标其值由表的实施者设置。</span><span class="sxs-lookup"><span data-stu-id="25717-106">There is one cursor for each view of a table; its value is set by the table's implementer.</span></span> <span data-ttu-id="25717-107">当使用表的客户端或服务提供程序的调用可以更改表的位置时，将重置的游标的值。</span><span class="sxs-lookup"><span data-stu-id="25717-107">When a client or service provider using the table makes a call to change the position of the table, the value of the cursor is reset.</span></span> <span data-ttu-id="25717-108">可以使用更改表的位置：</span><span class="sxs-lookup"><span data-stu-id="25717-108">A table's position can be changed with:</span></span>
  
- <span data-ttu-id="25717-109">书签。</span><span class="sxs-lookup"><span data-stu-id="25717-109">A bookmark.</span></span>
    
- <span data-ttu-id="25717-110">分数的值。</span><span class="sxs-lookup"><span data-stu-id="25717-110">A fractional value.</span></span>
    
- <span data-ttu-id="25717-111">筛选器。</span><span class="sxs-lookup"><span data-stu-id="25717-111">A filter.</span></span>
    

