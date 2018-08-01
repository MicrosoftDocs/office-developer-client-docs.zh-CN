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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: c3c66b9e54f0776a8afd6b4638d36dec3393dda8
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775710"
---
# <a name="imapitablequeryposition"></a>IMAPITable::QueryPosition

  
  
**适用于**： Outlook 
  
检索当前表行位置的指针，根据分数的值。
  
```cpp
HRESULT QueryPosition(
ULONG FAR * lpulRow,
ULONG FAR * lpulNumerator,
ULONG FAR * lpulDenominator
);
```

## <a name="parameters"></a>参数

 _lpulRow_
  
> [输出]到当前行数的指针。 行号是从零开始;表中的第一行为零。 
    
 _lpulNumerator_
  
> [输出]指向分子分数标识表位置的指针。
    
 _lpulDenominator_
  
> [输出]指向分母分数标识表位置的指针。 _LpulDenominator_参数不能为零。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 该方法返回_lpulRow_、 _lpulNumerator_和_lpulDenominator_中有效的值。
    
## <a name="remarks"></a>说明

**IMAPITable::QueryPosition**方法确定当前行位置，并返回这两个当前行和分数的值，该值指示它表末尾的相对位置的数量。 MAPI 将当前行定义为要读取的下一行。 
  
## <a name="notes-to-implementers"></a>针对实施者的注释

不需要返回_lpulDenominator_参数; 表中的确切的行数它可以是近似值。 
  
如果无法确定当前行，请在_lpulRow_返回 0xFFFFFFFF 值。
  
## <a name="notes-to-callers"></a>给调用方的说明

您可以使用**QueryPosition**定位滚动条中的滚动框。 例如，在表包含 100 的行，如果**QueryPosition** _lpulNumerator_参数， _lpulDenominator_参数中的 100 和_lpulRow_参数中的 75 中返回的值为 75 可以定位滚动框的 3/4跨滚动条方式。 
  
不依赖中_lpulDenominator_正在的表中的行数的值。 **QueryPosition**始终不能确定将光标定位的确切行。 
  
调用**QueryPosition**可能涉及大量内存，特别是对于大分类表。 如果_lpulRow_参数设置为 0xFFFFFFFF，太多的内存，需要**QueryPosition**以确定当前行。 调用[IMAPITable::SeekRowApprox](imapitable-seekrowapprox.md)方法来定位到由_lpulNumerator_和_lpulDenominator_参数标识的行的表。 但是，不始终希望**SeekRowApprox** **QueryPosition**如果内存不已经因素将具有同一行建立与当前的位置。 
  
## <a name="see-also"></a>另请参阅



[IMAPITable::SeekRowApprox](imapitable-seekrowapprox.md)
  
[IMAPITable : IUnknown](imapitableiunknown.md)

