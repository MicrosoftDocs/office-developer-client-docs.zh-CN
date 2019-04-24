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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32349292"
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
  
> 实时标志的位掩码, 用于控制传入的字符串的类型。 可以设置以下标志:
    
MAPI_UNICODE 
  
> 传入的字符串采用 Unicode 格式。 如果未设置 MAPI_UNICODE 标志, 则字符串将采用 ANSI 格式。
    
 _lppRestriction_
  
> 排除指向定义搜索条件的[SRestriction](srestriction.md)结构的指针的指针。 如果客户端应用程序在_lppRestriction_参数中传递了 NULL, 则**GetSearchCriteria**不会返回**SRestriction**结构。 
    
 _lppContainerList_
  
> 排除指向代表要包括在搜索中的容器的条目标识符数组的指针。 如果客户端在_lppContainerList_参数中传递了 NULL, 则**GetSearchCriteria**不会返回条目标识符的数组。 
    
 _lpulSearchState_
  
> 排除指向用于指示当前搜索状态的标志位掩码的指针。 如果客户端在_lpulSearchState_参数中传递了 NULL, 则**GetSearchCriteria**不会返回任何标志。 可以设置以下标志: 
    
SEARCH_FOREGROUND 
  
> 搜索应以高优先级运行, 相对于其他搜索。 如果未设置此标志, 则搜索将以常规优先级 (相对于其他搜索) 运行。
    
SEARCH_REBUILD 
  
> 搜索处于 CPU 密集型模式的操作中, 尝试查找符合条件的邮件。 如果未设置此标志, 则搜索操作的 CPU 密集型部分将结束。 只有在搜索处于活动状态 (即, 如果设置了 SEARCH_RUNNING 标志) 时, 此标志才有意义。
    
SEARCH_RECURSIVE 
  
> 搜索将在指定的容器及其所有子容器中查找匹配的条目。 如果未设置此标志, 则仅搜索在对[IMAPIContainer:: SetSearchCriteria](imapicontainer-setsearchcriteria.md)方法的最后一次调用中显式包含的容器。 
    
SEARCH_RUNNING 
  
> 搜索处于活动状态, 并且正在更新容器的内容表, 以反映邮件存储或通讯簿中的更改。 如果未设置此标志, 则搜索将处于非活动状态, 并且内容表是静态的。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功获取搜索条件。
    
MAPI_E_BAD_CHARWIDTH 
  
> 设置了 MAPI_UNICODE 标志, 且实现不支持 unicode, 或者未设置 MAPI_UNICODE, 且实现仅支持 UNICODE。
    
MAPI_E_NOT_INITIALIZED 
  
> 从不为容器建立搜索条件。
    
## <a name="remarks"></a>注解

**IMAPIContainer:: GetSearchCriteria**方法获取支持搜索的容器的搜索条件, 通常是搜索结果文件夹。 通过调用容器的**IMAPIContainer:: SetSearchCriteria**方法来创建搜索条件。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

仅当通讯簿容器提供与**PR_SEARCH** ([PidTagSearch](pidtagsearch-canonical-property.md)) 属性相关联的高级搜索功能时, 才需要支持**GetSearchCriteria** 。 有关如何为通讯簿容器实施高级搜索功能的详细信息, 请参阅[实施高级搜索](implementing-advanced-searching.md)。
  
## <a name="notes-to-callers"></a>给调用方的说明

完成_lppRestriction_和_lppContainerList_参数指向的数据结构后, 对每个要释放的结构调用[MAPIFreeBuffer](mapifreebuffer.md)一次。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|HierarchyTableDlg  <br/> |CHierarchyTableDlg:: OnEditSearchCriteria  <br/> |MFCMAPI 使用**IMAPIContainer:: GetSearchCriteria**方法从要显示的文件夹中获取搜索条件。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIContainer::SetSearchCriteria](imapicontainer-setsearchcriteria.md)
  
[IMAPIFolder::CreateFolder](imapifolder-createfolder.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)
  
[PidTagSearch 规范属性](pidtagsearch-canonical-property.md)
  
[IMAPIContainer : IMAPIProp](imapicontainerimapiprop.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

