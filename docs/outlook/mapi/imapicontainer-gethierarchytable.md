---
title: IMAPIContainerGetHierarchyTable
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIContainer.GetHierarchyTable
api_type:
- COM
ms.assetid: d0c54092-86a3-47e0-8133-72e119e74b65
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: efc7f7a2fa703004afe361d766e0209ba40ffe46
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33426196"
---
# <a name="imapicontainergethierarchytable"></a>IMAPIContainer::GetHierarchyTable

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
返回一个指向容器层次结构表的指针。
  
```cpp
HRESULT GetHierarchyTable(
  ULONG ulFlags,
  LPMAPITABLE FAR * lppTable
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> [in]控制如何在表中返回信息的位掩码标志。 可以设置以下标志：
    
CONVENIENT_DEPTH 
  
> 使用多个级别的容器填充层次结构表。 如果未CONVENIENT_DEPTH，则层次结构表仅包含容器的直接子容器。
    
MAPI_DEFERRED_ERRORS 
  
> **GetHierarchyTable** 可以成功返回，可能在表对调用方可用之前。 如果表不可用，则进行后续表调用可能会引发错误。 
    
MAPI_UNICODE 
  
> 请求以 Unicode 格式返回包含字符串数据的列。 如果未MAPI_UNICODE，则应该以 ANSI 格式返回字符串。 
    
SHOW_SOFT_DELETES
  
> 显示当前标记为软删除的项目，即它们处于已删除项目的保留时间阶段。
    
 _lppTable_
  
> [out]指向指向层次结构表的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功检索层次结构表。
    
MAPI_E_BAD_CHARWIDTH 
  
> 设置 MAPI_UNICODE 标志，而实现不支持 Unicode，或者MAPI_UNICODE未设置，并且实现仅支持 Unicode。
    
MAPI_E_NO_SUPPORT 
  
> 容器没有子容器，并且无法提供层次结构表。
    
## <a name="remarks"></a>备注

**IMAPIContainer：：GetHierarchyTable** 方法返回指向容器的层次结构表的指针。 层次结构表包含有关容器中子容器的摘要信息。 文件夹层次结构表包含有关子文件夹的信息;通讯簿层次结构表包含有关子通讯簿容器和通讯组列表的信息。 
  
某些容器可能没有子容器。 这些容器从MAPI_E_NO_SUPPORT **GetHierarchyTable 的实现中返回值**。
  
设置 CONVENIENT_DEPTH 标志时，层次结构表中的每一行还将 **PR_DEPTH** ([PidTagDepth](pidtagdepth-canonical-property.md)) 属性作为列。 **PR_DEPTH** 表示每个容器相对于实现表的容器的级别。 实现容器的直接子容器深度为零，零深度容器中的子容器深度为 1，等等。 随着级别 **层次结构PR_DEPTH，** 值会按顺序增加。 
  
有关层次结构表中必需列和可选列的完整列表，请参阅 [层次结构表](hierarchy-tables.md)。
  
## <a name="notes-to-implementers"></a>针对实现者的说明

如果支持容器的层次结构表，则还必须执行以下操作：
  
- 支持调用容器[的 IMAPIProp：：OpenProperty](imapiprop-openproperty.md)方法以打开 PR_CONTAINER_HIERARCHY  ([PidTagContainerHierarchy](pidtagcontainerhierarchy-canonical-property.md)) 属性。
    
- 从 **PR_CONTAINER_HIERARCHY**[的 IMAPIProp：：GetPropList](imapiprop-getproplist.md)或 [IMAPIProp：：GetProps](imapiprop-getprops.md)方法调用中返回值。 
    
## <a name="notes-to-callers"></a>给调用方的说明

字符串和二进制内容表列可能会被截断。 通常，提供程序返回 255 个字符。 由于无法事先知道表是否包含截断的列，因此假定如果列的长度为 255 或 510 字节，则会截断列。 您始终可以在需要时直接从对象检索截断列的完整值，方法是使用其条目标识符打开它，然后调用 [IMAPIProp：：GetProps](imapiprop-getprops.md) 方法。 
  
根据提供程序的实现，限制和排序操作可应用于整个字符串或该字符串的截断版本。 此外，存储提供程序不能保证遵守为层次结构表指定的排序顺序集[SSortOrderSet。](ssortorderset.md) 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|HierarchyTableTreeCtrl.cpp  <br/> |CHierarchyTableTreeCtrl：：GetHierarchyTable  <br/> |CHierarchyTableTreeCtrl 类使用 **GetHierarchyTable** 获取要显示在树视图控件中的层次结构表。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIProp::GetPropList](imapiprop-getproplist.md)
  
[IMAPIProp::GetProps](imapiprop-getprops.md)
  
[IMAPITable : IUnknown](imapitableiunknown.md)
  
[PidTagContainerHierarchy 规范属性](pidtagcontainerhierarchy-canonical-property.md)
  
[IMAPIContainer : IMAPIProp](imapicontainerimapiprop.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

