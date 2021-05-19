---
title: IMAPISupportModifyStatusRow
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISupport.ModifyStatusRow
api_type:
- COM
ms.assetid: a304ca8f-e404-4535-be76-0b673f2061a0
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 8c76e6059670e782ea6530ec8e94f77abfe5b9fe
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33417159"
---
# <a name="imapisupportmodifystatusrow"></a>IMAPISupport::ModifyStatusRow

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
通过添加新行或修改现有行来修改状态表。
  
```cpp
HRESULT ModifyStatusRow(
ULONG cValues,
LPSPropValue lpColumnVals,
ULONG ulFlags
);
```

## <a name="parameters"></a>参数

 _cValues_
  
> [in]要包含在新建或修改的状态表行中的属性数。 
    
 _lpColumnVals_
  
> [in]指向一组属性值的指针，这些属性值描述要作为列包含在新的或修改的状态表行中的属性。
    
 _ulFlags_
  
> [in]控制如何处理定义状态表行的信息的位掩码标志。 可以设置以下标志：
    
STATUSROW_UPDATE 
  
> 指示 MAPI 将  _lpColumnVals_ 指向的数组中包含的属性与现有状态表行（而不是新行）合并。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 状态表已成功更新。
    
## <a name="remarks"></a>备注

**IMAPISupport：：ModifyStatusRow** 方法针对所有服务提供程序支持对象实现。 服务提供程序在登录时调用 **ModifyStatusRow** 以将行添加到状态表，在会话期间的其他时间调用以更新该行。 **ModifyStatusRow** 为 MAPI 提供了生成状态表所必需的信息。 
  
## <a name="notes-to-callers"></a>给调用方的说明

在STATUSROW_UPDATE **ModifyStatusRow** 以更改现有状态表行中的属性时，请设置该标志。 这样做会通知 MAPI 仅传递  _lpColumnVals_ 参数中要更改的列。 
  
客户端可以使用状态表中的信息访问状态对象。 
  
有关应在状态表行中包括的列的完整列表，请参阅 [状态表](status-tables.md)。
  
## <a name="see-also"></a>另请参阅



[IMAPISupport : IUnknown](imapisupportiunknown.md)

