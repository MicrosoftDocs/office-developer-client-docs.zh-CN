---
title: 通过分数值设置表位置
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 80d31611-e508-4b17-b482-bedf76db26ff
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 104de38a41408091a6fbb69995de4f41f6fea6a2
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778763"
---
# <a name="setting-table-position-with-a-fractional-value"></a>通过分数值设置表位置

  
  
**适用于**： Outlook 
  
表用户可以移动到值，该值代表大概所占比例相对于总计行的位置。 而不是移动到精确的行，此方法的定位除以成几部分表基于分数。 表用户可以移动，例如，到表的一半点或为 7/8 通过表的方式的行。 
  
 **将光标近似行数**
  
- 调用[IMAPITable::SeekRowApprox](imapitable-seekrowapprox.md)。 **SeekRowApprox**将移至表示特定所占比例相对开始于 table 的行的行。 在_ulNumerator_和_ulDenominator_参数中指定此百分比。 **SeekRowApprox**经常用于实现滚动条。 
    
 **若要确定表的大概位置**
  
- 调用[IMAPITable::QueryPosition](imapitable-queryposition.md)。 **QueryPosition**可用于通知的用户的当前位置。 设置基于的表中的行数和当前行数的小数值。 希望此值表示近似值。 鼓励不计算确切的位置，因为准确实现成本很高调用，尤其是在分类表上将表实施。 
    
## <a name="see-also"></a>另请参阅



[MAPI 表](mapi-tables.md)

