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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32286937"
---
# <a name="imapicontainergethierarchytable"></a>IMAPIContainer::GetHierarchyTable

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
返回指向容器的层次结构表的指针。
  
```cpp
HRESULT GetHierarchyTable(
  ULONG ulFlags,
  LPMAPITABLE FAR * lppTable
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> 实时用于控制如何在表中返回信息的标志的位掩码。 可以设置以下标志:
    
CONVENIENT_DEPTH 
  
> 使用多个级别中的容器填充层次结构表。 如果未设置 CONVENIENT_DEPTH, 则层次结构表仅包含容器的直接子容器。
    
MAPI_DEFERRED_ERRORS 
  
> 在将表提供给调用程序之前, 可能会成功返回**GetHierarchyTable** 。 如果该表不可用, 则进行后续的表调用可能会引发错误。 
    
MAPI_UNICODE 
  
> 请求以 Unicode 格式返回包含字符串数据的列。 如果未设置 MAPI_UNICODE 标志, 则字符串应以 ANSI 格式返回。 
    
SHOW_SOFT_DELETES
  
> 显示当前标记为软删除的项目, 即它们处于 "已删除邮件" 保留时间阶段。
    
 _lppTable_
  
> 排除指向层次结构表的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功检索层次结构表。
    
MAPI_E_BAD_CHARWIDTH 
  
> 设置了 MAPI_UNICODE 标志, 且实现不支持 unicode, 或者未设置 MAPI_UNICODE, 且实现仅支持 UNICODE。
    
MAPI_E_NO_SUPPORT 
  
> 容器没有子容器, 无法提供层次结构表。
    
## <a name="remarks"></a>注解

**IMAPIContainer:: GetHierarchyTable**方法返回指向容器的层次结构表的指针。 层次结构表包含容器中的子容器的摘要信息。 文件夹层次结构表保留有关子文件夹的信息;通讯簿层次结构表格保存有关子通讯簿容器和通讯组列表的信息。 
  
有些容器可能没有子容器。 这些容器从其**GetHierarchyTable**的实现返回 MAPI_E_NO_SUPPORT。
  
设置 CONVENIENT_DEPTH 标志后, 层次结构表中的每一行也包含**PR_DEPTH** ([PidTagDepth](pidtagdepth-canonical-property.md)) 属性作为一列。 **PR_DEPTH**指示相对于实现表的容器的每个容器的级别。 实现容器的直接子容器的深度为零, 零深度容器中的子容器的深度为 1, 依此类推。 **PR_DEPTH**的值按级别 deepens 的层次结构增长。 
  
有关层次结构表中的必填列和可选列的完整列表, 请参阅[层次结构表](hierarchy-tables.md)。
  
## <a name="notes-to-implementers"></a>针对实现者的说明

如果您支持容器的层次结构表, 则还必须执行以下操作:
  
- 支持对容器的[IMAPIProp:: OpenProperty](imapiprop-openproperty.md)方法的调用, 以打开**PR_CONTAINER_HIERARCHY** ([PidTagContainerHierarchy](pidtagcontainerhierarchy-canonical-property.md)) 属性。
    
- 从对容器的[IMAPIProp:: GetPropList](imapiprop-getproplist.md)或[IMAPIProp:: GetProps](imapiprop-getprops.md)方法的调用中返回**PR_CONTAINER_HIERARCHY** 。 
    
## <a name="notes-to-callers"></a>给调用方的说明

字符串和二进制内容表中的列可以被截断。 通常, 提供程序返回255个字符。 由于您无法事先知道表是否包括截断的列, 因此假定列的长度为255或510字节时, 将截断列。 如果需要, 您始终可以从对象中直接检索已截断列的完整值, 方法是使用其条目标识符将其打开, 然后调用[IMAPIProp:: GetProps](imapiprop-getprops.md)方法。 
  
根据提供程序的实现, 限制和排序操作可应用于整个字符串或该字符串的截断版本。 此外, 不能保证存储提供程序遵循为层次结构表指定的排序顺序设置[SSortOrderSet](ssortorderset.md) 。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|HierarchyTableTreeCtrl  <br/> |CHierarchyTableTreeCtrl:: GetHierarchyTable  <br/> |CHierarchyTableTreeCtrl 类使用**GetHierarchyTable**获取要在树视图控件中显示的层次结构表。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIProp::GetPropList](imapiprop-getproplist.md)
  
[IMAPIProp::GetProps](imapiprop-getprops.md)
  
[IMAPITable : IUnknown](imapitableiunknown.md)
  
[PidTagContainerHierarchy 规范属性](pidtagcontainerhierarchy-canonical-property.md)
  
[IMAPIContainer : IMAPIProp](imapicontainerimapiprop.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

