---
title: ITableDataHrEnumRow
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- ITableData.HrEnumRow
api_type:
- COM
ms.assetid: b25d9f2b-9454-4983-98f7-6a051a3b8a04
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 50fd96acd0989459c9887770ec5a3a236f182da5
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33418370"
---
# <a name="itabledatahrenumrow"></a>ITableData::HrEnumRow

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
根据行在表中的位置检索行。 
  
```cpp
HRESULT HrEnumRow(
  ULONG ulRowNumber,
  LPSRow FAR * lppSRow
);
```

## <a name="parameters"></a>参数

 _ulRowNumber_
  
> [in]要返回其属性的行数。 _ulRowNumber_ 参数中的值可以是 0（表示表中第一行）到 n - 1（表示表格中的最后一行）的任何值。 
    
 _lppSRow_
  
> [out]指向描述目标行 [的 SRow](srow.md) 结构的指针的指针。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 该行检索成功，或者  _ulRowNumber_ 参数指定的行号的行不存在。 
    
## <a name="remarks"></a>备注

**ITableData：：HrEnumRow** 方法基于顺序编号检索行。 此数字表示插入顺序， (0 表示第一行，而行数减 1 表示最后一) 。 MAPI 在表数据对象的生存期内保持行插入的此时间顺序。 
  
如果在  _ulRowNumber_ 中指定的数字与表中的行不对应， **则 HrEnumRow** 将返回 S_OK，并且将  _lppSRow_ 参数设置为 NULL。 
  
创建表数据对象时 [，MAPI 通过使用 MAPIAllocateBuffer](mapiallocatebuffer.md)函数为返回的 **SRow** 结构分配内存。 调用方必须通过调用 [MAPIFreeBuffer](mapifreebuffer.md) 函数释放此内存。 
  
若要按插入行的顺序从表中检索行，表数据对象用户调用 **HrEnumRow** 方法。 
  
## <a name="see-also"></a>另请参阅



[MAPIAllocateBuffer](mapiallocatebuffer.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)
  
[SRow](srow.md)
  
[ITableData : IUnknown](itabledataiunknown.md)

