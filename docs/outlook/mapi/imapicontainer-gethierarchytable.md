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
ms.openlocfilehash: 88b6f220f812f419b3f881aaa7f70a22186b589e
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22563798"
---
# <a name="imapicontainergethierarchytable"></a>IMAPIContainer::GetHierarchyTable

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
返回到容器的层次结构表的指针。
  
```cpp
HRESULT GetHierarchyTable(
  ULONG ulFlags,
  LPMAPITABLE FAR * lppTable
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> [in]位掩码的标志，控制如何将信息返回表中。 可以设置以下标志：
    
CONVENIENT_DEPTH 
  
> 用来自多个级别的容器中填充的层次结构表。 如果未设置 CONVENIENT_DEPTH，层次结构表包含仅容器的直接子容器。
    
MAPI_DEFERRED_ERRORS 
  
> **通讯**可以成功，可能之前返回表可用于将呼叫者。 如果表不可用，则进行后续表呼叫会引发错误。 
    
MAPI_UNICODE 
  
> Unicode 格式返回包含字符串数据的列的请求。 如果未设置 MAPI_UNICODE 标志，应以 ANSI 格式返回字符串。 
    
SHOW_SOFT_DELETES
  
> 显示项目的当前标记为软删除 — 即，它们是中已删除的邮件保留时间阶段。
    
 _lppTable_
  
> [输出]指向与层次结构表的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功检索层次结构表。
    
MAPI_E_BAD_CHARWIDTH 
  
> 既设置了 MAPI_UNICODE 标志实现不支持 Unicode，或未设置 MAPI_UNICODE 并实现支持仅 Unicode。
    
MAPI_E_NO_SUPPORT 
  
> 容器具有没有子容器，并不能提供层次结构表。
    
## <a name="remarks"></a>注解

**IMAPIContainer::GetHierarchyTable**方法返回到容器的层次结构表的指针。 层次结构表包含有关容器中的子容器的摘要信息。 文件夹层次结构表子文件夹; 有关保留的信息通讯簿层次结构表保留信息子地址簿容器和通讯组列表。 
  
很可能为一些容器具有没有子容器。 这些容器返回 MAPI_E_NO_SUPPORT 从**通讯**其实现。
  
当设置 CONVENIENT_DEPTH 标志时，层次结构表中的各行还作为列包含**PR_DEPTH** ([PidTagDepth](pidtagdepth-canonical-property.md)) 属性。 **PR_DEPTH**指示相对于容器实现表的每个容器的级别。 实施容器的直接子容器位于深度零，零深度容器中的子容器的深度，依此类推。 **PR_DEPTH**的值增加按顺序的层次结构级别深化。 
  
必需的和可选层次结构表中的列的完整列表，请参阅[层次结构表](hierarchy-tables.md)。
  
## <a name="notes-to-implementers"></a>针对实施者的注释

如果您支持您的容器层次结构表，还必须执行以下操作：
  
- 支持对容器的[IMAPIProp::OpenProperty](imapiprop-openproperty.md)方法的调用，以打开**PR_CONTAINER_HIERARCHY** ([PidTagContainerHierarchy](pidtagcontainerhierarchy-canonical-property.md)) 属性。
    
- 返回**PR_CONTAINER_HIERARCHY**中容器的[IMAPIProp::GetPropList](imapiprop-getproplist.md)或[IMAPIProp::GetProps](imapiprop-getprops.md)方法调用。 
    
## <a name="notes-to-callers"></a>给调用方的说明

可以截断字符串和二进制内容表格列。 通常情况下，提供程序返回 255 个字符。 因为您无法知道提前是否表包含截断的列，假定一列被截断如果列的长度为 255 个或 510 字节。 直接从通过使用其条目标识符来打开它，然后调用[IMAPIProp::GetProps](imapiprop-getprops.md)方法的对象，总是可以检索有必要，截断列中的完整值。 
  
具体取决于提供程序的实现、 限制和排序操作可以应用到整个字符串或该字符串的截断版本。 此外，存储提供程序不能保证服从的设置的排序顺序[SSortOrderSet](ssortorderset.md)指定层次结构表。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|HierarchyTableTreeCtrl.cpp  <br/> |CHierarchyTableTreeCtrl::GetHierarchyTable  <br/> |CHierarchyTableTreeCtrl 类使用**通讯**获取要在树视图控件中显示的层次结构表。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIProp::GetPropList](imapiprop-getproplist.md)
  
[IMAPIProp::GetProps](imapiprop-getprops.md)
  
[IMAPITable : IUnknown](imapitableiunknown.md)
  
[PidTagContainerHierarchy 规范属性](pidtagcontainerhierarchy-canonical-property.md)
  
[IMAPIContainer : IMAPIProp](imapicontainerimapiprop.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

