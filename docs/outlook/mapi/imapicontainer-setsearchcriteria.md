---
title: IMAPIContainerSetSearchCriteria
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIContainer.SetSearchCriteria
api_type:
- COM
ms.assetid: b5eb1841-e450-4024-aeaa-3b5a492ddb99
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: a6168e8fced2fff3a7f9d273e47ed2410ac4c010
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33427197"
---
# <a name="imapicontainersetsearchcriteria"></a>IMAPIContainer::SetSearchCriteria

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
为容器建立搜索条件。
  
```cpp
HRESULT SetSearchCriteria(
  LPSRestriction lpRestriction,
  LPENTRYLIST lpContainerList,
  ULONG ulSearchFlags
);
```

## <a name="parameters"></a>参数

 _lpRestriction_
  
> [in]指向定义 [搜索条件的 SRestriction](srestriction.md) 结构的指针。 如果在  _lpRestriction_ 参数中传递 NULL，则再次使用最近用于此容器的搜索条件。 对于容器中的第一个搜索，不应在  _lpRestriction_ 中传递 NULL。 
    
 _lpContainerList_
  
> [in]指向表示要包含在搜索中的容器的条目标识符数组的指针。 如果客户端在  _lpContainerList_ 参数中传递 NULL，则最近用于搜索此容器的条目标识符将用于新搜索。 对于容器中的第一个搜索，客户端不应在  _lpContainerList_ 中传递 NULL。 
    
 _ulSearchFlags_
  
> [in]控制搜索执行方式的标志的位掩码。 可以设置以下标志：
    
BACKGROUND_SEARCH 
  
> 相对于其他搜索，搜索应按正常优先级运行。 不能同时设置此标志和 FOREGROUND_SEARCH 标志。
    
FOREGROUND_SEARCH 
  
> 搜索应相对于其他搜索以高优先级运行。 不能同时设置此标志和 BACKGROUND_SEARCH 标志。
    
NON_CONTENT_INDEXED_SEARCH
  
> 搜索不应使用内容索引来查找匹配的条目。 此标志仅对应用商店Exchange有效。
    
RECURSIVE_SEARCH 
  
> 搜索应包括在  _lpContainerList_ 参数中指定的容器及其所有子容器。 不能同时设置此标志和 SHALLOW_SEARCH 标志。 
    
RESTART_SEARCH 
  
> 如果这是对 **SetSearchCriteria** 的首次调用，应启动搜索;如果搜索处于非活动状态，则重新启动搜索。 不能同时设置此标志和 STOP_SEARCH 标志。
    
SHALLOW_SEARCH 
  
> 搜索应仅在  _lpContainerList_ 参数中指定的容器中查找匹配的条目。 不能同时设置此标志和 RECURSIVE_SEARCH 标记。 
    
STOP_SEARCH 
  
> 应停止搜索。 不能同时设置此标志和 RESTART_SEARCH 标志。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功设置搜索条件。
    
MAPI_E_TOO_COMPLEX 
  
> 服务提供商不支持指定的搜索条件。
    
## <a name="remarks"></a>备注

**IMAPIContainer：：SetSearchCriteria** 方法为支持搜索的容器（通常为搜索结果文件夹）建立搜索条件。 搜索结果文件夹包含指向符合搜索条件的邮件的链接;实际邮件仍存储在其原始位置。 搜索结果文件夹中包含的唯一唯一数据是其内容表。 应用搜索限制后，搜索结果文件夹的内容表包含邮件存储的合并内容。 
  
搜索操作仅适用于此合并的内容表;它不会搜索其他搜索结果文件夹。 搜索结果仅返回与搜索条件匹配的邮件;不返回文件夹层次结构。
  
搜索完成后，控制权将返回到客户端。
  
## <a name="notes-to-implementers"></a>针对实现者的说明

通讯簿容器通过向内容表应用限制来建立搜索条件。 有关搜索条件及通讯簿容器的信息，请参阅 [实现高级搜索](implementing-advanced-searching.md)。
  
您应支持对搜索结果文件夹中的邮件执行打开、复制、移动和删除操作，而不是对搜索结果文件夹本身执行。 不允许在搜索结果文件夹中创建邮件或将邮件复制到搜索结果文件夹中。 
  
## <a name="notes-to-callers"></a>给调用方的说明

若要搜索邮件收件人，请设置 _lpRestriction_ 以指向子对象限制，将 [SSubRestriction 结构中的 ulSubObject](ssubrestriction.md)成员设置为 **PR_MESSAGE_RECIPIENTS** ([PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md)) 。  若要搜索附件，将 **ulSubObject** 成员设置为PR_MESSAGE_ATTACHMENTS ([PidTagMessageAttachments](pidtagmessageattachments-canonical-property.md)) 。 将 **lpRes** 成员设置为指向描述收件人或附件的搜索条件的属性限制。 
  
例如，若要查找扩展名为 .mss 的文件附件，将 **ulSubObject** 设置为 **PR_MESSAGE_ATTACHMENTS，** 将 **lpRes** 设置为与 **PR_ATTACH_EXTENSION** ([PidTagAttachExtension](pidtagattachextension-canonical-property.md)) .mss 匹配的属性限制。
  
在  _ulSearchFlags_ 参数中设置 FOREGROUND_SEARCH 标志可能会导致系统性能降低。 
  
可以使用 **SetSearchCriteria** 更改已在进行中的搜索的搜索条件。 您可以指定新的限制、要搜索的文件夹的新列表以及新的搜索优先级，例如将搜索升级到更高的优先级。 搜索优先级的更改不会导致现有搜索重新启动，但搜索条件的其他更改可能会重新启动。 
  
当您使用搜索结果文件夹时，您可以删除该文件夹或将其保持打开状态，供以后使用。 如果删除搜索结果文件夹，则仅删除邮件链接。 实际邮件仍保留在父文件夹中。 
  
有关搜索结果文件夹详细信息，请参阅 [MAPI 搜索文件夹](mapi-search-folders.md)。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|HierarchyTableDlg.cpp  <br/> |CHierarchyTableDlg：：OnEditSearchCriteria  <br/> |MFCMAPI 使用 **IMAPIContainer：：SetSearchCriteria** 方法在用户编辑文件夹后为文件夹编写搜索条件。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIContainer::GetContentsTable](imapicontainer-getcontentstable.md)
  
[IMAPIContainer::OpenEntry](imapicontainer-openentry.md)
  
[IMAPIFolder::CreateFolder](imapifolder-createfolder.md)
  
[IMAPIFolder : IMAPIContainer](imapifolderimapicontainer.md)
  
[SPropertyRestriction](spropertyrestriction.md)
  
[SRestriction](srestriction.md)
  
[SSubRestriction](ssubrestriction.md)
  
[IMAPIContainer : IMAPIProp](imapicontainerimapiprop.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

