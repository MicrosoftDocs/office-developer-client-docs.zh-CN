---
title: IMAPITableQueryPosition
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPITable.QueryPosition
api_type:
- COM
ms.assetid: 510b2e21-ba27-47dd-87cb-2a549e31fa28
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 2e44d824bbb5cc96c51d7ca91eb639001bc52a71
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33415661"
---
# <a name="imapitablequeryposition"></a>IMAPITable::QueryPosition

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
基于小数值检索游标的当前表格行位置。
  
```cpp
HRESULT QueryPosition(
ULONG FAR * lpulRow,
ULONG FAR * lpulNumerator,
ULONG FAR * lpulDenominator
);
```

## <a name="parameters"></a>参数

 _lpulRow_
  
> [out]指向当前行的编号的指针。 行号从零开始;表中的第一行为零。 
    
 _lpulNumerator_
  
> [out]指向确定表格位置的小数的分子的指针。
    
 _lpulDenominator_
  
> [out]指向用于标识表格位置的小数的分母的指针。 _lpulDenominator_ 参数不能为零。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 方法在  _lpulRow_  _、lpulNumerator_ 和  _lpulDenominator 中返回有效值_。
    
## <a name="remarks"></a>备注

**IMAPITable：：QueryPosition** 方法确定当前行的位置，并返回当前行的编号和指示其相对于表格末尾位置的小数值。 MAPI 将当前行定义为要读取的下一行。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

无需为  _lpulDenominator_ 参数返回表中的准确行数;它可以是近似值。 
  
如果无法确定当前行，则返回 _lpulRow 0xFFFFFFFF值。_
  
## <a name="notes-to-callers"></a>给调用方的说明

可以使用 **QueryPosition** 在滚动条中定位滚动框。 例如，在包含 100 行的表中，如果 **QueryPosition** 在  _lpulNumerator_ 参数中返回值 75，  _在 lpulDenominator_ 参数中返回 100，在  _lpulRow_ 参数中返回 75，可以在滚动条中将滚动框定位 3/4。 
  
不要依赖于  _lpulDenominator_ 中的值是表中的行数。 **QueryPosition** 不能始终标识光标定位到的确切行。 
  
对 **QueryPosition 的** 调用可能涉及大量内存，特别是对于大型分类表。 如果  _lpulRow_ 参数设置为 0xFFFFFFFF，则 **QueryPosition** 确定当前行所需的内存过多。 调用 [IMAPITable：：SeekRowApprox](imapitable-seekrowapprox.md) 方法将表定位到  _由 lpulNumerator_ 和  _lpulDenominator_ 参数标识的行。 但是，不要始终预期 **SeekRowApprox** 将同一行 **QueryPosition（** 如果内存不是一个因素）建立为当前位置。 
  
## <a name="see-also"></a>另请参阅



[IMAPITable::SeekRowApprox](imapitable-seekrowapprox.md)
  
[IMAPITable : IUnknown](imapitableiunknown.md)

