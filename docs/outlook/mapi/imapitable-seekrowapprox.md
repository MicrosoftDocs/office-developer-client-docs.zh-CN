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
  
将光标移到表格中的近似小数位置。 
  
```cpp
HRESULT SeekRowApprox(
ULONG ulNumerator,
ULONG ulDenominator
);
```

## <a name="parameters"></a>参数

 _ulNumerator_
  
> [in]指向表示表格位置的小数的分子的指针。 如果  _ulNumerator_ 参数为零，则游标将位于表的开头，而不考虑分母值。 如果  _ulNumerator_ 等于  _ulDenominator_ 参数，则光标位于最后一个表格行之后。 
    
 _ulDenominator_
  
> [in]指向表示表格位置的小数的分母的指针。 _ulDenominator_ 参数不能为零。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 查找操作成功。
    
MAPI_E_BUSY 
  
> 正在进行另一个操作，该操作阻止行的寻找操作启动。 应允许完成或停止进行中的操作。
    
## <a name="remarks"></a>备注

调用 **IMAPITable：：SeekRowApprox** 方法后表格中的光标位置是启发式分数，可能并不精确。 例如，某些提供程序可能在二进制树顶部实现一个表，出于性能原因，将表的中点视为树的顶部。 如果树未平衡，则使用的中点可能并非正好在表格的一半。 
  
## <a name="notes-to-callers"></a>给调用方的说明

调用 **SeekRowApprox** 以提供滚动条实现的数据。 例如，如果用户将滚动框定位在滚动条的 2/3 下，则可以通过调用 **SeekRowApprox，** 然后使用  _ulNumerator_ 和  _ulDenominator_ 传递等效的小数值来为该操作建模。 **SeekRowApprox** 搜索始终从表开头为绝对搜索。 若要移到表末尾  _，ulNumerator_ 和  _ulDenominator_ 中的值必须相同。 
  
使用合适的数字方案。 也就是说，若要在表的一半位置进行查找，可以指定 1/2、10/20 或 50/100。 
  
## <a name="see-also"></a>另请参阅



[IMAPITable : IUnknown](imapitableiunknown.md)

