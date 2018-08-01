---
title: IMAPITableSeekRowApprox
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPITable.SeekRowApprox
api_type:
- COM
ms.assetid: ce5e8c43-06af-4afc-9138-5cc51d8fc401
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 12b0c9b40c7ff06e9a3cf8e7929489f30434fa12
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775732"
---
# <a name="imapitableseekrowapprox"></a>IMAPITable::SeekRowApprox

  
  
**适用于**： Outlook 
  
将光标移到表中大约小数位置。 
  
```cpp
HRESULT SeekRowApprox(
ULONG ulNumerator,
ULONG ulDenominator
);
```

## <a name="parameters"></a>参数

 _ulNumerator_
  
> [in]指向分数表示表位置的分子指针。 如果_ulNumerator_参数为零，光标位于无论分母值表的开头。 如果_ulNumerator_等于_ulDenominator_参数，将光标定位后最后一个表格行。 
    
 _ulDenominator_
  
> [in]指向分母的小数部分表示表位置的指针。 _UlDenominator_参数不能为零。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> Seek 操作已成功。
    
MAPI_E_BUSY 
  
> 另一个操作正在进行阻止寻求操作从起始行中。 应允许正在进行的操作完成或应停止。
    
## <a name="remarks"></a>说明

对**IMAPITable::SeekRowApprox**方法的调用之后表中的光标位置是试探性地分数，且可能不可准确。 例如，特定提供程序可能实现二进制树中，在表视为出于性能原因树顶部的表的中点。 如果不平衡树，然后使用的中间点可能不是表到完全一半。 
  
## <a name="notes-to-callers"></a>给调用方的说明

调用**SeekRowApprox**滚动栏实现提供数据。 例如，如果用户定位滚动框 2/3 上向下滚动条，您可以通过调用**SeekRowApprox**和传递中等效的小数值使用_ulNumerator_和_ulDenominator_建模该操作。 **SeekRowApprox**搜索始终是绝对从表的开头。 若要移动到的表的末尾， _ulNumerator_和_ulDenominator_中的值必须相同。 
  
使用适合任何编号方案。 即寻求到表到一半的位置，您可以指定 1/2、 10/20 或 50/100。 
  
## <a name="see-also"></a>另请参阅



[IMAPITable : IUnknown](imapitableiunknown.md)

