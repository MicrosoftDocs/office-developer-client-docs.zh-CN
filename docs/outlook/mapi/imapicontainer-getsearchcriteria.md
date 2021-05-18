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
ms.openlocfilehash: 7845238722ce81b84210b6f4fc33f9df0abacc07
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33412021"
---
# <a name="imapicontainergetsearchcriteria"></a>IMAPIContainer::GetSearchCriteria

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
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
  
> [in]控制传入字符串类型的标志位掩码。 可以设置以下标志：
    
MAPI_UNICODE 
  
> 传入字符串采用 Unicode 格式。 如果未MAPI_UNICODE，则字符串采用 ANSI 格式。
    
 _lppRestriction_
  
> [out]指向定义搜索条件的 [SRestriction](srestriction.md) 结构的指针的指针。 如果客户端应用程序在  _lppRestriction_ 参数中传递 NULL， **则 GetSearchCriteria** 不会返回 **SRestriction** 结构。 
    
 _lppContainerList_
  
> [out]指向指向表示要包含在搜索中的容器的条目标识符数组的指针的指针。 如果客户端在  _lppContainerList_ 参数中传递 NULL， **则 GetSearchCriteria** 不会返回条目标识符数组。 
    
 _lpulSearchState_
  
> [out]指向用于指示搜索当前状态的标志的位掩码的指针。 如果客户端在  _lpulSearchState_ 参数中传递 NULL， **则 GetSearchCriteria** 不返回任何标志。 可以设置以下标志： 
    
SEARCH_FOREGROUND 
  
> 搜索应相对于其他搜索以高优先级运行。 如果未设置此标志，则相对于其他搜索以正常优先级运行搜索。
    
SEARCH_REBUILD 
  
> 搜索将进入其操作占用大量 CPU 的模式，尝试查找与条件匹配的消息。 如果未设置此标志，则搜索操作中占用大量 CPU 的部分将结束。 此标志仅在搜索处于活动状态（ (，即，如果SEARCH_RUNNING设置该标记) 。
    
SEARCH_RECURSIVE 
  
> 搜索在指定的容器及其所有子容器中查找匹配的条目。 如果未设置此标志，则仅搜索上次调用 [IMAPIContainer：：SetSearchCriteria](imapicontainer-setsearchcriteria.md) 方法时显式包含的容器。 
    
SEARCH_RUNNING 
  
> 搜索处于活动状态，并且正在更新容器的内容表以反映邮件存储或通讯簿中的更改。 如果未设置此标志，则搜索将处于非活动状态，并且内容表是静态的。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功获取搜索条件。
    
MAPI_E_BAD_CHARWIDTH 
  
> 设置 MAPI_UNICODE 标志，而实现不支持 Unicode，或者MAPI_UNICODE未设置，并且实现仅支持 Unicode。
    
MAPI_E_NOT_INITIALIZED 
  
> 从未为容器建立搜索条件。
    
## <a name="remarks"></a>备注

**IMAPIContainer：：GetSearchCriteria** 方法获取支持搜索的容器（通常为搜索结果文件夹）的搜索条件。 通过调用容器的 **IMAPIContainer：：SetSearchCriteria 方法创建搜索** 条件。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

只有在提供与 PR_SEARCH ([PidTagSearch](pidtagsearch-canonical-property.md)属性关联的高级搜索功能时，通讯簿容器才可能需要支持 **GetSearchCriteria**) 。 若要详细了解如何实现通讯簿容器的高级搜索功能，请参阅 [实现高级搜索](implementing-advanced-searching.md)。
  
## <a name="notes-to-callers"></a>给调用方的说明

完成 _lppRestriction_ 和 _lppContainerList_ 参数指向的数据结构后，请针对要释放的每个结构调用一次 [MAPIFreeBuffer。](mapifreebuffer.md) 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|HierarchyTableDlg.cpp  <br/> |CHierarchyTableDlg：：OnEditSearchCriteria  <br/> |MFCMAPI 使用 **IMAPIContainer：：GetSearchCriteria** 方法从要显示的文件夹获取搜索条件。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIContainer::SetSearchCriteria](imapicontainer-setsearchcriteria.md)
  
[IMAPIFolder::CreateFolder](imapifolder-createfolder.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)
  
[PidTagSearch 规范属性](pidtagsearch-canonical-property.md)
  
[IMAPIContainer : IMAPIProp](imapicontainerimapiprop.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

