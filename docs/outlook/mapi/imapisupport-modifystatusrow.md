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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 24718c50d02da5d60a6594f56ea6100650fe9f1a
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775617"
---
# <a name="imapisupportmodifystatusrow"></a>IMAPISupport::ModifyStatusRow

  
  
**适用于**： Outlook 
  
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
  
> [in]属性包括新的或修改状态表中行数。 
    
 _lpColumnVals_
  
> [in]一个指向介绍了要为新的或修改状态表格行中的列包含的属性的属性值的数组。
    
 _ulFlags_
  
> [in]位掩码的标志，控制如何处理定义状态表格行的信息。 可以设置以下标记：
    
STATUSROW_UPDATE 
  
> 指示 MAPI 合并包括数组所指的_lpColumnVals_与现有状态表行，而不是一个新行中的属性。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功更新状态表。
    
## <a name="remarks"></a>说明

**IMAPISupport::ModifyStatusRow**方法将执行所有服务提供商支持对象。 服务提供商调用**ModifyStatusRow**在登录时，将行添加到状态表和其他更新行在会话期间的时间。 **ModifyStatusRow**将 MAPI 提供构建状态表所需的信息。 
  
## <a name="notes-to-callers"></a>给调用方的说明

调用**ModifyStatusRow**对您现有的状态表格行中的属性进行更改时，请设置 STATUSROW_UPDATE 标志。 这样通知 MAPI， _lpColumnVals_参数中传递仅正在更改的列。 
  
客户端可以使用状态表中的信息，以访问您状态的对象。 
  
您应在您状态的表格行中包括的列的完整列表，请参阅[状态表](status-tables.md)。
  
## <a name="see-also"></a>另请参阅



[IMAPISupport : IUnknown](imapisupportiunknown.md)

