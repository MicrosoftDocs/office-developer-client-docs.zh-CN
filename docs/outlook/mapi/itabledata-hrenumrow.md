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
  
根据行在表中的位置对其进行检索。 
  
```cpp
HRESULT HrEnumRow(
  ULONG ulRowNumber,
  LPSRow FAR * lppSRow
);
```

## <a name="parameters"></a>参数

 _ulRowNumber_
  
> 实时要为其返回属性的行的编号。 _ulRowNumber_参数中的值可以是0中的任何值, 它指示表中的第一行, 即表示表中的最后一行的 n-1。 
    
 _lppSRow_
  
> 排除指向描述目标行的[SRow](srow.md)结构的指针的指针。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功检索行, 或_ulRowNumber_参数所指定的行号的行不存在。 
    
## <a name="remarks"></a>说明

**ITableData:: HrEnumRow**方法根据顺序编号检索行。 此数字表示插入顺序 (0 表示第一行, 行数减1表示最后一行)。 MAPI 在表数据对象的生存期内保持行插入的时间顺序。 
  
如果_ulRowNumber_中指定的数字不对应于表中的行, 则**HrEnumRow**将返回 S_OK, 并将_lppSRow_参数设置为 NULL。 
  
在创建 table data 对象时, MAPI 使用[MAPIAllocateBuffer](mapiallocatebuffer.md)函数为返回的**SRow**结构分配内存。 调用方必须通过调用[MAPIFreeBuffer](mapifreebuffer.md)函数来释放此内存。 
  
若要按插入顺序检索表中的行, 则表数据对象用户调用**HrEnumRow**方法。 
  
## <a name="see-also"></a>另请参阅



[MAPIAllocateBuffer](mapiallocatebuffer.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)
  
[SRow](srow.md)
  
[ITableData : IUnknown](itabledataiunknown.md)

