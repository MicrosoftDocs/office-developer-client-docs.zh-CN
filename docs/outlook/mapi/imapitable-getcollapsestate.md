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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 97575a65cd6825e07d6f11c813beec539f99f53a
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33436074"
---
# <a name="imapitablegetcollapsestate"></a>IMAPITable::GetCollapseState

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
返回重建已分类表的当前折叠或已展开状态所需的数据。
  
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
  
> 保留必须为零。
    
 _cbInstanceKey_
  
> 实时由_lpbInstanceKey_参数指向的实例键中的字节数。 
    
 _lpbInstanceKey_
  
> 实时一个指针, 指向应重新生成当前折叠或展开状态的行的**PR_INSTANCE_KEY** ([PidTagInstanceKey](pidtaginstancekey-canonical-property.md)) 属性。 _lpbInstanceKey_参数不能为 NULL。 
    
 _lpcbCollapseState_
  
> 排除一个指针, 指向_lppbCollapseState_参数指向的结构的计数。 
    
 _lppbCollapseState_
  
> 排除指向指向结构的指针的指针, 该结构包含描述当前表视图的数据。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功保存已分类表的状态。
    
MAPI_E_BUSY 
  
> 正在进行另一个操作, 以阻止操作启动。 应允许正在进行的操作完成, 或者应已停止。
    
MAPI_E_NO_SUPPORT 
  
> 该表不支持分类和展开和折叠视图。
    
## <a name="remarks"></a>说明

**imapitable:: GetCollapseState**方法与[imapitable:: SetCollapseState](imapitable-setcollapsestate.md)方法一起使用, 以更改用户的已分类表的视图。 **GetCollapseState**保存**SetCollapseState**所需的数据, 以重建已分类表的类别的相应视图。 服务提供商确定要保存的数据。 但是, 大多数实现**GetCollapseState**的服务提供程序都会保存以下内容: 
  
- 排序键 ("标准列" 和 "类别" 列)。
    
- 有关实例键表示的行的信息。
    
- 用于还原表的折叠和展开类别的信息。
    
有关分类表的详细信息, 请参阅[排序和分类](sorting-and-categorization.md)。
  
## <a name="notes-to-implementers"></a>针对实现者的说明

将表的所有节点的当前状态存储在_lppbCollapseState_参数中。 
  
## <a name="notes-to-callers"></a>给调用方的说明

在调用**SetCollapseState**之前, 请务必先调用**GetCollapseState** 。 
  
## <a name="see-also"></a>另请参阅



[IMAPITable::SetCollapseState](imapitable-setcollapsestate.md)
  
[IMAPITable : IUnknown](imapitableiunknown.md)

