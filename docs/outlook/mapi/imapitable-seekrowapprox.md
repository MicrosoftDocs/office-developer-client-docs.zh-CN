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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: bbb79097d03a8ea09cb4aff374231ee780e15395
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33412147"
---
# <a name="imapitableseekrowapprox"></a>IMAPITable::SeekRowApprox

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
将光标移到表中的近似小数位置。 
  
```cpp
HRESULT SeekRowApprox(
ULONG ulNumerator,
ULONG ulDenominator
);
```

## <a name="parameters"></a>参数

 _ulNumerator_
  
> 实时指向表示表位置的分数的分子的指针。 如果_ulNumerator_参数为零, 则光标定位在表的开头, 而不考虑分母值。 如果_ulNumerator_等于_ulDenominator_参数, 则光标定位在最后一个表行之后。 
    
 _ulDenominator_
  
> 实时指向表示表格位置的分数的分母的指针。 _ulDenominator_参数不能为零。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> seek 操作成功完成。
    
MAPI_E_BUSY 
  
> 正在进行另一个操作, 以防止启动行查找操作。 应允许正在进行的操作完成, 或者应已停止。
    
## <a name="remarks"></a>说明

在调用**IMAPITable:: SeekRowApprox**方法后, 表中的游标位置是分数, 可能不是确切的 heuristically。 例如, 某些提供程序可能会在二进制树的顶部实现一个表, 并将表的中间点视为树的顶部, 以提高性能原因。 如果树未平衡, 则使用的半点可能不会正好在表的一半。 
  
## <a name="notes-to-callers"></a>给调用方的说明

调用**SeekRowApprox**以提供滚动条实现的数据。 例如, 如果用户将滚动块2/3 放在滚动条的上方, 则可以通过调用**SeekRowApprox**并使用_ulNumerator_和_ulDenominator_传入等效的分数值来对该操作建模。 **SeekRowApprox**搜索始终是从表的开头开始的绝对路径。 若要移到表的末尾, _ulNumerator_和_ulDenominator_中的值必须相同。 
  
使用任何合适的数字方案。 也就是说, 若要定位到表的正中间位置, 可以指定1/2、10/20 或50/100。 
  
## <a name="see-also"></a>另请参阅



[IMAPITable : IUnknown](imapitableiunknown.md)

