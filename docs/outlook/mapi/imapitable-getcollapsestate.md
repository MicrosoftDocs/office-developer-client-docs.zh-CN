---
title: IMAPITableGetCollapseState
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPITable.GetCollapseState
api_type:
- COM
ms.assetid: fd4ea496-4c83-49cd-854e-f373cc1ed2af
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 2c1246c46e9723cd3f6d92f0a44fc1419eef4a2e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775698"
---
# <a name="imapitablegetcollapsestate"></a>IMAPITable::GetCollapseState

  
  
**适用于**： Outlook 
  
返回的数据所需重新生成当前折叠或展开分类表的状态。
  
```cpp
HRESULT GetCollapseState(
ULONG ulFlags,
ULONG cbInstanceKey,
LPBYTE lpbInstanceKey,
ULONG FAR * lpcbCollapseState,
LPBYTE FAR * lppbCollapseState
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> 保留;必须为零。
    
 _cbInstanceKey_
  
> [in]_LpbInstanceKey_参数指向的实例项中的字节数。 
    
 _lpbInstanceKey_
  
> [in]应重新生成一个指向当前折叠或展开状态的行的**PR_INSTANCE_KEY** ([PidTagInstanceKey](pidtaginstancekey-canonical-property.md)) 属性。 _LpbInstanceKey_参数不能为 NULL。 
    
 _lpcbCollapseState_
  
> [输出]一个指向结构_lppbCollapseState_参数指向的计数。 
    
 _lppbCollapseState_
  
> [输出]指向包含介绍当前表视图的数据结构的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功保存分类的表的状态。
    
MAPI_E_BUSY 
  
> 正在进行中，可以防止启动操作是另一个操作。 应允许正在进行的操作完成或应停止。
    
MAPI_E_NO_SUPPORT 
  
> 表不支持分类和展开和折叠视图。
    
## <a name="remarks"></a>备注

**IMAPITable::GetCollapseState**方法处理所[IMAPITable::SetCollapseState](imapitable-setcollapsestate.md)方法更改用户的分类表视图。 **GetCollapseState**保存数据所需的**SetCollapseState**用于重新生成适当类别分类的表的视图。 服务提供商确定要保存的数据。 但是，大多数服务提供商实现**GetCollapseState**保存下列： 
  
- 排序关键字 （标准的列和类别列）。
    
- 有关实例键所表示的行的信息。
    
- 若要还原的表的折叠和展开类别的信息。
    
有关分类表的详细信息，请参阅[排序和分类](sorting-and-categorization.md)。
  
## <a name="notes-to-implementers"></a>针对实施者的注释

_LppbCollapseState_参数中存储的表的所有节点的当前状态。 
  
## <a name="notes-to-callers"></a>给调用方的说明

调用**SetCollapseState**之前，始终调用**GetCollapseState** 。 
  
## <a name="see-also"></a>另请参阅



[IMAPITable::SetCollapseState](imapitable-setcollapsestate.md)
  
[IMAPITable: IUnknown](imapitableiunknown.md)

