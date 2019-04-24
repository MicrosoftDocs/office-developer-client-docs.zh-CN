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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32328871"
---
# <a name="imapitablequeryposition"></a>IMAPITable::QueryPosition

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
根据分数值检索游标的当前表行位置。
  
```cpp
HRESULT QueryPosition(
ULONG FAR * lpulRow,
ULONG FAR * lpulNumerator,
ULONG FAR * lpulDenominator
);
```

## <a name="parameters"></a>参数

 _lpulRow_
  
> 排除指向当前行的编号的指针。 行号是从零开始的;表格中的第一行为零。 
    
 _lpulNumerator_
  
> 排除指向标识表位置的分数的分子的指针。
    
 _lpulDenominator_
  
> 排除指向标识表格位置的分数的分母的指针。 _lpulDenominator_参数不能为零。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 该方法在_lpulRow_、 _lpulNumerator_和_lpulDenominator_中返回了有效值。
    
## <a name="remarks"></a>注解

**IMAPITable:: QueryPosition**方法确定当前行位置, 并同时返回当前行的编号和表示其在表末尾的相对位置的小数值。 MAPI 将当前行定义为要读取的下一行。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

您无需为_lpulDenominator_参数返回 table 中的确切行数;它可以是一个近似值。 
  
如果无法确定当前行, 则在_lpulRow_中返回值0xffffffff。
  
## <a name="notes-to-callers"></a>给调用方的说明

您可以使用**QueryPosition**在滚动条中定位滚动框。 例如, 在包含100行的表中, 如果**QueryPosition**在_lpulNumerator_参数中返回值 75, 100 在_lpulDenominator_参数中, 在_lpulRow_参数中为 75, 则可以将滚动框3/4 定位滚动条上的方式。 
  
不要依赖_lpulDenominator_中的值作为表中的行数。 **QueryPosition**不能始终识别游标所定位的确切行。 
  
对**QueryPosition**的调用可能会涉及大量内存, 尤其是对于大型分类的表。 如果将_lpulRow_参数设置为 0xffffffff, 则**QueryPosition**需要过多的内存来确定当前行。 调用[IMAPITable:: SeekRowApprox](imapitable-seekrowapprox.md)方法将表定位到由_lpulNumerator_和_lpulDenominator_参数标识的行。 但是, 如果内存不是一个因素, 则不总是认为**SeekRowApprox**是与当前位置相同的行**QueryPosition**的当前位置建立的。 
  
## <a name="see-also"></a>另请参阅



[IMAPITable::SeekRowApprox](imapitable-seekrowapprox.md)
  
[IMAPITable : IUnknown](imapitableiunknown.md)

