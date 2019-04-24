---
title: 使用分数值设置表位置
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 80d31611-e508-4b17-b482-bedf76db26ff
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 7800a58cad7b4e2b0b1696706c8e1d401ed424d7
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32339261"
---
# <a name="setting-table-position-with-a-fractional-value"></a>使用分数值设置表位置

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
表用户可以移动到表示相对于总数的大概百分比的行的位置。 这种定位方法将表分成多个部分, 而不是移到确切的行。 例如, 表用户可以移动到表的半角点, 或者移动到表中的7/8 行。 
  
 **将游标移动大约行数**
  
- 调用[IMAPITable:: SeekRowApprox](imapitable-seekrowapprox.md)。 **SeekRowApprox**移动到表示特定百分比的行 (相对于表的开头) 的行。 此百分比在_ulNumerator_和_ulDenominator_参数中指定。 **SeekRowApprox**经常用于实现滚动条。 
    
 **确定表的大概位置**
  
- 调用[IMAPITable:: QueryPosition](imapitable-queryposition.md)。 **QueryPosition**可用于通知用户当前位置。 它根据表中的行数和当前行数设置一个小数值。 预期此值表示近似值。 建议不要将表实施者计算出确切的位置, 因为准确的实现可能会导致调用开销较高, 尤其是在分类表上。 
    
## <a name="see-also"></a>另请参阅



[MAPI 表](mapi-tables.md)

