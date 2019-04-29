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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: c142424bb050ae287f54a87ea8a5e0ea45acb12c
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33411615"
---
# <a name="imapifoldersavecontentssort"></a>IMAPIFolder::SaveContentsSort

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
设置文件夹的内容表的默认排序顺序。
  
```cpp
HRESULT SaveContentsSort(
  LPSSortOrderSet lpSortCriteria,
  ULONG ulFlags
);
```

## <a name="parameters"></a>参数

 _lpSortCriteria_
  
> 实时指向包含默认排序顺序的[SSortOrderSet](ssortorderset.md)结构的指针。 
    
 _ulFlags_
  
> 实时用于控制如何设置默认排序顺序的标志的位掩码。 可以设置以下标志:
    
RECURSIVE_SORT 
  
> 默认的排序次序将应用于指定的文件夹及其所有子文件夹。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功保存排序顺序。
    
MAPI_E_NO_SUPPORT 
  
> 邮件存储区提供程序不支持保存其文件夹内容表的排序顺序。
    
## <a name="remarks"></a>说明

**IMAPIFolder:: SaveContentsSort**方法为文件夹的内容表建立默认的排序顺序。 也就是说, 当客户端在代码调用**SaveContentsSort**后调用文件夹的[IMAPIContainer:: GetContentsTable](imapicontainer-getcontentstable.md)方法时, 返回的内容表中的行将按**SaveContentsSort**建立的顺序显示。
  
并非所有邮件存储提供程序都支持**SaveContentsSort**;邮件存储提供程序从**SaveContentsSort**方法返回 MAPI_E_NO_SUPPORT 是可接受的。 
  
## <a name="see-also"></a>另请参阅



[IMAPIContainer::GetContentsTable](imapicontainer-getcontentstable.md)
  
[SSortOrderSet](ssortorderset.md)
  
[IMAPIFolder : IMAPIContainer](imapifolderimapicontainer.md)

