---
title: 使用小数值设置表位置
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 80d31611-e508-4b17-b482-bedf76db26ff
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 7800a58cad7b4e2b0b1696706c8e1d401ed424d7
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33437334"
---
# <a name="setting-table-position-with-a-fractional-value"></a>使用小数值设置表位置

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
表格用户可以移动到表示行占总行的大致百分比的位置。 这种定位方法不是移动到精确行，而是根据分数将表格划分为多个部分。 例如，表格用户可以移动到表格的半向点或经过表格的 7/8 行。 
  
 **将光标移动大致的行数**
  
- 调用 [IMAPITable：：SeekRowApprox](imapitable-seekrowapprox.md)。 **SeekRowApprox** 将移动到代表相对于表格开头的行的特定百分比的行。 此百分比在  _ulNumerator_ 和  _ulDenominator_ 参数中指定。 **SeekRowApprox** 通常用于实现滚动条。 
    
 **确定表的近似位置**
  
- 调用 [IMAPITable：：QueryPosition](imapitable-queryposition.md)。 **QueryPosition** 可用于通知用户当前位置。 它基于表格中的行数和当前行的行数设置小数值。 预计此值表示近似值。 建议表实施者不要计算精确位置，因为调用准确的实现成本可能很高，尤其是在分类表上。 
    
## <a name="see-also"></a>另请参阅



[MAPI 表](mapi-tables.md)

