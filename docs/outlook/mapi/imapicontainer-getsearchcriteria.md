---
title: IMAPIContainerGetSearchCriteria
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIContainer.GetSearchCriteria
api_type:
- COM
ms.assetid: 41b6c162-9984-43a3-b38e-44f0afae67de
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 4ca565f97851a2efe2f3279f062f6ea89a4c6326
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22579961"
---
# <a name="imapicontainergetsearchcriteria"></a>IMAPIContainer::GetSearchCriteria

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
获取容器的搜索条件。
  
```cpp
HRESULT GetSearchCriteria(
  ULONG ulFlags,
  LPSRestriction FAR * lppRestriction,
  LPENTRYLIST FAR * lppContainerList,
  ULONG FAR * lpulSearchState
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> [in]位掩码的标志的控制传入的字符串的类型。 可以设置以下标记：
    
MAPI_UNICODE 
  
> 传入的字符串采用 Unicode 格式。 如果未设置 MAPI_UNICODE 标志的字符串是以 ANSI 格式。
    
 _lppRestriction_
  
> [输出]指向[SRestriction](srestriction.md)结构，定义的搜索条件的指针的指针。 如果客户端应用程序中的_lppRestriction_参数传递 NULL， **GetSearchCriteria**不返回**SRestriction**结构。 
    
 _lppContainerList_
  
> [输出]指向为数组表示容器要包括在搜索中的项标识符的指针的指针。 如果客户端中_lppContainerList_参数传递 NULL， **GetSearchCriteria**不返回项标识符的数组。 
    
 _lpulSearchState_
  
> [输出]一个指向用于指示搜索的当前状态标志的位掩码。 如果客户端中_lpulSearchState_参数传递 NULL， **GetSearchCriteria**返回任何标志。 可以设置以下标志： 
    
SEARCH_FOREGROUND 
  
> 搜索应运行在相对于其他搜索高优先级。 如果未设置此标志，则在相对于其他搜索正常优先级运行搜索。
    
SEARCH_REBUILD 
  
> 搜索是 CPU 密集型模式操作，尝试查找符合条件的邮件中。 如果未设置此标志，搜索操作的 CPU 密集型部分是通过。 此标志仅当有意义搜索处于活动状态 （也就是说，如果设置了 SEARCH_RUNNING 标志）。
    
SEARCH_RECURSIVE 
  
> 搜索查找指定的容器的匹配项的所有及其子容器中。 如果未设置此标志，正在搜索仅[IMAPIContainer::SetSearchCriteria](imapicontainer-setsearchcriteria.md)方法的最后一个呼叫中明确包括的容器。 
    
SEARCH_RUNNING 
  
> 搜索处于活动状态且容器的内容表正在更新以反映邮件存储区中的更改或通讯簿。 如果未设置此标志，搜索处于非活动状态并将目录是静态的。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 成功获取的搜索条件。
    
MAPI_E_BAD_CHARWIDTH 
  
> 既设置了 MAPI_UNICODE 标志实现不支持 Unicode，或未设置 MAPI_UNICODE 并实现支持仅 Unicode。
    
MAPI_E_NOT_INITIALIZED 
  
> 搜索条件从不已建立的容器。
    
## <a name="remarks"></a>注解

**IMAPIContainer::GetSearchCriteria**方法获取支持搜索，通常为一个搜索结果文件夹的容器中的搜索条件。 通过调用容器的**IMAPIContainer::SetSearchCriteria**方法创建搜索条件。 
  
## <a name="notes-to-implementers"></a>针对实施者的注释

通讯簿容器可能需要支持**GetSearchCriteria** ，仅当它们提供与**PR_SEARCH** ([PidTagSearch](pidtagsearch-canonical-property.md)) 属性关联的高级的搜索功能。 有关如何实施通讯簿容器的高级的搜索功能的详细信息，请参阅[实现高级搜索](implementing-advanced-searching.md)。
  
## <a name="notes-to-callers"></a>给调用方的说明

在完成时与指向由_lppRestriction_和_lppContainerList_参数的数据结构，调用[MAPIFreeBuffer](mapifreebuffer.md)一次为每个结构必须释放。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|HierarchyTableDlg.cpp  <br/> |CHierarchyTableDlg::OnEditSearchCriteria  <br/> |MFCMAPI 使用**IMAPIContainer::GetSearchCriteria**方法获取从文件夹显示的搜索条件。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIContainer::SetSearchCriteria](imapicontainer-setsearchcriteria.md)
  
[IMAPIFolder::CreateFolder](imapifolder-createfolder.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)
  
[PidTagSearch 规范属性](pidtagsearch-canonical-property.md)
  
[IMAPIContainer : IMAPIProp](imapicontainerimapiprop.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

