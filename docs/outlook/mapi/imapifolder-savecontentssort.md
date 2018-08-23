---
title: IMAPIFolderSaveContentsSort
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIFolder.SaveContentsSort
api_type:
- COM
ms.assetid: 5ae3fdf0-6193-4c1f-bd2e-d69c56d69773
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 1f79265c4356747e64aa8102dd4486db229baf5a
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22579660"
---
# <a name="imapifoldersavecontentssort"></a>IMAPIFolder::SaveContentsSort

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
设置某个文件夹的内容表的默认排序次序。
  
```cpp
HRESULT SaveContentsSort(
  LPSSortOrderSet lpSortCriteria,
  ULONG ulFlags
);
```

## <a name="parameters"></a>参数

 _lpSortCriteria_
  
> [in]一个指向[SSortOrderSet](ssortorderset.md)结构，其中包含的默认排序次序。 
    
 _ulFlags_
  
> [in]设置控制默认排序顺序的方式的标志位掩码。 可以设置以下标记：
    
RECURSIVE_SORT 
  
> 设置的默认排序顺序适用于指示的文件夹和所有子文件夹。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功保存的排序次序。
    
MAPI_E_NO_SUPPORT 
  
> 消息存储提供程序不支持保存其文件夹内容表的排序次序。
    
## <a name="remarks"></a>注解

**IMAPIFolder::SaveContentsSort**方法可创建一个文件夹内容表的默认排序次序。 即，当客户端代码调用**SaveContentsSort**后调用该文件夹的[IMAPIContainer::GetContentsTable](imapicontainer-getcontentstable.md)方法，将建立**SaveContentsSort**顺序出现返回的内容表中的行。
  
并非所有的消息存储提供程序支持**SaveContentsSort**;它是适用于从**SaveContentsSort**方法返回 MAPI_E_NO_SUPPORT 的消息存储提供程序。 
  
## <a name="see-also"></a>另请参阅



[IMAPIContainer::GetContentsTable](imapicontainer-getcontentstable.md)
  
[SSortOrderSet](ssortorderset.md)
  
[IMAPIFolder : IMAPIContainer](imapifolderimapicontainer.md)

