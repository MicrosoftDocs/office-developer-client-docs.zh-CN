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
ms.openlocfilehash: 93fb82c6274a1703376d7a9e15f37088e132dc23
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22585890"
---
# <a name="imapicontainersetsearchcriteria"></a>IMAPIContainer::SetSearchCriteria

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
建立容器的搜索条件。
  
```cpp
HRESULT SetSearchCriteria(
  LPSRestriction lpRestriction,
  LPENTRYLIST lpContainerList,
  ULONG ulSearchFlags
);
```

## <a name="parameters"></a>参数

 _lpRestriction_
  
> [in]指向定义的搜索条件的[SRestriction](srestriction.md)结构的指针。 如果_lpRestriction_参数中传递 NULL，则将再次使用此容器的最近使用的搜索条件。 容器中的第一个搜索中_lpRestriction_应不会传递 NULL。 
    
 _lpContainerList_
  
> [in]一个指向表示容器要包括在搜索中的项标识符的数组。 如果客户端中_lpContainerList_参数传递 NULL，最近用于搜索此容器的项标识符用于新搜索。 客户端不应在_lpContainerList_容器中的第一个搜索传递 NULL。 
    
 _ulSearchFlags_
  
> [in]控制如何执行搜索的标志的位掩码。 可以设置以下标志：
    
BACKGROUND_SEARCH 
  
> 搜索应运行在相对于其他搜索普通优先级。 不能同时作为 FOREGROUND_SEARCH 标志设置此标志。
    
FOREGROUND_SEARCH 
  
> 搜索应运行在相对于其他搜索高优先级。 不能同时作为 BACKGROUND_SEARCH 标志设置此标志。
    
NON_CONTENT_INDEXED_SEARCH
  
> 搜索不应使用内容索引来查找匹配项。 此标志是仅供 Exchange 存储区。
    
RECURSIVE_SEARCH 
  
> 搜索应包括_lpContainerList_参数及其所有子容器中指定的容器。 不能同时作为 SHALLOW_SEARCH 标志设置此标志。 
    
RESTART_SEARCH 
  
> 搜索应启动如果这是**SetSearchCriteria**，第一个呼叫，或重新启动如果搜索处于非活动状态。 不能同时作为 STOP_SEARCH 标志设置此标志。
    
SHALLOW_SEARCH 
  
> 搜索应仅在用于匹配条目_lpContainerList_参数中指定的容器中。 不能同时作为 RECURSIVE_SEARCH 标志设置此标志。 
    
STOP_SEARCH 
  
> 应停止搜索。 不能同时作为 RESTART_SEARCH 标志设置此标志。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功设置搜索条件。
    
MAPI_E_TOO_COMPLEX 
  
> 服务提供程序不支持指定的搜索条件。
    
## <a name="remarks"></a>注解

**IMAPIContainer::SetSearchCriteria**方法建立支持搜索，通常为一个搜索结果文件夹的容器中的搜索条件。 搜索结果文件夹包含一些主题的链接，符合搜索条件; 的邮件实际邮件仍存储在其原始位置。 搜索结果文件夹中包含的唯一数据是其内容表。 内容表中的搜索结果文件夹应用搜索限制后已合并的邮件存储的内容。 
  
搜索操作仅适用于该表合并的内容;它不会通过其他搜索结果文件夹搜索。 搜索结果返回符合搜索条件中; 邮件不返回文件夹层次结构。
  
在完成搜索后，将返回到客户端控制权。
  
## <a name="notes-to-implementers"></a>针对实施者的注释

通讯簿容器通过将限制应用于其内容表中建立搜索条件。 有关详细信息搜索条件和通讯簿容器，请参阅[实现高级搜索](implementing-advanced-searching.md)。
  
应支持 open、 复制、 移动和删除操作对搜索结果文件夹内的邮件，而不对搜索结果文件夹本身。 不允许邮件中创建或复制到一个搜索结果文件夹。 
  
## <a name="notes-to-callers"></a>给调用方的说明

若要搜索的邮件的收件人，设置_lpRestriction_以指向与**ulSubObject**成员[SSubRestriction](ssubrestriction.md)结构设置为**PR_MESSAGE_RECIPIENTS** ([PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md)) 中的子对象限制。 若要搜索的附件，将设置为**PR_MESSAGE_ATTACHMENTS** ([PidTagMessageAttachments](pidtagmessageattachments-canonical-property.md)) 的**ulSubObject**成员。 设置要指向的收件人或附件中介绍的搜索标准属性限制的**lpRes**成员。 
  
例如，要查找具有扩展.mss 的文件附件，设置**ulSubObject** **PR_MESSAGE_ATTACHMENTS**和**lpRes**到匹配**PR_ATTACH_EXTENSION** ([PidTagAttachExtension](pidtagattachextension-canonical-property.md)属性限制) 与。 mss。
  
设置 FOREGROUND_SEARCH 标志_ulSearchFlags_参数中可能会导致系统性能降低。 
  
您可以使用**SetSearchCriteria**更改已在进行搜索的搜索条件。 您可以指定新限制、 新列表文件夹搜索和新的搜索优先级，例如将搜索升级到更高的优先级。 搜索优先级中的更改不会导致现有搜索要重新启动，但其他更改搜索标准可以。 
  
当您通过使用的搜索结果文件夹时，可以删除该文件夹或使其保持打开状态以供将来使用。 如果您删除的搜索结果文件夹，将删除仅消息链接。 实际的邮件保留在其父文件夹。 
  
有关搜索结果文件夹的详细信息，请参阅[MAPI 搜索文件夹](mapi-search-folders.md)。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|HierarchyTableDlg.cpp  <br/> |CHierarchyTableDlg::OnEditSearchCriteria  <br/> |MFCMAPI 使用**IMAPIContainer::SetSearchCriteria**方法后用户编辑其文件夹的写入搜索条件。  <br/> |
   
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

